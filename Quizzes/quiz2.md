Ryan Tillis - Exploratory Data Analysis- Data Science - Quiz 2 - Coursera
================
<a href="http://www.ryantillis.com"> Ryan Tillis </a>
July 8, 2016

Exploratory Data Analysis Quiz 2
--------------------------------

This is Quiz 1 from the Exploratory Data Analysis course within the Data Science Specialization on Coursera. Topics include sorting, matching, and aggregating data.

### Questions

<hr>
<font size="+2">1. </font> Under the lattice graphics system, what do the primary plotting functions like xyplot() and bwplot() return?

<hr>
<font size="+1"> <b>

-   an object of class "trellis"

</b> </font>

<hr>
<hr>
<font size="+2">2. </font> What is produced by the following code?

``` r
library(nlme)
library(lattice)
xyplot(weight ~ Time | Diet, BodyWeight)
```

![](quiz2_files/figure-markdown_github/Question%201-1.png)
<hr>
<font size="+1"> <b>

-   A set of 3 panels showing the relationship between weight and time for each diet.

</b> </font>

<hr>
<hr>
<font size="+2">3. </font> Annotation of plots in any plotting system involves adding points, lines, or text to the plot, in addition to customizing axis labels or adding titles. Different plotting systems have different sets of functions for annotating plots in this way.

Which of the following functions can be used to annotate the panels in a multi-panel lattice plot?

<hr>
<font size="+1"> <b>

-   panel.lmline()

</b> </font>

<hr>
<hr>
<font size="+2">4. </font> The following code does NOT result in a plot appearing on the screen device.

``` r
library(lattice)
library(datasets)
library(ggplot2)
data(airquality)
p <- xyplot(Ozone ~ Wind | factor(Month), data = airquality)
```

Which of the following is an explanation for why no plot appears?
<hr>
<font size="+1"> <b>

-   The object 'p' has not yet been printed with the appropriate print method.

</b> </font>

<hr>
<hr>
<font size="+2">5. </font> In the lattice system, which of the following functions can be used to finely control the appearance of all lattice plots?

<hr>
<font size="+1"> <b>

-   trellis.par.set()

</b> </font>

<hr>
<hr>
<font size="+2">6. </font> What is ggplot2 an implementation of?

<hr>
<font size="+1"> <b>

-   the Grammar of Graphics developed by Leland Wilkinson

</b> </font>

<hr>
<hr>
<font size="+2">7. </font> Load the \`airquality' dataset form the datasets package in R

``` r
library(datasets)
data(airquality)
```

I am interested in examining how the relationship between ozone and wind speed varies across each month. What would be the appropriate code to visualize that using ggplot2?

<hr>
<font size="+1"> <b>

``` r
airquality = transform(airquality, Month = factor(Month))
qplot(Wind, Ozone, data = airquality, facets = . ~ Month)
```

    ## Warning: Removed 37 rows containing missing values (geom_point).

![](quiz2_files/figure-markdown_github/answer-1.png)

</b> </font>

<hr>
<font size="+2">8. </font> What is a geom in the ggplot2 system?

<hr>
<font size="+1"> <b>

-   a plotting object like point, line, or other shape

</b> </font>

<hr>
<font size="+2">9. </font> When I run the following code I get an error:

``` r
library(ggplot2)
library(ggplot2movies)
g <- ggplot(movies, aes(votes, rating))
print(g)
```

I was expecting a scatterplot of 'votes' and 'rating' to appear. What's the problem?

<hr>
<font size="+1"> <b>

-   ggplot does not yet know what type of layer to add to the plot.

</b> </font>

<hr>
<font size="+2">10. </font> The following code creates a scatterplot of 'votes' and 'rating' from the movies dataset in the ggplot2 package. After loading the ggplot2 package with the library() function, I can run

``` r
qplot(votes, rating, data = movies)
```

How can I modify the the code above to add a smoother to the scatterplot?

<hr>
<font size="+1"> <b>

-   qplot(votes, rating, data = movies) + geom\_smooth()

</b> </font>

<hr>
See more at: <http://www.ryantillis.com/>

<hr>
