# weRateDogs_tweets_analysis
Analysing Dog rating tweets from the @WerateDogs twitter account

The data used in this analysis were gotten from three different sources

- A csv(comma separated values) file Twitter archive dataset which was publicly available - df_archive  
- A tsv (Tab separated values) file holding predictions data of image classification of dog and their corresponding - df_pred 
- Data gotten through the twitter API using the tweepy library- df_twt  
 
Since the data were from different sources, issues of data cleanliness are inevictable. Having that in mind, i merged the 3 dataframes into 1 and named it df_master using their common attribute which is the tweet_id. The df_master was assessed programatically and visually to check for issues of quality and tidiness. Some of the issues discovered are highlighted below:

- Missing data
- wrong Data type
- complex data representation
- outliers in some of the columns input
- Not all tweets are dog ratings  
