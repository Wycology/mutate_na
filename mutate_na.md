<center>
<font aspan size = '6'>Mutating a column in data frame with some NA
values</font>
</center>
================
<center>
Wyclife Agumba Oluoch <wyclifeoluoch@gmail.com>
</center>
<center>
2021-09-06 15:04:35
</center>

# Introduction

In this short article I demonstrate how to mutate a column in a data
frame with some NA values so that cases where value is NA are assigned
some ‘real’ values (not NAs). I am doing this because it gave me some
hard time and later I got a way out.

# The code

``` r
x <- data.frame(column = c(1:5, NA, 9, NA, 14, NA))
x_mutated <- x |> mutate(mutated = case_when(column <= 5 ~ 'Small', column > 5 ~ 'Big', column |> is.na() ~ 'This is NA'))
kable(x_mutated)
```

| column | mutated    |
|-------:|:-----------|
|      1 | Small      |
|      2 | Small      |
|      3 | Small      |
|      4 | Small      |
|      5 | Small      |
|     NA | This is NA |
|      9 | Big        |
|     NA | This is NA |
|     14 | Big        |
|     NA | This is NA |

# References

<div id="refs" class="references csl-bib-body hanging-indent">

<div id="ref-R-rmarkdown" class="csl-entry">

Allaire, JJ, Yihui Xie, Jonathan McPherson, Javier Luraschi, Kevin
Ushey, Aron Atkins, Hadley Wickham, Joe Cheng, Winston Chang, and
Richard Iannone. 2021. *Rmarkdown: Dynamic Documents for r*.
<https://CRAN.R-project.org/package=rmarkdown>.

</div>

<div id="ref-R-base" class="csl-entry">

R Core Team. 2021. *R: A Language and Environment for Statistical
Computing*. Vienna, Austria: R Foundation for Statistical Computing.
<https://www.R-project.org/>.

</div>

<div id="ref-R-dplyr" class="csl-entry">

Wickham, Hadley, Romain François, Lionel Henry, and Kirill Müller. 2021.
*Dplyr: A Grammar of Data Manipulation*.
<https://CRAN.R-project.org/package=dplyr>.

</div>

<div id="ref-knitr2014" class="csl-entry">

Xie, Yihui. 2014. “Knitr: A Comprehensive Tool for Reproducible Research
in R.” In *Implementing Reproducible Computational Research*, edited by
Victoria Stodden, Friedrich Leisch, and Roger D. Peng. Chapman;
Hall/CRC. <http://www.crcpress.com/product/isbn/9781466561595>.

</div>

<div id="ref-knitr2015" class="csl-entry">

———. 2015. *Dynamic Documents with R and Knitr*. 2nd ed. Boca Raton,
Florida: Chapman; Hall/CRC. <https://yihui.org/knitr/>.

</div>

<div id="ref-R-knitr" class="csl-entry">

———. 2021. *Knitr: A General-Purpose Package for Dynamic Report
Generation in r*. <https://yihui.org/knitr/>.

</div>

<div id="ref-rmarkdown2018" class="csl-entry">

Xie, Yihui, J. J. Allaire, and Garrett Grolemund. 2018. *R Markdown: The
Definitive Guide*. Boca Raton, Florida: Chapman; Hall/CRC.
<https://bookdown.org/yihui/rmarkdown>.

</div>

<div id="ref-rmarkdown2020" class="csl-entry">

Xie, Yihui, Christophe Dervieux, and Emily Riederer. 2020. *R Markdown
Cookbook*. Boca Raton, Florida: Chapman; Hall/CRC.
<https://bookdown.org/yihui/rmarkdown-cookbook>.

</div>

</div>
