# hugo-webring
An easy-to-use hugo module to add a personal webring to your website. It generates static html without javascript.

Inspired by [openring](https://sr.ht/~sircmpwn/openring/).

## Installation
Initialize the hugo module system ([Read more](https://gohugo.io/hugo-modules/use-modules/#use-a-module-for-a-theme)):
`hugo mod init github.com/<your_user>/<your_project>`

Add this to your hugo config file:
```
[module.imports]
path = 'github.com/rikvanloenhout/hugo-webring'
```

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
title = "More interesting posts"
feeds = [
  "https://drewdevault.com/feed.xml",
  "https://emersion.fr/blog/rss.xml",
  "https://100r.co/links/rss.xml"
]
```

## Updates
You can get update the plugin later by running:
`hugo mod get -u`