---
title: "Tag Your AWS Resources in StarCluster"
date: 2014-11-10T22:30:07-07:00
draft: true
---

[StarCluster](http://star.mit.edu/cluster/) is a convenient way to
manage HPC clusters on [Amazon Web Services](https://aws.amazon.com/)
(AWS). If you use the same AWS account for multiple tasks such as 
hosting your web servers and its associated databases, running 
StarCluster how can you tell how much of your bill is from StarCluster?
AWS lets you tag your detailed billing information, this can be used
to get a feel [^1] for how much you spent on a specific tag. You need to enable detailed billing and pick your allocation tags, start by reading the [Billing](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html)
docs.
  
There is also another reason to tag your resources in StarCluster - to
utilize IAM [resource-level
permissions](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-iam-actions-resources.html)
to restrict access, e.g. a IAM StarCluster user can only start/stop
StarCluster, not terminate every EC2 instance in your account. This is a
topic for another blog post, but requires tagging to help restrict
permissions.  
  
There are three steps to enable tagging within StarCluster:

1. Save a custom plugin
2. Configure the plugin in your config
3. Add the plugin to your cluster stanza

First, save this custom plugin, which we call tagger, to ``$HOME/.starcluster/plugins/tagger.py``

{{< highlight python3 >}}
# Install this file to $HOME/.starcluster/plugins/tagger.py or somewhere on your $PYTHONPATH
from starcluster.clustersetup import ClusterSetup
from starcluster.logger import log
  
class TaggerPlugin(ClusterSetup):
    def __init__(self, tags):
        self.tags = eval(tags)
  
    def run(self, nodes, master, user, user_shell, volumes):
        log.info("Tagging all nodes...")
        for tag in self.tags:
            val = self.tags.get(tag)
            log.info("Applying tag - {0}: {1}".format(tag, val))
            for node in nodes:
                node.add_tag(tag, val)
 
    def on_add_node(self, node, nodes, master, user, user_shell, volumes):
        log.info("Tagging new node...")
        for tag in self.tags:
            val = self.tags.get(tag)
            log.info("Applying tag - {0}: {1}".format(tag, val))
            node.add_tag(tag, val)
{{< / highlight >}}

Second, at the bottom of your StarCluster configuration (typically ``$HOME/.starcluster/config``)
define the tags you want to attach. Take care in picking your tags, you
want everyone using the same tag key/values.  

{{< highlight ini >}}
[plugin tagger]
setup_class = tagger.TaggerPlugin
tags = {'owner':'craig', 'dept':'development'}
{{< / highlight >}}
  
Finally, get your cluster to call the new plugin, by editing your
cluster stanza:  

{{< highlight ini >}}
[cluster smallcluster]
# Various other settings... 
# Enable the following plugins</span>  
PLUGINS = tagger 
{{< / highlight >}}
  
Now when you launch your next cluster you will see a few extra lines in
the output confirming tagger has run and you can check on the AWS
Management console that EC2 instances and ELB volumes are now tagged.  
  
[^1]: It is not possible to tag every resource or the resource is shared so how do you split the cost? The actual cost will likely be higher than just the resources you tag.