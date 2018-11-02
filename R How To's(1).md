

# R How To's

All content was derived from personal experience, and R documentation of the packages used.

## Table of contents

1. [R Syntax](#r-syntax)
	1. [How to write a for loop?](#how-to-write-a-for-loop)
	2. [How to force a side effect?](#how-to-force-a-side-effect)
2. [Lists](#lists)
	1. [How to create a list of repeated values?](#how-to-create-a-list-of-repeated-values)
	2. [How to create a linearly spaced list?](#how-to-create-a-linearly-spaced-list)
4. [Strings](#strings)
	1. [How to get the substring before a particular separator ?](#how-to-get-the-substring-before-a-particular-separator)
5. [Explore dataframes](#explore-dataframes)
	1. [How to get the index of a row that has a value on an injective column?](#how-to-get-the-index-of-a-row-that-has-a-value-on-an-injective-column)
	2. [How to get the column names?](#how-to-get-the-column-names)
	3. [How to get the number of rows?](#how-to-get-the-number-of-rows)
6. [Edit dataframes](#edit-dataframes)
	1. [How to split a character column into two separate columns with separator ‘sep’ in a data frame?](#how-to-split-a-character-column-into-two-separate-columns-with-separator-in-a-data-frame)
	2. [How to delete a column in a dataframe?](#how-to-delete-a-column-in-a-dataframe)
	3. [How to cast a character column to a numeric one?](#how-to-cast-a-character-column-to-a-numeric-one)
	4. [How to filter the data?](#how-to-filter-the-data)
	5. [How to cast a variable to a factor?](#how-to-cast-a-variable-to-a-factor)
	6. [How to coerce a dataframe to a tibble?](#how-to-coerce-a-dataframe-to-a-tibble)
	7. [How to replace a value in all columns of a dataframe by another?](#how-to-replace-a-value-in-all-columns-of-a-dataframe-by-another)
	8. [How to create a count dataframe counting the frequency of combinations of categorical variables?](#how-to-create-a-count-dataframe-counting-the-frequency-of-combinations-of-categorical-variables)
	9. [How to copy a dataframe?](#how-to-copy-a-dataframe)
	10. [How to apply a custom function to change values in a column?](#how-to-apply-a-custom-function-to-change-values-in-a-column) 
	11. [How to change the order of levels in a factor column?](#how-to-change-the-order-of-levels-in-a-factor-column)
	12. [How to create a tibble?](#how-to-create-a-tibble?)
	13. [How to create a tibble from columns of an existing tibble?](#how-to-create-a-tibble-from-columns-of-an-existing-tibble)
	14. [How to sort a dataframe on one column?](#how-to-sort-a-dataframe-on-one-column)
7. [Plotting data](#plotting-data)
	1. [How to plot a histogram?](#how-to-plot-a-histogram)
	2. [How to facet a histogram on two variables?](#how-to-facet-a-histogram-on-two-variables)
	3. [How to plot a cumulative frequency histogram?](#how-to-plot-a-cumulative-frequency-histogram)
	4. [How to manually set bins in a histogram?](#how-to-manually-set-bins-in-a-histogram)
	5. [How to change the binwidth of a histogram interactively?](#how-to-change-the-binwidth-of-a-histogram-interactively)
	6. [How to make a scatterplot?](#how-to-make-a-scatterplot)
	7. [How to plot a bar chart?](#how-to-plot-a-bar-chart)
	8. [How to make a scatterplot matrix?](#how-to-make-a-scatterplot-matrix)
	9. [How to plot a vertical line?](#how-to-plot-a-vertical-line)
	10. [How to add a density curve to a histogram?](#how-to-add-a-density-curve-to-a-histogram)
	11. [How to make a boxplot?](#how-to-make-a-boxplot)
	12. [How to make a variable width boxplot?](#how-to-make-a-variable-width-boxplot)
	13. [How to add a density to a scatterplot?](#how-to-add-a-density-to-a-scatterplot) 
	14. [How to add a smooth to a scatterplot?](#how-to-add-a-smooth-to-a-scatterplot)
	15. [How to plot a line?](#how-to-plot-a-line)
	16. [How to make a parallel coordinate plot?](#﻿﻿how-to-make-a-parallel-coordinate-plot)
	17. [How to add alpha-blending to a pcp?](#how-to-add-alpha-blending-to-a-pcp)
	18. [How to group on a pcp?](#how-to-group-on-a-pcp)
	19. [How to remove labels and variable names on the y-axis?](#how-to-remove-labels-and-variable-names-on-the-y-axis)
	20. [How to plot a bar chart with count column?](#how-to-plot-a-bar-chart-with-count-column)
	21. [How to make a mosaicplot?](#how-to-make-a-mosaicplot)
	22. [How to see how a particular value of a dependent variable is found across other categorical variables?](#how-to-see-how-a-particular-value-of-a-dependent-variable-is-found-across-other-categorical-variables)
	23. [How to set the x-axis ticks for a continuous variable?](#how-to-set-the-x-axis-ticks-for-a-continuous-variable)
8. [Modeling](#modeling)
	1. [How to fit a linear model?](#how-to-fit-a-linear-model)


## R Syntax

#### How to write a for loop?
```
for (i in 2010:2015){
 
}
```

#### How to force a side effect?
`global_var <<- new_value`

## Lists

#### How to create a list of repeated values?
`rep(values, each = n)`

#### How to create a linearly spaced list?
`seq(a, b, c)`
will be `c(a, a + c, a + 2c...)`

## Strings

#### How to get the substring before a particular separator?
Using `stringr`
`word(string, sep = “sepa”)`

## Explore dataframes

#### How to get the index of a row that has a value on an injective column?
`df[which(df$col == value), ]`

#### How to get the column names?
`colnames(df)`

#### How to get the number of rows?
`nrow(df)`

## Edit dataframes

#### How to split a character column into two separate columns with separator in a data frame?
Using `tidyr`
`separate(data, col, into, sep = "", remove = TRUE)`

#### How to delete a column in a dataframe?
Using `dyplr`
`data %>% select (-c(col1, col2))`

#### How to cast a character column to a numeric one?
`data$col <- as.numeric(data$col)`

#### How to filter the data?
`filter(data, var > threshold)`
or
```
library(dplyr)
df <- df %<% filter(condition1, condition2,..)
```

#### How to cast a variable to a factor?
`factor(data)`

#### How to coerce a dataframe to a tibble?
`df <- as_tibble(df)`

#### How to replace a value in all columns of a dataframe by another?
`df[df == value] <- new_value`

#### How to create a count dataframe counting the frequency of combinations of categorical variables?
`counts <- as_tibble(data)[, categorical_vars] %>% group_by(categorical_vars) %>% 
    summarize(Freq = n())`

#### How to copy a dataframe?
`data.frame(df)`

#### How to apply a custom function to change values in a column?
```
f <- function(x) {...}
df$col <- sapply(df$col, f)
```

#### How to change the order of levels in a factor column?
`x =  factor(x, levels(x)[c(4,5,1:3)])`

#### How to create a tibble?
```
library(tibble)
tibble(x = 1:4, y = col)
```

#### How to create a tibble from columns of an existing tibble?
`bind_cols(t[,1],t[,3])`

#### How to sort a dataframe on one column?
```
library(dplyr)
df <- df %>% arrange(desc(col_name))
```

#### How to create a column from other columns?
```
library(dplyr)
df <- df %>% mutate(new_col = f(existing_cols))
```

## Plotting data
Using `tidyverse`

#### How to plot a histogram?
`ggplot(data, aes(x = numerical_var, fill = categorical_var)) + xlim(lim_inf, lim_sup) + geom_histogram(binwidth = bin_width, fill = "mediumpurple", center = center_value_for_one_of_the_bins) + xlab("labelx") + facet_wrap(~categorical_var2, ncol = 1) + ylab("")`

#### How to facet a histogram on two variables?
`ggplot(data, aes(numerical_var)) + geom_histogram() + facet_grid(categorical_var1 ~ categorical_var2)`

#### How to plot a cumulative frequency histogram?
`ggplot(df, aes(x = numerical_var)) + geom_histogram(aes(y = cumsun(..count..)), color = "blue", fill = "lighblue")`
where `color` is the color of the edges of the rectangles and `fill` is the color filling the columns

#### How to manually set bins in a histogram?
`geom_histogram(breaks = seq(30,110,10))`

#### How to change the binwidth of a histogram interactively?
```
library(tidyverse)
library(ggvis)
df %>% ggvis(~numerical_var) %>% 
	layer_histograms(fill := "lightblue",
			 width = input_slider(0.1, 2, value = .1, step = .1, label = "width"),
			 center = input_slider(min, max, value = starting_value, step = step, label = "center"))
```

#### How to make a scatterplot?
`ggplot(data, aes(numerical_var1, numerical_var2, color = categorical_var)) + geom_point() + theme(legend.position = "bottom") + scale_colour_colorblind()`

#### How to plot a bar chart?
`ggplot(data, aes(categorical_var)) + geom_bar(aes(weight = Freq))`

#### How to make a scatterplot matrix?
```
library(GGally)
ggpairs(data, title = "title", diag = list(continuous = 'density'), axisLabels = 'show')
```
or `axisLabels = 'none'`
#### How to plot a vertical line?
`ggplot(data, aes(x)) + geom_vline(xintercept = median(data$x), col = "red")`

#### How to add a density curve to a histogram?
`ggplot(data, aes(numerical_var)) + geom_histogram(aes(y = ..density..)) + geom_density() + ggtitle("title")`

#### How to make a boxplot?
`ggplot(data, aes("var", numerical_var)) + geom_boxplot() + scale_x_discrete(breaks = NULL) + coord_flip()`
where `"var"` is a dummy variable

####  How to make a variable width boxplot?
`ggplot(data, aes(categorical_var, numerical_var)) + geom_boxplot(varwidth = TRUE)`

#### How to add a density to a scatterplot?
`ggplot(data, aes(x, y)) + geom_point() + geom_density2d()`

#### How to add a smooth to a scatterplot?
`ggplot(data, aes(x, y)) + geom_point() + geom_smooth(colour = "green")`

#### How to plot a line?
`geom_abline(slope = 1, intercept = 0)`

#### How to make a parallel coordinate plot?
`ggparcoord(data = d, columns = c(1:3), scale = "uniminmax")`

or `scale = "globalminmax"`

#### How to add alpha-blending to a pcp?
`ggparcoord(data = d, columns = c(1:3), scale = "uniminmax", alphaLines = 0.2)`

#### How to group on a pcp?
`ggparcoord(data = d[order(d$var1),], columns = c(1:3,6), groupColumn = "var1", scale = "uniminmax") + theme(legend.position = "none")`

#### How to remove labels and variable names on the y-axis?
`... + theme(axis.ticks.y = element_blank(), axis.text.y = element_blank())`

#### How to plot a bar chart with count column?
`geom_bar()` makes the height of the bar proportional to the number of cases in each group while with `geom_col()` the heights of the bars represents values in the data

`ggplot(data, aes(categories_names, count_column)) + geom_col()`

Another way to do it is:
`ggplot(data, aes(x = categories_names, y = count_column)) + geom_bar(stat = "identity")`

#### How to make a mosaicplot?
```
library(vcd)
mosaic(dependent_var ~ categorical_var1 + categorical_var2, data = df, direction = c("v", "v", "h"))
```
where `direction` is the succession of cuts, either `v` (vertical) or `h` (horizontal)

#### How to see how a particular value of a dependent variable is found across other categorical variables?
Make a mosaic plot and fill the values you don't care for in the same color:
```
library(vc)
library(grid)
mosaic(dependent_var ~ categorical_var1 + categorical_var2, data = df, direction = c("v", "v", "h"), gp = gpar(fill = c("grey", "grey", "grey", "red", "grey")))
```
where we are interested in the 4th value of `dependent_var`

#### How to set the x-axis ticks for a continuous variable?
`ggplot(df, aes(x = numerical_var)) + ... + scale_x_continuous(breaks = seq(30,60,10))`
Here ticks will be at `40, 50, 60`

## Modeling

#### How to fit a linear model?
`lm(formula, data)`





