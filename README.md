# Book_Recommendation_Project
The project simply provides readers to find their next book to read. It asks users to enter how many genres they want and the genres, and gives top 10 read books with genres provided by reader.
## Dataset
The project is based on a dataset scraped via the Goodreads API, created in 2019. The one that I have used updated in 2022 with genre information.
The dataset itself is a bit out-dated, still pretty useful to explore the world of books.
The original dataset can be found on Kaggle through this link: https://www.kaggle.com/datasets/middlelight/goodreadsbookswithgenres

## First Glance to Data
The dataset includes 13 columns and 11030 non-null rows.
The column names are:Book ID, Title, Author, average_rating, isbn, isbn13, language_code, num_pages, ratings_count, text_reviews_count, publication_data, publisher, genres.
_In this project, I haven't used Book ID, isbn, isbn13, publication_data, and publisher columns._

First, I tried to explore the data. I have found NaN values and outliers using pandas methods.
I checked specific columns to see if there were any irregularities. 

 ![a_rating_hist](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/464ec482-11c4-4ece-a41c-d72460851b0f)
 ![num_pages_hist](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/8be57a2e-6de6-4091-8200-1645b9662219)

I got 2 histogram tables belongs to "average_rating" and "num_pages".
There were some irregularities, so I have organized the data accordingly.
 
Furthermore, I have collected some prior information about authors, books, languages they were written. 
Those informations are to provide readers to see the overall picture of bookworms. :) 
They can be observed below:
 
![most-read](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/04b6721b-5117-469e-9150-d48cef8b8e8d)

Apparently, J.R.R. Tolkien and L.K.Rowling are two very popular authors. In general, Harry Potter series seems to be leading.

![most-reviewed](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/b0a4d0cb-b4b7-4025-b7a9-2bfc887c9a1a)

These are some other books with the most reviews.

![authors](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/9cc7d344-a9d1-4fc0-9575-02d0bf4f2809)

Apparently, P.G. Wodehouse and Stephen King are the two most published authors according to this dataset.

![lang](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/9ee47b51-6a43-4a92-9bc8-b970dcbd2676)

Most of the books seems to be published in English. I was pretty sad to see there is only one book with my mothertongue, Turkish.

![corr table](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/009b4025-064d-41c1-9039-f692ef289cd0)

The last table shows the correlation between average rating and rating counts with a highlight of number of test reviews.
Apparently, high rating does not necessarily correlate with rating counts. _After this result, I have decided to use ratings count instead of average rating for top rated books.

## Book Recommendation App

In this part, I first pull all the values from 'genres' column and assign them to a list where every element of the list is unique.
I created a word cloud using that list to show readers what kind of genres there are in a fancy way. It can be seen below:

![wordcloud](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/a088a9af-1f87-4d69-a2b3-89389d67b054)

The application first print out information about its purpose. Then it asks reader/user to select how many genres they want to enter. Second, it asks user to enter genre names. 
If it is not in the unique genres list, program raises and error and asks again. For each genre entry, user has 3 trials.
After user enters selected genres, program finds all the relevant rows that contains all the genres user entered.
Finally, the program provides a list of 10 most rated book based on genres user enters.

For example;

![genres-enteres](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/13b58f44-432f-404f-af20-f8e2bea5ef6f)

Here user asks to enter 3 genres. While typing, s/he makes a mistake. At the end, it can be observed that the user entered fiction, romance, and literature.
Based on these genres, program lists/recommends 10 top rated books.

![books recommended](https://github.com/zeybus/Book_Recommendation_Project/assets/113775433/d077ee14-1031-40a5-bb82-7ef557e8bc1e)

