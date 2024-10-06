My personal website and blog - https://craigbruce.me

Static web pages powered by Hugo built using AWS CodePipeline and deployed via S3 & CloudFront.

### Development

```
$ git clone https://github.com/craigbruce/craigbruce.me.git
$ cd craigbruce.me
$ hugo server
# View at http://localhost:1313/
```

#### Update theme

```
$ cd themes/hugo-coder
$ git fetch
$ git merge origin/main
$ cd ../..
# commit the change themes/hugo-coder
``` 