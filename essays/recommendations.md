---
layout: essay
type: essay
title: Filtering With Individuality or Popularity?
# All dates must be YYYY-MM-DD format!
date: 2020-02-13
labels:
  - Software Engineering
  - Machine Learning
  - Social Media
---

People don’t realize this, but the reasons why many websites become popular are not because of their features at face value. Sure a cool and unique website will grab the normal viewer at first glance, but what keeps them staying is the functionality in the background, namely their recommendation algorithms. Algorithms is a word that loves to be thrown around in famous platforms like Youtube, Instagram, and Twitter because they get people to stay by giving them more of what they want. And although we aren’t trying to have our viewers in InternBit (or whatever our label will be in the future) stay for long periods of time, it will help in the long run to give them instant recommendations for job listings that they searched for before. In the end, our goal should be to have our viewers find job listings that they want without even needing the use of a search bar. So talk get straight to the point and talk about the pros and cons of different recommendation algorithms and relate them to real life examples.

## Content Based:
As one of the more major approaches to a recommendation system, it filters the content given to a user based on what they have liked/frequented previously and works to give them more of what they want. In a sense, the algorithm will only recommend job listings that are similar to what you search the most. 
There are a few methods of finding the similarities of the item that you want, mainly the Cosine Similarity and Jaccard methods. Cosine similarity looks at the commonality of two items (i.e. the skills or common words in a job title) and produces a dot product between 0-1 (where 1 means perfect similarity). It’s a great method when there are many different metrics to calculate similarities for, but is also quite tedious as you must program code to check every property of a job listing for this method to give better results. Jaccard Similarity looks at the intersection over union of two items to give a similarity score. This is easier to make, but probably won’t work with job listings if there is a rating or ranking system implemented. Overall, if we are looking at individuality for a user’s experience with our website, this is the way to go.

### Pros:
A great system for frequent users, as they get their job listings on what they have liked before.
Recommendations evolve with the user. If a person wants a different kind of job listing, eventually the algorithm will adapt to recommend based on the new preference.
Easier to implement as we only need individual databases to have their recommendations.
The algorithm works without need of other user input.

### Cons:
Not very “first-time user” friendly, can be circumvented with a personalized profiling for new accounts. A great example of this is Netflix’s personalization system which asks a set of questions for genre.
Doesn’t recommend job listings out of what you prefer, making potentially good jobs unseen.
Produces inaccurate recommendations if there isn’t enough information in the job listings to work with.

### Examples of Websites/Social Media Platform w/This Method:
Netflix (Highly personalized recommendations, different tiers of similarity listing)
TikTok (Its For You Page AKA “FYP” constantly changes recommendations off of likes and shares. Extremely fluid)
Youtube (Advanced algorithm that recommends with a mixture of liked videos and subscription similarities)

### How To Approach This Method:
Similarity method to use would be the cosine similarity method as we are checking similarity through different metrics (Job Title, Company, Skills, etc.).

Examples of how cosine similarity works can be seen [here](https://www.machinelearningplus.com/nlp/cosine-similarity/)

Higher priority on job title similarity, second tier priority on skills needed (possibly make a metric that prevents the recommendation if the user doesn’t possess most of the skills needed). This can be achieved by a point-system method that gives points for similar words (points can be given for liked job listings).
Have a personalized profile tutorial for new users to check what skills they have and what jobs they are looking for (Made with a dropdown listing perhaps) to create a basic recommendation list.

I suggest looking at [this](https://towardsdatascience.com/how-to-build-from-scratch-a-content-based-movie-recommender-with-natural-language-processing-25ad400eb243) for coding help and approaching examples.


## Collaborative Filtering:
The second major approach to filtering recommendations, this method uses a more popularity approach into giving recommendations. If another person with similar interests in a job liked a post that you didn’t, the algorithm will more likely send that same job to you as a recommendation. In a sense, more people will gravitate towards jobs that seem interesting, creating a recommendation pool that many will agree to be good. Overall, this method helps to filter the jobs to find not only is good for you, but also that looks good as a whole. 
This also has two main methods to approach with: memory based and model based. Memory based approach uses the previously mentioned similarity methods and compares them between users with an added rating score based off of liked posts. This is done with multiple users and provides recommendations based on user ratings. It’s supposedly easy to create and interpret, but without an ample supply of user input, it is extremely inaccurate. Model based approach uses matrix factorization to produce ratings on which postings between users is more recommended. Quite hard to implement and hard to interpret, but good for faster computation over larger user bases. 

If you’re confused on how matrix factorization works as well as more help understanding collaborative filtering, watch [this](https://www.youtube.com/watch?v=n3RKsY2H-NE). 

### Pros:
Provides a popularity system within recommendations (popular jobs on your interest is more likely to show up)
Can provide very accurate recommendations with ample user input to work off on.
Allows for jobs that slightly deviate from what you prefer to show up, allowing for more diversity in the recommendation listing.

### Cons:
Quite difficult to get accurate recommendations without a large user base.
Harder to implement and interpret similarity results.
Can be quite slow since it uses the entire database to determine recommendations.
Popular job postings could overshadow less popular ones, causing many good listings to be unseen.
Popular job postings = more competition

### Examples of This Method Used:
Twitter: Famous for their retweet function that influences the algorithm to see more of what your friends are posting.
Netflix: Works in tandem with the personalized recommendation system to show most popular shows/movies of your liking.
Mostly every other social media platform.

### How to Approach This Method:
Quite difficult as we don't really have a good amount of people to have accurate predictions, but hypothetically, we should use a memory based approach as it’s a way easier method to implement. 
Revolve the predictions over the favorite function or even a rating system if we want to implement that, then cross reference with similarities to your liking.

## Other Methods:
Although I went on about the two major methods used by most recommendation systems, there are four other methods that could be looked upon as well. These include Demographic Based, Utility Based, Knowledge Based, and Hybrid Recommender. Ultimately they work off similar concepts as Content and Collaborative recommendation systems, but they have their own unique advantages with each one. 

More about what each does can be found [here](https://www.bluepiit.com/blog/classifying-recommender-systems/#:~:text=There%20are%20majorly%20six%20types,system%20and%20Hybrid%20recommender%20system).

## My Choice For Our Recommendation System:
Each of the two recommendation systems have quite good qualities going for them, but ultimately I would say that the Content Based approach using the Cosine Similarity method would probably be the best to go for. As this is an internship website with a specific niche, Computer Science Majors, having a Collaborative recommendation system wouldn’t really work out. There will be a smaller viewer pool and recommendations will just be a handful of popular job listings that will obscure the different niches that can be in ICS. Content Based allows viewers to cultivate a specific job pool that they can choose from and overall will lessen the idea of competition within the site as a whole. So, when we do start making our recommendation system, I highly suggest going for Content Based.
 
