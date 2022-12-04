

Age and Context Sensitive

Entertainment Recommendation Model

Machine Learning Final semester project evaluation

1





Motivation

As fun and easy as it is to binge your favorite shows

with your loved ones, choosing what to watch is a

challenging task. With so many genres to choose

from, different preferences among individuals, and

choosing age-appropriate content, narrowing down

on the top movies and shows can be complicated.

With our project, we aim to create a movie

recommendation system that considers the family

members' preferences, past activities, and age and

recommends an age-appropriate movie for the family

to watch.

2





Literature Review

\1. User Based vs Item Based Filtering [1]

In user based ﬁltering, interests of users were compared to ﬁnd similar users.

Pearson Correlation Coeﬃcient was used to determine the similarity between ratings. The higher the coeﬃcient,

the more correlated were the two users. An algorithm which found N nearest neighbors and made clusters of

neighbors was used for user based Filtering. Since ratings change from time-to-time, this method is not static. In

Item Based Filtering, Log Likelihood similarity was used. User ratings once given do not change, hence values of

similarity would remain constant.

\2. Movie recommendation system using collaborative learning [2]

In this paper, a collaborative approach is used in prescribing movies to others with similar tastes, allowing users

to explore more. A web application is implemented that will enable users to rate movies and recommend

appropriate movies based on others' ratings. This paper concluded that the content-based recommendation

systems work on individual users’ ratings, limiting users from exploring more. However, the collaborative

learning approach computes the connection between different users and, relying upon their ratings,

recommends movies to others with similar tastes, allowing users to explore more.

3





Dataset Description

Dataset Description For Content and Demographic Filtering:

Our dataset contains the following attributes:

●

●

●

●

●

●

●

●

●

●

●

●

type: If it is a movie or a TV show.

title: The current title of the movie.

director: The director(s) of the movie/TV show.

cast: The actor(s)/actress(es) of the movie/TV show.

country: The country in which the movie was released.

date added: The date on which the movie/TV show was released.

age\_rating: The age rating given to the movie/TV show.

duration: Total duration of the movie/TV show

listed\_in: Genre(s) of the movie/TV show.

description: Sentence(s) describing the movie/TV show.

IMDB: The IMDB rating of the movies/TV show

TMBD: The tmdb rating of the movies/TV show

Dataset Description For Collaborative Filtering:

Our dataset contains the following attributes:

●

●

●

●

title: The current title of the movie.

user id: Uniquely identiﬁes the user

movie id: Uniquely identiﬁes the movie.

rating: The rating given by the user to a speciﬁc movie.

4





Data Preprocessing

● Merging of Datasets

○ Two datasets were merged to generate a dataset of

10k+ rows.

○ Outer-join was performed.

● Removal of duplicate rows whilst maintaining max data

○ Duplicate rows due to slight difference /null values in

columns of same title rows.

○ Information from all rows combined in a single row and

dropping of duplicates.

● Feature Selection

○ Seasons, duration and director column dropped.

● Removal of empty values

○ Dropping of rows where value is empty.

● One - Hot Encoding of Genre

○ Listed\_in consisted of multiple genres for movie/show.

One-hot encoded the genres.

5





Exploratory Data Analysis or EDA

Genres of movies and

TV shows. The highest

genre comes out to be

international movies, the

second highest genre is

Dramas

Frequency of the

imdb and tmdb

ratings of the

movies and TV

shows

6





Exploratory Data Analysis or EDA

Count of the age

certiﬁcation ratings of the

movies/TV shows of the

dataset. TV shows with

rating TV-MA(Mature

Audience) have the

highest count.

The Top 5

movies/Tv shows

with the highest

imdb rating(left) and

tmdb rating(right)

7





Exploratory Data Analysis or EDA

The count of

movies and TV

shows in the

dataset. There

are more

Countries that

made the most

movies/TV

shows. USA is

the highest

movies than TV

shows in our

dataset.

among all the

Number of

movies

released in a

year with max

in 2016 and

2017

8





Exploratory Data Analysis or EDA

Scatter plot

depicting for each

movie its average

rating(x) vs the

number of ratings

given by the user

A bell shaped plot

depicting the ratings

and round-off rating

given by the users

9





PCA vs Variance

● Our ﬁnal TFIDF matrix came to be

around of size 8809 X 18000

● We can’t apply PCA on the 8k rows

as these represent the movies

● We have applied PCA on the 18k

vector.

● We plotted n(dimensions column

vector is reduced to) Vs Variance

● Variance indicates the amount of

information preserved after

dimensionality reduction

N components vs Variance

10





Methodology

Age Based Filters

We have different categories like TV-MA: strictly for adults, TV-14: for 14 and

above, and TV-PG: for 14 and above but with parental guidance. Following this,

we updated our dataset to remove ratings unsuitable for the given age group.

We decide on suitable ratings by the min and max age present in the group.

Min-age is calculated to remove adult movies, while max-age is calculated so PG

movies(parental guidance) can be allowed when an adult accompanies the

children.

11





Demographic Filtering

Demographic refers to the statistical characteristics of the human population. When a new user joins the system,

the model is unaware of his past choices. This situation is termed a ‘Cold Start’. In such situations, we can predict

the top-rated movies of all time to the user. In our dataset, we had access to both the IMDB and TMDB ratings of a

movie. The Pearson correlation between them was found to be 0.57. This is a moderate-high positive correlation,

i.e., if one increases, the other is also expected to increase.

The weights by which IMDB and TMDB ratings is multiplied are hyperparameters which can be tuned if real-time

feedback is available.

IMDb ratings are more popular hence Imdb ratings were given a higher priority in the new\_score calculation

12





Content Based Filtering

We calculated the Term Frequency-Inverse Document Frequency (TF-IDF) vectors of the description on an age ﬁltered

dataset. For quantifying similarity, we used Cosine Similarity as it is independent of magnitude and is much faster to

calculate than the other two metrics without signiﬁcantly affecting our ﬁnal results.

The formal, mathematical deﬁnition of cosine similarity is as follows:

Finally, we sorted the list containing the pairwise cosine similarity of all the movies with the movie we chose

and took the total sum of pairwise cosine similarity of each movie in the dataset with each movie of choice

as our ﬁnal similarity metric. We then recommended the movies in decreasing order of value of this metric.

13





Collaborative Filtering

In the collaborative ﬁltering approach, we recommend the movies to a user based on other users having similar interests.

We look for users with similar tastes and preferences to the current user. Then we recommend the movies favored by the

matched users to the current user.

We make a pivot table with index value as the user id, columns value as the movie title and the feature whose statistical

summary is to be seen is ratings. Now we input a movie name to which the current user wants similar recommendations.

We calculate the Pearson correlation of the column vector of the input movie title with all other column vectors having

ratings more than 20.

Now we get the pairwise Pearson Correlation value of every movie with the input movie. Now, we recommend ﬁve

movies whose pairwise Pearson Correlation is the highest.

14





Results/Analysis/Conclusion

Demographic Filtering

15

Movies with top scores are recommended





Results/Analysis/Conclusion

Content Based Filtering

a) For a group of teenagers

b) For a group of adults

16





Results/Analysis/Conclusion

Collaborative Based Filtering

Model Performance In Collaborative Filtering

●

We cannot directly minimize the loss or calculate

the performance metric of our model based on

fixed data.

●

●

True Performance can be analyzed by collecting

user feedback for the recommendations made.

It can be calculated through CTR. CTR is the

number of times a recommendation is clicked by

the user upon the total number of times the

recommendation is shown.

●

Over time, the CTR value of the model increases as

it gains more information about the user

preferences and choices.

17





Combined Output

Input:

Output:

18





Final Outputs

According to the timeline we proposed in the proposal, we have

completed all the tasks that we proposed.

The tasks to be accomplished are as follows :

●

●

●

●

●

●

●

Data Collection and Data Visualization

Feature Analysis and Selection

Principal Component Analysis

Content Based Filtering

Demographic Filtering

Age Based Filtering

Collaborative Filtering

●

●

●

●

Model performance Analysis

K - Means Clustering

Hyperparameter Tuning

Adding the option of entering more movie preferences per

user in order to make a more accurate movie

recommendation system.

19





**Thank You!**

Abhinn Yadav(2020013)

Dhruv Mishra(2020296)

Hunar Kaur(2020303)

Sadhvi Bhan(2020325)

20

