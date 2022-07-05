# Movie-Recommendation-System
Movie Recommendation System based on  Item-Item Recommendation System. This technique attempts to figure out what a user's favourite aspects of an item is, and then recommends items that present those aspects.  We use Maxtrix-Factorization based algorithm to predict our movies to the user.

##Pre-Processing:
1. Differentiating between the year that is given in the 'title' into a different column under 'year'. 
2. Then splitting the differnt genre's by  | so that we can use the split function on it.
3. Putting all of the genre into different columns and iterating '1' and '0' based on the movie if it comes under the given 'Genre'.
4. Removing Timestamp from the Reviews.csv to clean the dataframe with usefull information only.

#Application on Matrix-Factorization based Algorithm:

We figure out to apply Content Based Recommendation System in it , and upload the dataset given by the user of its favourite movie which inlcudes the year , genre and title of the following movie. We keep it under the dataframe of UserInput.
We merge the UserInput to our own Movies Dataset and produce a InputMovies table which is in the same way written as our original datatable. (inlcuding the reviews)
Filter out these InputMovies from the MovieswithGenre table and create a table which now inlcudes the movies with the '1' and '0's of the given genre.

We create a GenreTable which drops the name of the movies and year it was realeased and just keeps the Genre's the User likes (cause thats the basis of us telling him what he might like further from the given dataset of Movies).

We create a UserProfile in which we multiply the Ratings of the movies he likes into the Genre's of the movies from GenreTable. Creating a list with each genre and showing us his/her prefrence of which genre they like in a descending order.

It will be shown in such a way ->
Adventure             10.0
Animation              8.0
Children               5.5
Comedy                13.5
Fantasy                5.5
Romance                0.0
Drama                 10.0
Action                 4.5
Crime                  5.0
Thriller               5.0
Horror                 0.0
Mystery                0.0
Sci-Fi                 4.5
IMAX                   0.0
Documentary            0.0
War                    0.0


We create a GenreTable of the all the movies we have in the dataset , and working on it we Multiply the genres by the weights and then take the weighted average.
""recommendationTable_df = ((genreTable*userProfile).sum(axis=1))/(userProfile.sum())""

We append the values into a table called as RecommendationTable , which we further sort out in Descending Order.
We locate the RecommendationTable with the given MovieID and give a whole list of the top 20 movies the User may like.


