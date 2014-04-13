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
This is just a test :)

# Primer uporabe knitr
## Author: A. Blejec

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


{% highlight r %}
library("Hmisc")
{% endhighlight %}



{% highlight text %}
## Warning: package 'Hmisc' was built under R version 3.0.3
{% endhighlight %}



{% highlight text %}
## Loading required package: grid
## Loading required package: lattice
{% endhighlight %}



{% highlight text %}
## Warning: package 'lattice' was built under R version 3.0.3
{% endhighlight %}



{% highlight text %}
## Loading required package: survival
## Loading required package: splines
## Loading required package: Formula
## 
## Attaching package: 'Hmisc'
## 
## The following objects are masked from 'package:base':
## 
##     format.pval, round.POSIXt, trunc.POSIXt, units
{% endhighlight %}



{% highlight r %}
tbl <- table(letters[round(runif(100, 1, 3))], LETTERS[round(runif(100, 1, 3))])
tbl
{% endhighlight %}



{% highlight text %}
##    
##      A  B  C
##   a  4  7  2
##   b 10 34 15
##   c  6 16  6
{% endhighlight %}

Tabele lahko izpiše tudi \LaTeX:

{% highlight r %}
latex(tbl, file = "", where = "!htbp", caption = "Poskusna tabela")
{% endhighlight %}

%latex.default(tbl, file = "", where = "!htbp", caption = "Poskusna tabela")%
\begin{table}[!htbp]
\caption{Poskusna tabela\label{tbl}} 
\begin{center}
\begin{tabular}{lrrr}
\hline\hline
\multicolumn{1}{l}{tbl}&\multicolumn{1}{c}{A}&\multicolumn{1}{c}{B}&\multicolumn{1}{c}{C}\tabularnewline
\hline
a&$ 4$&$ 7$&$ 2$\tabularnewline
b&$10$&$34$&$15$\tabularnewline
c&$ 6$&$16$&$ 6$\tabularnewline
\hline
\end{tabular}\end{center}\end{table}


## Zakljucek

Sweave je zakon!

