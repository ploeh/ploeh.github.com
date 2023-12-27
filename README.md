# ploeh blog

This repository contains the templates and data for my blog at [blog.ploeh.dk](https://blog.ploeh.dk). It is powered by [Jekyll-Bootstrap](http://jekyllbootstrap.com).

## Comments

Comments for a particular post are kept as part of the post itself.

If you wish to comment on a particular post, send me a pull request for that post. If you're in doubt about the format, just look at how previous comments are formatted. For an example of a post with comments, see e.g. [the very first post on this blog](/_posts/2009-01-28-LivingInInterestingTimes.html).

If you're using [Visual Studio Code](https://code.visualstudio.com/), you may use this [code snippet](https://code.visualstudio.com/docs/editor/userdefinedsnippets) if you like:

```
"Add comment": {
	"prefix": "addcomment",
	"body": ["<div class=\"comment\" id=\"${1:guid}\">",
		"\t<div class=\"comment-author\"><a href=\"${2:url}\">${3:name}</a> <a href=\"#$1\">#</a></div>",
		"\t<div class=\"comment-content\">",
		"\t</div>",
		"\t<div class=\"comment-date\">$CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE ${4:hour}:$CURRENT_MINUTE UTC</div>",
	"</div>"],
	"description": "Adds a single comment, but not the surrounding divs that separate the comment section from the main article. This, you should add yourself. The snippet makes a guess at the current date and time, but you should check it, particularly around midnight. Also, be sure to check the minutes if you're in a time zone not hour-aligned to UTC. The time should be in UTC."
}
```

If you only wish to comment, you don't have to read on, but if you're curious, here follows some background.

Why is the comment system implemented this way? Partly, it's for historical reasons, but increasingly, it's also for longevity reasons.

### Legacy

From its inception in 2009 to 2013 the blog ran on blogging software called *dasBlog*, which had its own comment system. When I decided to [migrate to Jekyll](https://blog.ploeh.dk/2013/03/03/moving-the-blog-to-jekyll), I had to figure out what to do with the existing comments.

While it would have been easier to ignore the existing comments, I felt an obligation to the readers who had engaged with the blog. Throwing the comments away didn't seem like a proper course of action.

The most popular comment system at the time was Disqus, and I did investigate whether I could import the existing comments into that system. It did strike me as a bit proprietary, though, which made me reflect further on the problem. Migrating the comments to Disqus would effectively trap them there. Would I be able to get them out again if I decided to migrate to yet another system?

Thus, I decided (at first, as an experiment) to embed the comments directly in the article. It's not ideal, but the trade-off I've identified.

### Longevity

The web site at https://blog.ploeh.dk is the second blog I've authored. Before it, I wrote [a blog on MSDN](http://blogs.msdn.com/ploeh). When I stopped at Microsoft, I could no longer update it, which I found less than ideal.

When I started this incarnation of *ploeh blog*, having full control of the entire life cycle of it was a major priority. For the first four years, I ran the blog off a server in my home office. Before moving to Jekyll and GitHub pages, I specifically investigated whether that would lock me into GitHub, either technically or legally. That, fortunately, turned out not to be an issue.

Including the comments in the source code for the blog minimises dependencies on other systems. Should I need to move the blog to another platform in the future, the comments are right here, along with everything else.

I find it telling that since I migrated to Jekyll, Disqus is no longer the leading comment platform. What else will come and go?

*ploeh blog* has been around since 2009. Ponder the time involved. Services come and go, but I'm here for the long haul. I plan to do this for many more years, and I don't want to take a dependency on something that may become a problem in the future.

That means every third-party comment platform, *including GitHub*.

Readers occasionally write to suggest some service based on GitHub issues or the like. GitHub may last for a long time, but who knows about the code that drives such integration? And even a dependency on GitHub is not something I'm keen to accept.

GitHub is only a host and a publishing channel for the blog. The web site runs perfectly well on my laptop as well. It'll run fine somewhere else, too. After all, it's just static HTML files.

My time perspective is measured in *decades*. Few things last that long in software, so I'm taking a conservative stance.

## Contributions

While *ploeh blog* is my personal blog, I'm happy to accept contributions such as:

* Comments (see above)
* Corrections of typos and the like
* Look and feel enhancements (better CSS, etc.)

On the other hand, I don't intend to turn *ploeh blog* into a site with 'guest bloggers', so don't bother sending an unsolicited pull request for a completely new post.
