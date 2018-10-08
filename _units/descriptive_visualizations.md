---
layout: page
title: Descriptive Visualizations

order: 50

duration:10

tutorial: true
instructors_notes: true

description: |

supporting_files: 
  - file: id1
    file_name: 'descriptive_visualization.R'
    link_text: Example script for this unit.  
    
---

In this unit we'll explore our data further by creating some common data 
visualizations. We'll also start learning about some of R's powerful
data visualization capabilities.

Still working with our Iris data set, lets first work through creating some
box plots. For this first visualization we'll take a step by step approach to
demonstrate a basic workflow and highlight some of the options available to us.

#### Box Plots

R has a `boxplot()` function built in. So we can start with something fairly basic.
As always, start with `help()` when you are using a new function. As you can see
`boxplot()` has a lot of options, this is typical of visualization functions.

```R
    help(boxplot)
    
    # Equivalent ways of getting Figure 1a.
    boxplot(sepal_length, data=iris_data) 
    boxplot(iris_data$sepal_length)
    
    # Box plot for each variable, Figure 1b.
    boxplot(iris_data[,c(1;4)])
```

<div class="row fig-array">
    <div class="col col-md">
        <figure>
          <img src="{{ site.baseurl }}/assets/img/descriptive_visualizations/figure1a.png" alt="Single variable box plot"/>
          <figcaption>Figure 1a. A simple box plot with one variable.</figcaption>
        </figure>
    </div>
    <div class="col col-md">
        <figure>
          <img src="{{ site.baseurl }}/assets/img/descriptive_visualizations/figure1b.png" alt="Multi-variable box plot"/>
          <figcaption>Figure 1b. A simple box plot with four variables.</figcaption>
        </figure>
    </div>
</div>

There a lot to improve with these box plots. Just using the four variable version,
lets add a title, and tweak the boxes to add a little more information and 
add axis labels.

```R
    boxplot(iris_data[, c(1:4)], 
                main="Iris Flower Morphology Box Plots", 
                notch = TRUE, ylab="Measurement (cm)", 
                xlab="Floral Characteristic")
```

<div class="row fig-array">
    <div class="col col-lg">
        <figure>
          <img src="{{ site.baseurl }}/assets/img/descriptive_visualizations/figure2.png" alt="Improved multi-variable box plot"/>
          <figcaption>Figure 2. Improved multi-variable box plot.</figcaption>
        </figure>
    </div>
</div>


### Histograms

We can easily make histograms as well. Here we use the `par()` function to
create a graphical array of four historgrams. 

```R
    # One figure in row 1 and two figures in row 2
    par(mfrow=c(2,2))  # The par() function arranges the plots, in this case the next four plots in 2 x 2
    hist(iris_data$sepal_length, main = "Sepal Length", xlab = "Length (cm)")
    hist(iris_data$sepal_width, main = "Sepal Width", xlab = "Width (cm)")
    hist(iris_data$petal_length, main = "Petal Length", xlab = "Length (cm)")
    hist(iris_data$petal_width, main = "Petal Width", xlab = "Width (cm)")
```
<div class="row fig-array">
    <div class="col col-lg">
        <figure>
          <img src="{{ site.baseurl }}/assets/img/descriptive_visualizations/figure3.png" alt="Improved multi-variable box plot"/>
          <figcaption>Figure 3. An array of four histograms, displaying the frequency of measurements from each variable.</figcaption>
        </figure>
    </div>
</div>

We are starting to get a sense of our data, and if you look at the histogram,
there is something "odd" going on with petals. Both petal legth and width
have a bimodal distribution. In the next units we will learn how to 
modify and shape our data, do some analyses and learn some more visualization
techniques and tools.





    







