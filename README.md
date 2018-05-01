# Data Wrangling
I worked on this project where i had to wrangle tweet data from different sources to create a clean dataset on which i could perform analysis and provide useful insights. First, let me explain what is Data Wrangling?

Data Wranglingis a process where first data is gathered from different sources, then the quality of the data is assessed and finally the data is cleaned to create a dataset on which exploratory data analysis could be performed.

Basically the following three processes are performed in Data Wrangling:-

Gather : The data is gathered from different sources. The data could be downloaded from a link, scraped from a website, uploaded from txt, csv and more kind of files.
Assess : After gathering data, it is assesed visually as well as programatically. The data is assesed on the basis of its quality and tidiness. Dirty(poor quality) data and untidy(messy) data are the two unwanted traits of gathered data that should be assessed properly and then cleaned.
Clean : After assessing the gathered data and noting down all the unwanted traits, the data is cleaned programatically. Cleaning consists of three steps: Define, Code & Test.

## Gather
For this I had to gather three pieces of data, all three from different sources. First, I gathered the WeRateDogs Twitter archive from a csv file which was manually downloaded from a link provided. Second, I gathered the tweet image predictions data from a link programatically using the python library requests. Finally, I used Tweepy python access library for Twitter to fetch the tweet data for each tweet_id in the WeRateDogs. Using the tweepy library, I got JSON data which I wrote to a text file, gathering all the tweets JSON data in text file. Later on fetched tweet ID, retweet count, and favorite count from the text file line by line and then created a data base.

## Assess
After gathering all the 3 files, I stored their data into a dataframe for easier assessment and cleaning. In order to assess the data, I examined it visually and programatically using python's pandaslibrary. First, i printed out all the dataframes entirely, used the info() function to assess the datatypes, used describe() function to summarise the quantitative variables in the datasets, etc. Then i examined the dataframes more specifically by examining each variable separately and found out the following issues:-

### Quality
Missing and incorrect dog names extracted from text. 'a' is the most popular name which itself is not a name.
Timestamp is in string format.
Source not extracted properly from hyperlink tag.
A lot of null values are not null.
Columns: in_reply_to_status_id, in_reply_to_user_id, retweeted_status_user_id, retweeted_status_id and retweeted_status_timestamp, have a lot of null values.
Gender of dog could be extracted from text.
Hashtags could also be extracted.
Absurd rating values.
Records without dog breed prediction
### Tidiness
The dog stage columns in twitter_archive can be arranged into a single column.
The image predictions could be condensed to show just the most confident dog breed prediction.
All three dataframes can be combined into one single dataframe.

## Clean
Cleaning process consists of three steps: Define, code & Test. First we define how to tackle the issue. Then, we code to resolve the issue and finally we test our code to see if the issues with the data have been resolved. So, in order to clean these 3 dataframes, I carried out the 3 steps for each of the issues and was finally able to achive a clean dataframe. For cleaning purposes, I used pandas's functions: cut, merge, apply, etc. The cleaned dataset was then stored into a csv file.
