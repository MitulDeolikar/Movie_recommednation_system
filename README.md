# Movie_recommednation_system

This system allows the useres to enter their favourite movie and browse similar movies based on the content,cast,genre,director and plot of the movie.

I have made the use of pandas , difflib ,scikit to carry out this project

Cosine Similarity Algorithm helps me find the similarity score between any two movies present in the dataset

//////////////////////////////////////////////////////////////////////////////////////////////////////
movie_name = input(' Enter your favourite movie name : ')

list_of_all_titles = movies_data['title'].tolist()

find_close_match = difflib.get_close_matches(movie_name, list_of_all_titles)

close_match = find_close_match[0]

index_of_the_movie = movies_data[movies_data.title == close_match]['index'].values[0]

similarity_score = list(enumerate(similarity[index_of_the_movie]))

sorted_similar_movies = sorted(similarity_score, key = lambda x:x[1], reverse = True) 

print('Movies suggested for you : \n')

i = 1

for movie in sorted_similar_movies:
  index = movie[0]
  title_from_index = movies_data[movies_data.index==index]['title'].values[0]
  if (i<=10):
    print(i, '.',title_from_index)
    i+=1

The Above code allows user input and suggests the top 10 similar movies based on your interest
