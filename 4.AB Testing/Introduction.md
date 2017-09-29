
An AB test is an example of statistical hypothesis testing, a process whereby a hypothesis is made about the relationship between two data sets and those data sets are then compared against each other to determine if there is a statistically significant relationship or not.

To put this in more practical terms, a prediction is made that Page Variation #B will perform better than Page Variation #A, and then data sets from both pages are observed and compared to determine if Page Variation #B is a statistically significant improvement over Page Variation #A.

But that’s not the whole story. The point of AB testing has absolutely nothing to do with how variations #A or #B perform. We don’t care about that.

What we care about is how our page will ultimately perform with our entire audience.

And from this birdseye view, the answer to our original question is that statistical analysis is our best tool for predicting outcomes we don’t know using information we do know.

In short, statistical analysis allows us to use information we know to predict outcomes we don’t know with a reasonable level of accuracy.


## Sampling

![picture](https://conversionsciences.com/wp-content/uploads/pasted-image-0-2.png)


The “population” is the group we want information about. It’s the next 100,000 visitors in my previous example. When we’re testing a webpage, the true population is every future individual who will visit that page.

The “sample” is a small portion of the larger population. It’s the first 1,000 visitors we observe in my previous example.

In a perfect world, the sample would be 100% representative of the overall population.

For example:

Let’s say 10,000 out of those 100,000 visitors are going to ultimately convert into sales. Our true conversion rate would then be 10%.

In a tester’s perfect world, the mean (average) conversion rate of any sample(s) we select from the population would always be identical to the population’s true conversion rate. In other words, if you selected a sample of 10 visitors, 1 of them (10%) would buy, and if you selected a sample of 100 visitors, then 10 would be buy.

But that’s not how things work in real life.

In real life, you might have only 2 out of the first 100 buy or you might have 20… or even zero. You could have a single purchase from Monday through Friday and then 30 on Saturday.

This variability across samples is expressed as a unit called the “variance”, which measures how far a random sample can differ from the true mean (average).

The Freakonomics podcast makes an excellent point about what “random” really is. If you have one person flip a coin 100 times, you would have a random list of heads or tails with a high variance.

If we write these results down, we would expect to see several examples of long streaks, five or seven or even ten heads in a row. When we think of randomness, we imagine that these streaks would be rare. Statistically, they are quite possible in such a dataset with high variance.

The higher the variance, the more variable the mean will be across samples. Variance is, in some ways, the reason statistical analysis isn’t a simple process. It’s the reason I need to write an article like this in the first place.

So it would not be impossible to take a sample of ten results that contain one of these streaks. This would certainly not be representative of the entire 100 flips of the coin, however.

Fortunately, we have a phenomenon that helps us account for variance called “regression toward the mean”.


In order to compare two pages against each other in an Ab test, we have to first collect data on each page individually.

Typically, whatever AB testing tool you are using will automatically handle this for you, but there are some important details that can affect how you interpret results, and this is the foundation of statistical hypothesis testing, so I want to go ahead and cover this part of the process.

Let’s say you test your original page with 3,662 visitors and get 378 conversions. What is the conversion rate?

You are probably tempted to say 10.3%, but that’s inaccurate. 10.3% is simply the mean of our sample. There’s a lot more to the story.

![picture](https://www.che.utah.edu/~tony/img/CI_CL/CICL_in_meas.gif)


To understand the full story, we need to understand two key terms:

Confidence Interval
Margin of Error


In order to compare two pages against each other in an Ab test, we have to first collect data on each page individually.

Typically, whatever AB testing tool you are using will automatically handle this for you, but there are some important details that can affect how you interpret results, and this is the foundation of statistical hypothesis testing, so I want to go ahead and cover this part of the process.

Let’s say you test your original page with 3,662 visitors and get 378 conversions. What is the conversion rate?

You are probably tempted to say 10.3%, but that’s inaccurate. 10.3% is simply the mean of our sample. There’s a lot more to the story.

To understand the full story, we need to understand two key terms:

Confidence Interval
Margin of Error



$$ \alpha = \beta $$        (a)








Markup : * Bullet list
              * Nested bullet
                  * Sub-nested bullet etc
          * Bullet list item 2







First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell
