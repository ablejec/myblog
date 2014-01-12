---
layout: post
title: Tidy up your R code
categories:
- R language
tags:
- parse()
- R code
---

Years ago I wrote a WinEdt script to tidy up a R source. I was not happy with loss of comments in the R obvious solutions at that time. This is a reminder for a [Jihui Xie blog post](http://yihui.name/en/2007/08/tidy-up-your-r-code/)  about this question. Here is, what he is using:

{% highlight r %}
tidy.source = function(file = choose.files()) {
   exprs = parse(file)
   for (i in 1:length(exprs)) {
       dep = paste(deparse(exprs[i]), collapse = "\n")
       dep = substring(dep, 12, nchar(dep) - 1)
       cat(dep, "\n")
   }
}
{% endhighlight %}

