# weRateDogs_tweets_analysis
Analysing Dog rating tweets from the @WerateDogs twitter account

The data used in this analysis were gotten from three different sources

A csv(comma separated values) file Twitter archive dataset which was publicly available - df_archive  
A tsv (Tab separated values) file holding predictions data of image classification of dog and their breed - df_pred 
Data gotten through the twitter API using the tweepy library- df_twt  
Since the data were from different sources. it was expected to have some issues of data cleanliness. Having that in mind, i merged the 3 dataframes into 1 and named it df_master using their common attribute which is the tweet_id. The df_master was assessed programatically and visually to check for issues of quality and tidiness. Some of the issues discovered are highlighted below:

- Missing data
- wrong Data type
- complex data representation
- outliers in some of the columns input
- Not all tweets are dog ratings
I Made a copy of the master dataframe and named it df_master_copy.
I Dropped columns with missing data and columns associated with retweets as they were not valuable to the Analysis. - I Converted columns with wrong datatypes to their appropriate datatypes.
The columns with complex data representations are columns associated with Doggolingo dog classification and data associated with prediction/classification of dog breeds. In both cases, the columns were made into one meaningful column.
In bid to rate more than one dog in a picture as one rating, @WeRateDog adopted a rating system(different from the standard) to accomodate all dogs in such picture by adding all the rating numerator of each dog as rating_numerator and multiplying the number of dogs by 10 as rating_denominator. E.g a picture of 5 dogs with rating of 12 each will be represented as 60/50. This system was what led to the anomalies found in those columns. The affected rows were assessed and modified by appending the average of the given rating_numerator.
Lastly, the columns that were predicted not to be dog i.e rows with p1_dog, p2_dog and p3_dog as all False were eliminated.
