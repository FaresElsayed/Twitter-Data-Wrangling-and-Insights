Twitter-Data-Wrangling-and-Insights
---------------------------------------
Real-world data rarely comes clean. Using Python and its libraries, we will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it.
Then Showcasing the data through analyses and visualizations using Python (and its libraries).

Goal:
---------------------------------------
wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations.
The Twitter archive is great, but it only contains very basic tweet information.
Additional gathering, then assessing and cleaning is required for "Wow!"-worthy analyses and visualizations.

The Data:
---------------------------------------
The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything.
One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced" Of the 5000+ tweets, I have filtered for tweets with ratings only (there are 2356).

The extracted data from each tweet's text

Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But you, because you have the WeRateDogs Twitter archive and specifically the tweet IDs within it, can gather this data for all 5000+. And guess what? You're going to query Twitter's API to gather this valuable data.

Image Predictions File

One more cool thing: I ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs*.
The results are a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

Image predictions
Tweet image prediction data

So for the last row in that table:

tweet_id is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921

p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever

p1_conf is how confident the algorithm is in its #1 prediction → 95%

p1_dog is whether or not the #1 prediction is a breed of dog → TRUE

p2 is the algorithm's second most likely prediction → Labrador retriever

p2_conf is how confident the algorithm is in its #2 prediction → 1%

p2_dog is whether or not the #2 prediction is a breed of dog → TRUE

etc.

And the #1 prediction for the image in that tweet was spot on:

@dog_rates tweet
A golden retriever named Stuart

So that's all fun and good. But all of this additional data will need to be gathered, assessed, and cleaned. This is where I come in.

