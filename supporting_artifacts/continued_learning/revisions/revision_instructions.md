
# Revisions 
For the revisions included in your Portfolio, to help me understand the nature
of your revisions, please denote somehow the feedback I provided you (e.g.,
boldface, italics, colored text) before your revisions.

### Lab 2
**Technically, both geom_point() and geom_jitter() are plotting points, so you are actually double plotting the points. You only need one of these geoms in your plot!**

**You do not need to use the coord_flip() function to flip the coordinates of your plot. There is a much simpler way. Can you find it?**

The first revision I made was to change my YAML to ensure code folding throughout the entirety of the quarto document. Before, it had simply not code folded any of my html because it was not in the proper format. I had to change the wording of my YAML output since I originally got information from the r-markdown YAML specifications. 
The next revision I made was aligning the two graphs next to one another. Before, I just had 2 lines of code: "#| fig-show: hold / #| out-width: 50%", which placed the plots on top of one another, but after finding the correct specification in the Quarto document online resource, I added the "layout-ncol: 2" below those two lines to make the plots actually next to each other.

I learned that I should refer to a Quarto document resource rather than an R markdown resource when doing labs and challenges! 

### Lab 3
**Careful! A professional looking report should not display messages about reading in the data or loading in package. These messages are not useful for the reader and make your document look cluttered.**

**How was the sample of participants selected? How many were in the sample? How were the participants definitions coded?**

**Yes! There is one row per word per person! How many words are there per participant?**

**Consider the nature of the data when plotting. Is every participant on one row? If not, what should you do with the data before plotting it? The familiarity variable doesn’t speak to demographics of the participants.**

The first revision I made was regarding showing my document output in my final rendered document. Originally, I had all the information associated with loading in the dataset and tidyverse packages included the document output. I thought since I included the echo: False option, the code would not be included in the output. However, after some deeper digging I discovered that specification actually just hides the code, not the output of the code. So, I included an output: False option after figuring out that is the way to actually hide output, which I found in the quarto.org online resource. I learned the difference between the echo: and output: commands and each of their different applications. 

As for questions 1 and 2, I originally did not include a robust enough description for the datasets. This is probably because I just skimmed the document with the original description when we were working on the lab in class, and so I did not think about how it would be appropriate to talk about the number of participants, where the sample came from, how many words there were per participant, etc. I have now included all of this information after a thorough read-through of the data set description. 

For number 8, at first, I was creating plots based on the familiarity, ethnic class, and sex variables. I did not take into consideration the fact that these plots would not plot each participant with relation to these variables, because each participant is represented 64 times for each word, so there were many observations in the graphs. To remedy this, I used the distinct function to pull out the distinct subj values, and assigned this to a new dataset, and then used this dataset for the plots. 
Through this revision process, I learned that I should be wary of the way my data is oriented before making a plot of it, and that the solution to something may be right in front of me.

### Lab 4
**Where are the sections in your report delineating each question? You have revisions on the formatting of your report.**

**I want your output to be the one region with the most avocado sales**

**I want your output to be the one month with the most avocado sales.**

**I want your output to be the five cities with the most avocado sales.**

**You found the top 5 regions and their names are stored in a dataframe. You should use this dataframe to filter rather than typing out the names a second time.**

**I want you to pivot your dataframe to obtain the the differences!**

**Careful! These points are difficult to differentiate between! I would encourage you to jitter them!**

**I don’t want to see the output from summarize() in your report!**

The first revision I implemented was adding the numbers for each section delineating each question. I have no good reason for not doing this originally, but it is a good lesson to check my work before I turn it in. 

2) Cleaning the data:

When I originally cleaned the data, I forgot to include some of the large regions in my dataframes, like NorthernNewEngland and WestTexNewMexico. I have now included both of these regions in the region dataframe. 

3) Which major region sold the most organic, small Hass avocados in 2017?:

When I originally found which region sold the most organic, small Hass avocados in 2017, the summarize function at the end was printing out all of the regions and I just looked at it and identified the top region. To make it print out only the top region, I added a slice_max() condition at the end which filtered the output down to just the top mean. This makes the output much more concise to answer the question. 

4) Use the separate() function to split the Date variable into year, month, and day. In which month is the highest volume of avocado sales?:

Similar to the last problem, I originally was printing out each month’s sales, rather than the top month’s sales. To remedy this, I added another slice_max() function. Once again, this makes the output much more clear in terms of answering the question. 

5) Which metro area regions sold the most total avocados? Plot side-by-side boxplots of total volume for only the five regions with the highest averages for the Total Volume variable.:

When I originally did this problem, I had the function print out all of the metro areas, rather than just the top five. To remedy this, I added a slice_head(n = 5) function at the end of my pipeline, to ensure that only the top five cities were being printed out. This makes my output much more clear and tidy!
Also for number 5, I originally created a whole new dataframe where I manually found the top regions and typed their names in as strings. Now that I have a whole new dataframe with just the top 5 regions specified, however, I used this dataframe to join with my metro_regions data frame. This is much more efficient than typing out all the names again!

6) In which regions is the price of organic versus conventional avocados most different? Support your answer with a few summary statistics and a visualization.:

In this question, I originally just printed out a tibble depicting each region, and type, with their associated mean average prices. After pivoting the dataframe, I created a tibble with just the regions and the mean average price for each type of avocado in their respective columns. I then added another column in which I found the difference between the conventional and organic avocado types. I also added a brief answer to the actual question being asked. This particular revision reiterated the concept that summary statistics should be concise, and the revision helped me to achieve that in my code. 
For the visualization in part 6, I was unsatisfied by my plot when I originally made it but wasn’t sure what to do about it. This revision comment reminded me of the geom_jitter() function, which I implemented in my code. It made the points on the plot much more discernible!

7) Plot recreation:

For number 7, my knitted html document was originally printing out the output from my summarize argument, when it should have just been outputting my pretty recreated plot. To remedy this issue I created another code chunk for the plot, which isolated the code pivoting the dataframe. I then hid the output for this code chunk. 

Throughout this revision process, I learned that the output from my code should be very clear and concise. I also learned that these lab steps are meant to build off of one another, so I made the whole document a bit more cohesive. 

### Lab 7
**What is the input structure for across()? What is the first input? What is the second input? How do we indicate that our function we want across() to use is something we’re creating?**
**Great work using map() How could use use a map family function that outputs a vector or dataframe of missing values?**

**Every plot you make in this course should have informative labels! What is being plotted on the y-axis? What do the 1 and 2 in the facets refer to? What does section refer to?** 

**The , in stopifnot() is the same as calling the function multiple times! Arguably, calling the function multiple times is also inefficient! ;)**

**A bar plot is reserved for categorical variables. What type of plots do we use for the distribution of numerical variables?**

Part One: Summaries and Plots

Task 1 – Summarizing Missing Data:

The first revision I made was to reorient the way I used the across function. I was using the sum() and is.na() functions outside of the function, when I could have more easily put the functions inside the .fns argument within the across function. I made this change and the output is more clear. 

The second revision I made to this problem was to change map() to map_int() to ensure the output was an integer vector, rather than a list. 

Task 2 – Visualizing Missing Data:

For the graph in task 2, I added some labels to make it more informative for the reader. The title explains what is being plotted on the y-axis, what the “1” and “2” facets mean, as well as what the colors in the legend are telling us. I also added a better legend title. 

Part Two: Adjusting the Data:

Task 2 – Adding Stops:

I adjusted the stopifnot() function to be more efficient with a comma, rather than calling it two times in a row. 

Task 4 - Performing a More Difficult Test:

I changed my original bar plots to histograms since they are better for visualizing the distribution of numerical variables. 

Through this revision process, I have learned to go back and triple check my work. I also learned that I should constantly be going back and referring to past labs and assignments to implement the things I have gotten revisions on in the past, especially with being more efficient.


