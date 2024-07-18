# 4. Visualization

## Visualization Basics 

As you discovered towards the end of [Statistical Thinking](3-statistical-thinking.md), data visualization is about communication. Data relationships are translated to a **visual representation.** This visual representation is how we perceive and rationalize the mathematical relationships that exist between data points. 

1. Visualization accomplishes a goal
   - Exploration of existing data to uncover new insights and learning
   - strengthen arguments and key concepts with visual aid
   - share a data-driven idea

    
2. (Chart/Graph) design decisions can help or hinder how effectively visualizations communicate the features of the data.
   - chart type
   - color
   - labeling / annotation
   - context

```text
Tricks for remembering X/Y in a Cartesian plane. 

    X-axis looks like a person doing jumping jacks on the ground 
    (i.e. a horizontal plane) 
    
    Y-axis... if you cut it in half, the top of a "Y" is a V for "vertical"
```
### Data Types / Charts

This section is intended to just be a "taste" to charts and visualization. 
There are dozens of chart types and styles. [Matplotlib Charts](https://matplotlib.org/stable/gallery/index) and [Seaborn Charts](https://seaborn.pydata.org/examples/index.html) provide a good amount of examples. 

More than one possible chart can be used to describe a dataset, however different types of charts emphasize different questions, arguments or relationships between variables. 

Below is a quick table for some common/basic problem-to-chart relationships, followed by an example of each. 

| Problem | Chart Type |
| --- | --- | 
| Changes over time | Line / Bar Charts | 
| Part-whole relationships / proportions | Pie Charts | 
| Distribution / spread of data points in a single variable | Histogram | 
| Direct comparison of two variables to understand trends | Scatterplot | 

_Line Chart (Seaborn)_

![lineplots.png](img/lineplots.png)


_Bar Charts (Seaborn)_

![grouped_barplot.png](img/grouped_barplot.png)


_Pie Charts (Jaspersoft)_

![pie.svg](img/pie.svg)

_Histogram (Seaborn)_

![histogram.png](img/histogram.png)


_Scatterplot (Seaborn)_

![scatterplot.png](img/scatterplot.png)



As mentioned, there are dozens of types of charts and graphs. Play around with them. Look for well-scrutinized _scientific_ examples of the charts being demonstrated in order to learn how to use them. This is one case where using Google can do more harm than good. Many folks select graphs for aesthetic reasons (they like the graph) without a
good understanding of how the visualization might be perceived. 

----

### Univariate Charts

These are charts that measure a single variable. Charts of this nature are typically solving questions of **quantity** or **frequency**. We break this down into 2 categories. 

1. Counts
2. Distributions

#### Counts

A bar graph is one of the most popular charts to answer questions of "how much/how many". Differences in quantity are translated into a difference in bar height. 

![grouped_barplot.png](img/grouped_barplot.png)


#### Distributions

These measure the distribution or spread of a single variable. This measures "normalcy" vs. "skew" of distributions.
(Remember this from [Statistical Thinking](3-statistical-thinking.md)?). They answer questions such as "how does the frequency of a value of a variable vary across the set of bins in that variable?" For instance, shoe size across a population, or parts per assembly, or users per service. 


##### Histograms

Distributions are most frequently visualized using histograms. 

![histogram.png](img/histogram.png)

The two primary characteristics of a histogram are: 

1. **Bins**: (The x-axis / horizontal axis) Which represents an observed value of a variable in a set. 
2. **Frequency**: (The y-axis / horizontal axis) which represents the count or number of occurrences that the observed value has occurred for a variable in the set. 

Histograms and bar charts appear to be very similar, however the difference is the type of variable being plotted
on the X-axis. 
- Bar Charts are typically used for **discrete** numerical variables or categorical variables. 
- Histograms are typically used for **continuous** datasets that plot a range of data. 

While these trends aren't strict requirements, histograms generally assume continuous values along the x-axis, because
the fundamentals of a normal distribution or skewed distributions are predicated on similarly distanced intervals between
data points along the horizontal (x) axis. Edge cases exist, but they should be evaluated with judicious skepticism!


##### Density curve

A density curve is a similar to a histogram without the data bins. If you were to draw a line along the top of a histogram, you end up with the density curve. 

This is an analog or functional mathematical representation of a histogram, where the bins might represent the approximating rectangles / quantization of that mathematical function. 

Density curves provide a better indication or summary of data shape, but with less precision and substance than histograms. 

_Paired density and scatterplot matrix_

![pair_grid_with_kde.png](img/pair_grid_with_kde.png)

One of the primary advantages of a density curve is its simplicity. It's rarely used on its own, but given the lack of features and contours, it is easy to include in complex visual matrices to provide the same general information as a
histogram, coupled with other types of information. 

##### Box Plot (a.k.a. Box and Whiskers)

A box plot is a "mathematical" plot for showing distributions. It's also a bit of a swiss-army knife, because it conveys many features of the data. 


![horizontal_boxplot.png](img/horizontal_boxplot.png)

Most box plots don't show the ticks, but it can be helpful to see the overlay. 

The **box** represents the **IQR (interquartile range)** of the variable. 

The line inside the box (usually in the middle!) is the **median**. 

The end lines or (whiskers) of the plot represent the min and max values of the data set. 

Some visualizations might show ticks outside the boxplot's endlines. These are omitted outliers. 

##### Violin Plots (a.k.a. KDE - Kernel Density Estimates)

A violin plot is similar to a box plot, but the features are varied. It usually represents a comparison of one or more density curves (shaded). 

Given the rich dimensionality of the visualization these plots tend be used in multivariate distribution comparisons. 

![kde.png](img/kde.png)

As you can see above, KDE can include a box plot, the features of the box plot or various other forms of visualization to help present features of the graph. 

The ability to overlay additional types of graphs onto the violin plot is considered one of it's most valuable characteristics. 

----

#### Multivariate Charts

These charts are used to present two or more variables. 