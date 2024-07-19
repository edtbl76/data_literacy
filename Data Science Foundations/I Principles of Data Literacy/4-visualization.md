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

![grouped_boxplot.png](img/grouped_boxplot.png)

Most box plots don't show the ticks, but it can be helpful to see the overlay. As you can see, boxplots can go left to right or up and down. There are volumes of books and blogs that discuss which is more appropriate. 

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

### Multivariate Charts

These charts are used to present two or more variables. 

#### Scatterplot

This is the "classic" bivariate visualization translating the relationship between two variables in the data to an intuitive spatial (ideally linear!) relationship. 


One variable is measured on each axis, and the data point represents a single observation. (You can think of the point as being the intersection of two columns from one row in a database.)

![different_scatter_variables.png](img/different_scatter_variables.png)

Scatterplots depend on the spatial relationship between variables. This means that as each variable increases or decreases, the values move accordingly up or down their respective axes. 

This makes it critical that at least one of the variables being measured is numerical. (Most use cases compare two numerical variables.)


#### Line Chart

A line chart is a bivariate chart that measures one variable against another. The second variable is most commonly time. (It's so common that old curmudgeons might refer to the line chart as a linear time chart)

![wide_data_lineplot.png](img/wide_data_lineplot.png)

Line charts are excellent at comparing multiple observations within the same variable. Another useful (but arguably complex) visualization is using different lines for different variables against a Y axis that represents a standardized scale. For instance, the Y axis could represent the values of a Beta (correlation) coefficient. 

This type of comparison is a common analysis performed in EDA (the other one!) when selecting variables for model training in machine learning. 

Evaluating the decay of correlation variables over time, compared to that of others is sometimes more important than a variable that appears strongly correlated at any given instant. 

A common mistake is to assume that having multiple lines makes a line chart a multivariate analysis. This is untrue. 
- Multiple observations of the same variable is still a single variable, such that the line chart can have multiple lines and remain a bivariate analysis. 
- Different variables depicted against a standardized axis allows the comparison of multiple variables, making the analysis (potentially) multivariate. 


---
## Aesthetics

The math is important, but it must be consumable. In order to communicate data visually, we manipulate several aesthetic properties or attributes: 
- position
- size
- shape
- color / pattern

![facebook.png](img/facebook.png)

Let's look at this example. The X axis measures time, and the Y axis measures the company value (in billions of dollars). The shape of the data is a circle, which is the same thing as a point on a graph, but size and color have been added to provide more dimensionality. The size of each circle tracks with the company value at IPO. Time is represented by color. Early points are red, the latest points are blue, and the intersection between the two is purple (right around 1995). The colors create a separate visualization of time scale by separating it into roughly 3 decades, while the ticks are every 5 years. This is a composite representation of information within the same variable. 

This isn't just aesthetic, it may convey specific meaning. 

As you look at the information, here, what else do you notice? 


### Information Redundancy

Yes. I kind of spoiled it by putting the answer right below the question. **Information redundancy** in data visualization is the deliberate encoding of the same information in different aesthetic visual properties. 

I already mentioned the multiple dimensions of the time axis. However, you might notice that both the size and height of the circle convey the same information. (I view them almost like balloons floating into the sky). 

Why would you do this? It's really simple. Your brain looks as this information and recognizes that there are multiple "arrows" (the properties) tied to the value on the y axis. This emphasis on visual categorization is a way to leverage information redundancy to help **key data points stand out.** (If you remember, this is one of the goals of visualization. Mission accomplished!)

Easy peasy right? Not so fast. 

### Audience Context. 

Different context is appropriate for different audiences. The same information can be presented to different audiences with charts that have very different titles and annotations. Experience directors and middle managers know this better than anyone, because they have to manage down to their direct reports and up to the executives on a regular basis. (So be nice to them, context switching is hard!)

Points to consider about audience: 
- What is the expertise of the audience? 
  - Are they laypersons? Academics? Professional Experts? 


- What kind of data are they looking for? 
  - do they want evidentiary data? ("Show me proof!")
  - are they looking for generative insights? ("tell me something I don't already know")


- What is their attention span? 
  - Age Group? 
  - Demographics? 
  - Personality types? 


- Is it a captive audience? 
  - Do they **have** to be there, or do they _want_ to be there? 


### Tips for Delivering Context

- Provide **necessary details**. Bridge the knowledge gap, but don't oversell unnecessary information. 
  - Too many presentations suffer from too much of "I want you to know how much I know" and too little of "I want to give you what you need to know."


- Tell a story with the data. 
  - provide enough additional information for the audience to reach an intuitive understanding. 
  - additional information should be **helpful** for the **specific** audience. Use it to ensure they're following along.


- Avoid the noise! Dump "Chart Junk"
  - excess graphics and annotations
  - general lines that don't contain useful information
  - be descriptive but brief. 


Many folks using charts for the first time go overboard with the visual toys. My suggestion is to get this out of your system on your own. Go play with the charts until it becomes ad nauseum. Once it starts to feel tedious and annoying, you've more than likely found the point that you can use them like tools and not like toys. 

----

## Accessibility Basics. 

These are some basic UX principles that are worth considering when building charts. I don't want to go too far down this path, but I think it's important to provide some context. 

### Color

Color is most often described by its **hue** (red, green, yellow etc.), however the **value** of that color is the magnitude of that color. (i.e. dark or light).

Good color comparisons use **high contrast values** not just different hues. 

Color sensitivity is often described as: 
- **protanomaly**: (reduced sensitivity to red light or "Red Weak")
- **deuteranomaly**: (reduced sensitivity to green light or "Green Weak")
- **tritanomaly**: (reduced sensitivity to blue light or "Blue Weak")

Deuteranomaly is the most common form of color sensitivity while tritanomaly is the rarest. These are often factors in selecting color palettes for UX design, and the same rules apply for selecting colors and visual presentations in data. 

Below are examples of good and bad color palettes. I like to call this "Skittles vs. L.L. Bean"


![accessible-palette.png](img/accessible-palette.png)


![bad-palette-no-biscuit.png](img/bad-palette-no-biscuit.png)


### Fonts and Text

Use readable sizes. As I approach 50, I'm starting to understand this more and more. 

Make sure to use **web-accessible** fonts for any content that is going to be exposed ... to the web. 

Ensure that **alt text** is provided for images to ensure that users who experience visualizations through screen readers won't miss out on the information being presented. 


### Universal Design

This is the principle or accessibility goal to make our work available to access a broader population. It goes beyond just color and fonts. 

**Readability** for a general audience should be kept at the high school level when possible. This is especially true in developing countries or underserved areas of first world countries. 

Define unfamiliar terms and avoid unnecessary jargon that requires considerable prior knowledge. 

Pace and organize the introduction of new information to avoid information overload. 

While these are good practices for underserved populations and developing countries, they provide a good baseline for any general audience. 

---- 

## Authorship

Data doesn't speak for itself. (Yet!) Authorship is the concept that the author of visualizations and charts becomes the case-specific domain expert (even if they "aren't".)

Time vested in wrangling and analyzing data in addition to the time spent working with (or for) an audience to curate and structure visualizations qualifies the "author" to make decisions about what should be included and how to reach the target audience. 

That "author" becomes person best positioned to create helpful annotations. 

The concept of **verbal context** is the ability of the author to provide clarification and answers to the audience who asks questions. (This is one of the possible valuable use cases of Generative AI in analytical contexts, because it provides a 'near author' level of expertise.)

The unfortunate limitations of verbal context are that it is only available to the participating audience. It can be useful to some degree if the entire presentation was captured, however only to the extent that any questions future audiences might have are answered within the captured presentation. 

As a result, many charts and visualizations come with a **written summary** that acts as a static proxy of authorship. 

These contextual augmentations provide several potential benefits: 
- limitation of false conclusions
- limitation of misinterpretation
- limitation of misinformation derived from one or both of the previous two. 
- provides a "good faith" of the intent to demonstrate prevention of **disinformation**


## Misleading and Confusing Graphs

Before we wave goodbye to the topic of visualization, it's worth taking a quick tour through common issues. 

### Mercator Projection 

Perhaps the most well-known problem of visualizations is **The Mercator Projection (1569)**. 

This demonstrates the limits of transferring a three-dimensional sphere or globe to a two-dimensional plane (or map). You guessed it, good ole planet Earth. 

While it's useful to teach geography, it severely distorts landmasses near the poles. (No one lives there but polar bears and penguins right?)

This is the most common depiction of the planet on a two-dimensional map. 
![mercator-bad.png](img/mercator-bad.png)


This is a fixed map demonstrating the land masses at proper scale, but distorting position and separation. 
As you can see, it affects more than just penguins and polar bears. 
![mercator-fixed.png](img/mercator-fixed.png)

### Distorted Axes

A frequent tool for misrepresentation along an axis are jumps between the hashmarks on the axis. If you look at the left diagram below, you'll see that the three bars are very difficult to separate because the values are relatively close to each other based on the scale provided for the Y-axis. The right diagram tries to solve this, but introduces additional problems. As you can see the first hashmark represents 100 attendees, the second hashmark represents 105. This distorts the distance between hashmarks. This removes context and amplifies the **change** over the **context** by altering proportional relationships.

A less-problematic distortion is starting an axis from a non-zero number. In the example to the right we could have represented the data, by starting at 100, which retains the spatial relationship of the bars. 

![misleading-axes.png](img/misleading-axes.png)

Good practices for avoiding these issues: 
- if the change between data points is more important than the proportion, it's better to select visualization types that are fit for demonstrating change (e.g. line charts, scatter plots)


- The example to the right was caught up trying to do too much in order to solve the limitations of the visualization on the left. This is a common issue when trying to show both proportion and change. We can borrow the concept of **single responsibility** from software development and architecture; avoid using one graph to tell two stories if it muddles the context. 
  - Consider showing two visualizations. Show a scaled up visualization that maintains the initial proportions, then use a "breakout" or zoomed-in visualization that shows the scaled content. 


- in the worst case, ensure that there is sufficient context to view differences in proportion to a meaningful amount. 


- Generally speaking, due to long-standing convention, readers intuitively expect to see time measured horizontally (on the x-axis). 

---

### Physical Scale

This category of scale refers to the physical distance between numbers on an axis. 

A **linear** scale counts numbers in a consistent interval. **Logarithmic** scaling is common for showing exponential growth that would otherwise not fit on a page when scaled in a linear fashion.

The diagram below shows the same data with a linear scale on the left and a logarithmic scale on the right.

![log-vs-linear.png](img/log-vs-linear.png)

As you can see, logarithmic charts are hard to reason. We don't see the same data shape we're accustomed to seeing. Logarithmic scales are generally considered a very poor choice for general audiences, because they aren't trained or practiced viewing data at that scale. 

This is actually a common tactic used in advertising and marketing when the actual data shape indicates undesirable information. Yes, this is disinformation. 

----

### Color Scale 

You're probably wondering why I'm talking about color again. I swear I'm not sneaking in UX training. Color is one of the first elements our brain begins to decode when we look at visualizations of any kind. This is why color is an important topic when studying data visualizations. 

There are three types of relationships we can visualize with color, and an appropriate color scale for each. 

#### Sequential

Colors in sequence. 

This color scale is usually the same hue with more white being added or removed. This relationship is used to demonstrate increasing/decreasing **magnitude** in a variable. 

![color-scale-sequential.png](img/color-scale-sequential.png)

#### Divergent

This color scale is anchored by colors from opposite sides of the color wheel (a.k.a. **complementary colors**). It is used to visualize data where the middle is a baseline and either side represents a contrasting change. Examples might be a positive/negative swing in voting, temperature above/below some threshold (i.e. boiling, freezing) and most commonly, Profit and Loss statements. 

![color-scale-divergent.png](img/color-scale-divergent.png)


#### Categorical

This color scale is just a variety of colors to differentiate categories or classifications without assigning rank or order. This is the most common relationship we see with color. Selections are often associated with cultural norms (red means stop, green means go in Western nations),etc. 

There is no relationship between the different categories. The colors are connected only to the category they are intended to represent. Categorical representation is the same basic premise as categorical variables

![color-scale-categorical.png](img/color-scale-categorical.png)


NOTE: I usually have a section on Color Associations here, but I've decided to remove it for our purposes. I think I've spoken enough about color, and there are numerous resources that hit the key points better than I can!

---

### Labels and Titles

#### Titles

Pros of a good title:
- It is the simplest, most effective tool for creating understandable visualizations
- reduces most basic confusion


Cons of no title: 
- viewers have to do the leg work (synonymous to passing of costs to the customer)
- we don't know what the axes' measure
- we don't know what the data points show. 
- It's just a pretty picture.


Two Common Techniques: 
1. "Question and Answer"
   - titles are phrased as a question, which is answered by the content of the chart/graph
   - This is extremely powerful for visualizations that have intuitive and obvious depictions of trends or key points. 



2. Statements
   - A direct statement is effective when the significance or "story" told by the data isn't immediately obvious. 
   - The statement should be a clear, concise description of what the graph shows. It is important that it draws the reader's attention quickly to the key data points the visualization is intended to demonstrate.


#### Annotations

Annotations are additional "helper" titles that provide contextual information about the data to support key points. 

Common use cases are: 
- helping viewers understand points of interest
- explanation of any outliers or divergence
- inclusion of background information or context that isn't present in the graph. 
- providing additional details about the information, analysis, data collection etc. (often in anticipation of questions)
- define/explain baselines
- explanation of caveats of the data (potential limitations or invalidators during collection and research)
- reinforce the insights of the graph



### Summary of Visualization Goals 

Normally, I don't end sections with any attempts at wisdom, but this is such a critical concept in the journey of understanding data, I felt it was necessary. 

The goal in avoiding misleading graphs or confusing visualizations is to eliminate the gap between:

**the truth of the data** and **how the viewer understands that truth**

It takes time to improve design skills, and it must be sought with purpose. Strive for clear visualizations that reduce or ideally eliminate bias. Follow established practices that help **standarize** the information being conveyed so that audiences can easily grasp the message. 

One of the greatest misnomers of visualizations is that they are about suiting needs of the moment. 

Good data visualizations are a combination of **quality data** and **effective design choices**.