# Age-and-Context-Sensitive-Hybrid-Entertaintment-Recommender-System
                                                                                
### About
With the hectic lifestyle, the time a family spends together has decreased
in today's world. Rather than spending quantity family time, quality family
time has become essential. Hence, many people have started with family
movie night rituals in their houses. However, families have to spend much
time finding movies that all family members prefer and that are
age-appropriate. Our project aims to create a movie recommendation
system that considers the family members' preferences, past activities,
and age and recommends an age-appropriate movie for the family.
### Introduction
As fun and easy as it is to binge your favorite shows with your loved ones,
choosing what to watch is challenging. With so many genres to choose
from, different preferences among individuals, and choosing
age-appropriate content, narrowing down on the top movies and shows
can be complicated.
Our Ml model is a movie recommendation system for a group of
individuals which recommends the top movies based on the above
criteria. Our dataset contains information about the users and the ratings
given by them to make suggestions.

### Features

- Allows age based Filtering
- Supports Content Based Filtering for Standard Recommendations
- Supports Content Based Filtering for Standard Recommendations
- Supports Content Based Filtering for finding similar content
- Supports Collaborative Filtering for matching user preferences
- Useful for families with multiple preferences for people of all age groups

### Datasets
The datasets were sourced from kaggle.com and movielens.com. They have been included with theis project. For more information, check out the detailed report.
##### Dataset Description For Content and Demographic Filtering:
- Our dataset contains the following attributes:
 -  type: If it is a movie or a TV show.
 -  title: The current title of the movie.
 - director: The director(s) of the movie/TV show.
 - cast: The actor(s)/actress(es) of the movie/TV show.
 -  country: The country in which the movie was released.
 - date added: The date on which the movie/TV show was released.
 -  age_rating: The age rating given to the movie/TV show.
 - duration: Total duration of the movie/TV show
 - listed_in: Genre(s) of the movie/TV show.
 - description: Sentence(s) describing the movie/TV show.
 - IMDB: The IMDB rating of the movies/TV show
 - TMBD: The tmdb rating of the movies/TV show
 
##### Dataset Description For Collaborative Filtering:
- Our dataset contains the following attributes:
 - title: The current title of the movie.
 - user id: Uniquely identifies the user
 - movie id: Uniquely identifies the movie.
 - rating: The rating given by the user to a specific movie.

### Exploratory Data Analysis
In order to understand the structuring of our data, and fine tune some parameters, we analyzed the data on several grounds. Some results of the analysis have been presented below. Check the report for a more detailed description.

![image](https://user-images.githubusercontent.com/88545875/205520998-9ab23977-eeef-4a9d-b9c5-3fd1f730948b.png)
![image](https://user-images.githubusercontent.com/88545875/205521048-198b3a08-0fc8-40e3-8ad9-6e1dab0e411f.png)
![image](https://user-images.githubusercontent.com/88545875/205521076-694c67be-330f-4c3f-aa8a-aa3d2dfa2cf3.png)
![image](https://user-images.githubusercontent.com/88545875/205521116-2787e755-b5aa-4cae-8b39-4da05a80a5a3.png)
![image](https://user-images.githubusercontent.com/88545875/205521136-15011862-8cd4-40cc-b540-212a1f7cdabe.png)

### Sample Output
We tested the model on the following input:

![image](https://user-images.githubusercontent.com/88545875/205521629-19ec17a2-6af5-4c2d-bef8-68f56351a766.png)

And obtained the following output: 

![image](https://user-images.githubusercontent.com/88545875/205521582-2eacca24-0dbb-4bde-ab5a-e170a52ff6dd.png)

For detailed description of the working of this model, check out the report.

### Learnings from this Project

Through this project, we learned about the three main filtering
techniques for movie recommendation systems: content-based,
collaborative, and demographic filtering. Content-based filtering provides
recommendations similar to the user's preferences in the past.
Demographic filtering utilizes information from the population to make
recommendations where user preferences are unknown.
Collaborative-based filtering provides recommendations by finding
similar users. We learned about encoding string data into more
computationally friendly formats while preserving the integrity of the
data. We also learned about different similarity metrics like Pearson
correlation and cosine similarity. We learned how to apply PCA and chose
the number of components to reduce dimensionality. We applied K-means
to analyze if our data could be clustered.
