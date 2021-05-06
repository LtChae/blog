---
title: "Starting Out"
date: 2021-05-05T19:00:36-04:00
summary: Starting this blog on hugo
categories: 
- Development
tags:
- site
- design
- hugo
draft: false
---

I've needed a personal blog/portfolio for a long time now, but had never settled on a solution for it. I looked into WordPress, but found it too hand-holdy for what needed to be at least partly a technical blog. Ideally, what I'm doing here should serve not only as a creative outlet, but also as a professional resource.

I knew I wanted something that would be fast and lightweight. What annoys me the most about the modern web is the sheer volume of javascript packed into each and every page. That led me to the paradigm of static, pre-rendered sites.

I had looked into [Jekyll](https://jekyllrb.com/) before, but had not been impressed with its reliance on Ruby. Following that trail led me to [Hugo](https://gohugo.io/), built on Go.

Hugo is fast and simple, with the same feature set as Jekyll and more or less exactly what I needed. Compiled, even with the theme, it only comes out to 20kb of javascript. It won't win any awards for minimalism, but that's small enough to barely be noticed in a world of multi-mb websites.

Starting a whole new site is as easy as:
```sh
hugo new site quickstart
```

Adding an article as simple as:
```sh
hugo new posts/my-first-post.md
```

Directory structure informs site structure in Hugo. Their documentation states:
> Hugo assumes that the same structure that works to organize your source content is used to organize the rendered site.

This is exactly what I want.

Much of the magic of Hugo happens in what it calls "[Front Matter](https://gohugo.io/content-management/front-matter/)", a block of configuration and metadata at the top of each content file. This enables, among other things, tagging and categorization of articles.

The Front Matter for this article looks like this, for example. Notice the tags that appear at the bottom of the page automatically.
```yaml
---
title: "Starting Out"
date: 2021-05-05T19:00:36-04:00
summary: Starting this blog on hugo
categories: 
- Development
tags:
- site
- design
- hugo
draft: true
---
```

Content, like this article, is written in Markdown. I've worked in Markdown most of my career and even take personal notes in it. For anything Markdown can't handle, Hugo provides what it calls [Shortcodes](https://gohugo.io/content-management/shortcodes/). Shortcodes are chunks of Go templatting embedded in the Markdown, like this:

```go
{{</* figure src="http://placekitten.com/500/500" title="A Cat" caption="Image from [Placekitten](https://placekitten.com/)" */>}}
```

Which resolves to
{{< figure src="http://placekitten.com/500/500" title="A Cat" caption="Image from [Placekitten](https://placekitten.com/)" >}}

Go templates are also familiar to me due to extensive [Helm](https://helm.sh/) experience over the past few years.

For now, Hugo will serve my purposes well.