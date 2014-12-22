# Vignette: Branch and Bound
  
  

<script type="text/javascript" src="js/jquery.min.js"></script>
<script type="text/javascript" src="js/jquery-ui.min.js"></script>
<script type="text/javascript" src="js/jquery.fancybox-1.3.4.pack.min.js"></script>
<script type="text/javascript" src="js/jquery.tocify.js"></script>
<script type="text/javascript" src="js/jquery.scianimator.min.js"></script>
<script type="text/javascript" src="js/page.js"></script>
<script>  </script>
<link type="text/css" rel="stylesheet" href="css/jquery.tocify.css" />
<link type="text/css" rel="stylesheet" media="screen" href="css/jquery.fancybox-1.3.4.css" />
<link type="text/css" rel="stylesheet" href="css/style.css"
<head> <div id="tableofcontents"></div> </head>
<div id="source" class="tocify"> 
<ul class="tocify-header nav nav-list">
<li class="tocify-item active" style="cursor: pointer;">
<a onclick='toggle_R();' >Show / Hide Source</a>
</li></ul>
</div>

__Kevin M. Smith // Environmental Statistics // Fall 2014__
<hr>

```r
library(knitr)
library(ggplot2)
library(xtable)
library(gridExtra)
library(pander)

opts_knit$set(fig.width = 10,
              xtable.type = 'html',
              warning = FALSE,
              cache = TRUE,
              dev = 'png')


options(xtable.comment = FALSE)
panderOptions('table.split.table', Inf)
```

# Overview
The purpose of this short note is to introduce the __branch and bound__ method for __exhaustive subsetting of predictor variables in multivariate linear regression__. Those familiar with _integer programming_ may be familiar with __branch and bound__ techniques. It was __Furnival and Wilson__

The algorithmic details of the __branch and bound__ procedure vary widely because of differing heuristics. This note will attempt to convey the basic 

itself will be left to the reader to explore (_see Furnival and Wilson_), but its assumptions and consequences will be discussed.

# Best Subsets Regression
Here we are concerned with estimating the mean of the vector $y = X\beta + \epsilon$ where $X$ is a $n$ by $p$ design matrix. In general, increasing $p$ (the number of predictors) relative to $n$ (the number of observations) will reduce the residual sum of squares, $RSS = \sum_i^n (y_i - \hat{y})$ and increase the coefficient of determination $R^2$. As a definitional consequence of linear regression __RSS will never increase__ and __the $R^2$ never decrease__ with an additional predictor $X_{p+1}$, regardless of wheter or not the new predictor $X_{p+1}$ is a cuasal driver of $y$ or just random noise. 

#

