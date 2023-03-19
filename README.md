# Airbnb_bookibg_analysis

![image](https://user-images.githubusercontent.com/48796009/226155282-f4ef418b-82e6-477c-93a8-c3d87c27f1fa.png)


Airbnb is an online marketplace that connects people who want to rent out their homes with people looking for accommodations in that locale. 
NYC is the most populous city in the United States, and one of the most popular tourism and business places globally.

Since 2008, guests and hosts have used Airbnb to expand on traveling possibilities and present a more unique, personalized way of experiencing the world. 
Nowadays, Airbnb became one of a kind service that is used by the whole world.

 Data analysts become a crucial factor for the company that provided millions of listings through Airbnb. These listings generate a lot of data that can be
 analyzed and used for security, business decisions, understanding of customers’ and providers’ behavior on the platform, implementing innovative additional services,
 guiding marketing initiatives, and much more.
 
 
 
# Data Exploration and variable Identification

Since 2008, guests and hosts have used Airbnb to expand on traveling possibilities and present a more unique, personalized way of experiencing the world. 
Nowadays, Airbnb became one of a kind service that is used by the whole world. Data analysts become a crucial factor for the company that provided millions of listings 
through Airbnb. These listings generate a lot of data that can be analyzed and used for security, business decisions, understanding of customers’ and providers’ behavior
on the platform, implementing innovative additional services, guiding marketing initiatives, and much more.

The very basic information about the dataset using df.info()



![image](https://user-images.githubusercontent.com/48796009/226154536-2b60d199-0d5b-4b6c-86a5-a77810956fba.png)


By basic inspection, a particular property name will have one particular host name hosted by that same individual but a particular host name can have multiple
properties in an area.
So, host_name is a categorical variable here. Also neighbourhood_group (comprising of Manhattan, Brooklyn, Queens, Bronx, Staten Island), 
neighbourhood and room_type (private,shared,Entire home/apt) fall into this category.

~id,latitude,longitude,price,minimum_nights,number_of_reviews,last_review, reviews_per_month, calculated_host_listings_count, availability_365 are numerical variables.


# the price column and see its distribution and nature

I was curious to check the distribution of price over the entire dataset looking at the five-number summary of the data, later found out something like this.

I have used seaborn distplot to plot this distribution curve.
![image](https://user-images.githubusercontent.com/48796009/226154642-4f6f2eea-1004-4eef-90bf-5ab8575dea99.png)


The distribution has a positively skewed tail at the very extreme as we can see. Also getting the skewness as 19.118939 and kurtosis to be 585.672879, depicting the skewness value>1 and kurtosis is much high indicating presence of good amount of outliers, we will look later into this when we handle outliers!!
 
  # the relationship between numerical variables
  We’ll be finding the relationship between these two numerical variables using seaborn scatter plot as below:
  ![image](https://user-images.githubusercontent.com/48796009/226154711-172a1ad8-acd4-4186-8d41-aa005bee416e.png)
  
   the correlation matrix to understand how are the features interrelated with each other. I have plotted using seaborn heatmap to understand the strength between the variables used.

 the correlation matrix to understand how are the features interrelated with each other. I have plotted using seaborn heatmap to understand the strength between the variables used.
 ![image](https://user-images.githubusercontent.com/48796009/226154778-f465a170-b540-40d7-9d04-73d3c7172b33.png)

# Bi-variate analysis on Airbnb
Lets now check for distribution of price across: Manhattan, Brooklyn, Queens, Bronx & Staten Island.Instead of checking distributions for each categories one by
one we can simply do a violin plot for getting the overall statistics for each groups. But we’ll get to know the median of price/neighbourhood group.
![image](https://user-images.githubusercontent.com/48796009/226154846-9094da9b-ea7f-4eac-b2db-d911dfe0a742.png)
As usual Manhattan being the most costliest place to live in, have price more than 140 USD followed by Brooklyn with around 80 USD on an average for the listings.

Queens, Staten Island are on the same page with price on listings.

# Top neighbourhoods in NYC with respect to average price/day of Airbnb listings

![image](https://user-images.githubusercontent.com/48796009/226155230-34b7266e-92f9-48c6-8ce7-37358c39fa4f.png)





The bar plot above clearly depicts the neighbourhoods with listings having highest average price/day in each neighbourhood groups of NYC.

Among the top neighbourhoods in each neighbourhood groups, top 2 of them namely: Fort Wadsworth & Sea Gate, origins from Staten Island & Brooklyn respectively.

 # How monthly reviews varies with room types in each neighbourhood groups?
 
 ![image](https://user-images.githubusercontent.com/48796009/226154892-563dc69f-9b38-4bfb-8123-e5999334b074.png)
 Seaborn stripplot function always treats one of the variables as categorical and draws data at ordinal positions (0, 1, … n) on the relevant axis, even when the data has a numeric or date type. So what do we conclude by this another kind of scatter plot?

So, Private rooms received the most no of reviews/month where Manhattan had the highest reviews received for Private rooms with more than 50 reviews/month, followed by Manhattan in the chase.

Manhattan & Queens got the most no of reviews for Entire home/apt room type.

There were less reviews received from shared rooms as compared to other room types and it was from Staten Island followed by Bronx.
 
 # see what can be done with latitude and longitude?
 ![image](https://user-images.githubusercontent.com/48796009/226154952-3be21925-51ee-48e2-9c6c-223facf01723.png)

Now, let’s check for the distribution of types of rooms across all neighbourhood groups of NYC!

![image](https://user-images.githubusercontent.com/48796009/226154962-055002e5-10f2-4c51-84b2-38751ffc2119.png)

By the two scatterplots of latitude vs longitude we can infer there’s is very less shared room throughout NYC as compared to private and Entire home/apt.

95% of the listings on Airbnb are either Private room or Entire/home apt. Very few guests had opted for shared rooms on Airbnb.

Also, guests mostly prefer this room types when they are looking for a rent on Airbnb as we found out previously in our analysis.

The scatterplot showing the price variables across these co-ordinates in a more authentic way using the original NYC boroughs map by saving the original map image in my local directory and then reading the image using cv2 imread function.

We can infer that there are high range of prices across Manhattan followed by Brooklyn and Queens being the most costliest place to stay in NYC.

Listings availability in a year throughout NYC??

![image](https://user-images.githubusercontent.com/48796009/226154984-8b3bafe9-fbd6-46ea-b62f-e430282a21ce.png)

I’ve plotted the scatterplot depicting the availability of listings available throughout NYC in a year. I have used hues with different sizes based on the availability ranges.

Bronx & Staten Island has listings which are mostly available throughout the year, might be the case as they are not much costlier as compared to other boroughs as in Manhattan, Brooklyn & Queens.

I’ve reached almost the end of the analysis. There might be few analysis which can be done more. But there’s always an ending to a story!





 
