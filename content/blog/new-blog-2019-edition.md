---
title: "New Blog 2019 edition"
date: 2019-03-24T10:23:50-07:00
---

After quite a break I've moved my blog off [Blogger](http://cheminsilico.blogspot.com) and wanted a static site instead. I did most of the work to convert to [Jekyll](https://jekyllrb.com) and [GitHub pages](https://pages.github.com). However, I like building things myself so wanted to use AWS tools to host instead and I don't use Ruby so opted for [Hugo](https://gohugo.io) instead so I don't have to setup Ruby environments.

Now I have the following flow:

1. Commit changes to GitHub.
2. AWS CodePipeline is watching for changes. Once detected it will use CodeBuild to build the site and then deploy to S3. 
3. You'll actually consume the site via CloudFront and ACM for TLS happiness.

I'll post my about the actual details of my setup in the future.