# Finding a Suitable Neighborhood using Clustering & Foursquare API

# 1. Introduction

## 1.1 Problem

The project is based on a hypothetical personal scenario, but can be understood and tuned by others to help them out if they are in a similar situation.

I used to live in the city of Manchester. I used to love the place so much, but now due to family needs, we are moving to London.

I wonder how my lifestyle will change? Is there a way I can make myself feel at home even after changing the place? Maybe I can find a similar flat and residence. But what if we take a step further, and try to find a neighborhood that has all the right favorite places at similar proximity as the past residence? 

The favorite places at my previous residence were: 

- University (3.2 Miles)
- Indian Restaurant (2 Miles)
- Chinese Restaurant (1 Mile)
- Library (5.8 Miles)
- Martial Arts Dojo (6 Miles)
- Hospital (5 Miles)
- Garden (3 Miles)

If I could get all of these at the right proximity from the new home, maybe that would make it very easy to adapt to the new lifestyle. Perfect!

So the problem is : 

**"Can we find neighborhoods that are most similar to another one, in terms of proximity and availability of favorite venues?"**

## 1.2 Audience

The audience of this experiment is any individual who is looking for moving to a new place, and needs all his favorite places available in a similar fashion as the old residence.

We have chosen the particular case of various Boroughs in London, and the above mentioned venues at particular distances. But the reader can use similar methods to implement a solution for their problem.

# 2. Data

## 2.1 Boroughs in London & Their Coordinates

We definitely need to enlist all the Boroughs out there in the City of London, in order to proceed with any step in the experiment.

I found the right thing available at the Wikipedia page [https://en.wikipedia.org/wiki/London_boroughs](https://en.wikipedia.org/wiki/London_boroughs)

On which we will use some Web Scraping methods to extract the data.

We will also need the latitude and longitudes of the neighborhoods in order to use the Foursquare API. For the coordinates we will use a free geocoding API named LocationIQ ([https://locationiq.com/](https://locationiq.com/)). 

## 2.2 Category-wise Popular Venues in each Borough

 We will need to find for each Neighborhood the most popular venues in each category (University, Indian Restaurant, Garden, etc.)

We will average the distance of top venues for a category instead to choosing the minimum. This is because we cannot rely on just one venue to choose the new neighborhoods, in case it is not good enough.

The Foursquare API provides the **search**  endpoint to find popular venues near a location given by particular latitude and longitude. It also allows to filter the results by category.

[https://api.foursquare.com/v2/venues/search](https://api.foursquare.com/v2/venues/search)