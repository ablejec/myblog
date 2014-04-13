---
layout: post
title: Primer uporabe knitr
categories:
- R language
- markdown
- how-to
- test
tags:
- R code
- how-to
---
# Primer uporabe knitr
## Author: A. Blejec
This is Just a test :)

## Abstract
Poskusna datoteka za uporabo Sweave: povezava \R\ in \LaTeX.

## Racunanje

Poskus racunanja


{% highlight r %}
require(knitr)
render_jekyll()
opts_chunk$set(fig.path = ".", concordance = TRUE, tidy = TRUE)
opts_chunk$get()$results
{% endhighlight %}



{% highlight text %}
## [1] "markup"
{% endhighlight %}



{% highlight r %}
2 + 2
{% endhighlight %}



{% highlight text %}
## [1] 4
{% endhighlight %}


## Risanje

Malo risanja:

{% highlight r %}
hist(rnorm(100), col = "lightblue")  # slika
{% endhighlight %}

![plot of chunk unnamed-chunk-3](_unnamed-chunk-3.png) 


## Uporaba vrednosti v besedilu

Primerjava dveh porazdelitev (\R\ ukazi so skriti)


{% highlight text %}
## 
## 	Welch Two Sample t-test
## 
## data:  x and y
## t = 3.14, df = 57.79, p-value = 0.00266
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##   2.738 12.366
## sample estimates:
## mean of x mean of y 
##     97.04     89.48
{% endhighlight %}


Vrednosti iz \R\ objektov lahko uporabimo v besedilu.
Na primer:\\ Verjetnost $p=0.003$.

## Tabele

Za pripravo **tabel** z \LaTeX\ je prirocno namestiti paket \texttt{Hmisc}

## Zakljucek

Sweave je zakon!

