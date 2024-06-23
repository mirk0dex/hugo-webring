# hugo-webring
An easy-to-use hugo module to add a personal webring to your website. It generates static html without javascript.

The original (by [infopunk (formerly
rikvanloenhout)](https://github.com/infopunk)) has been been modified to include
nil-checks, the lack of which was causing errors on my end. 

Inspired by [openring](https://sr.ht/~sircmpwn/openring/).

## Installation
Initialize the hugo module system ([Read more](https://gohugo.io/hugo-modules/use-modules/#use-a-module-for-a-theme)):
`hugo mod init github.com/<your_user>/<your_project>`

Add this to your hugo config file:
```
[module.imports]
path = 'github.com/mirk0dex/hugo-webring'
```

### Styling
You can either include the default stylesheet by adding `<link rel="stylesheet" href="/css/hugo-webring.css" />` to the `layouts/_default/baseof.html` or write your own style.

## Configuration
The partial expects the configuration to be passed as an argument:
```
...
</article>
<footer>
  {{ partial "webring" .Site.Params.webring }}
</footer>
```

And configure the partial in you hugo config file:
```
[params.webring]
title = "articles from other cool blogz"
feeds = [
  "https://lukesmith.xyz/rss.xml",
  "https://denshi.org/rss.xml",
  "https://blackdownsoundboy.blogspot.com/rss.xml"
]
```

## Updates
You can get update the plugin later by running:
`hugo mod get -u`
