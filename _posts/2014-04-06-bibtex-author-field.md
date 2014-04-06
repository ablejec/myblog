---
layout: post
title: BibTeX author filed converter
categories:
- R language
- LaTeX
tags:
- BibTeX
- LaTeX
- R code
---

I am organizing my BibTeX files with Jabref. For Jabref the proper syntax for the author field for multiple authors is `Last1, First1 and Last2, First2` (and delimited). Often the list of authors is composed as `First1 Last1, First2 Last2` (comma delimited).

The code below helps to change 'comma' delimted list of authors into 'and' delimited list of authors:

{% highlight r %}
fl2lf <- function(x){
	if(missing(x)) x <- read.table(file="clipboard",sep="??")
	x1=strsplit(x," *, *")[[1]]
	x2=sapply(x1,function(x) gsub("^(.*) (.*)$","\\2, \\1",x))
	x3=paste(x2,collapse=" and ")
	return(x3)
}
{% endhighlight %}

{% highlight r %}
x <- "Tim Horton, Tom Orton , Tam   Hortan,Tem Horten"
fl2lf(x)
# [1] "Horton, Tim and Orton, Tom and Hortan, Tam   and Horten, Tem"
{% endhighlight %}

The function is quite forgiving to the number of spaces around commas.

