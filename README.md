# ReadSmart-Personalized-E-Book-Recommendation-System
It currently implements two recommendation strategies:
•Top Rated – Selects the highest-rated books in the chosen genre.
•Similarity Based – Finds books similar to a user’s favorite title using TF-IDF text similarity.

🚀 Features
Filter books by genre and minimum average rating.
Two Recommendation Strategies:
Strategy A: Top-rated books in a chosen genre.
Strategy B: Similar books to a given title (TF-IDF + cosine similarity).
Handles partial title matches to improve search accuracy.
Easily extendable for future integration of A/B testing.

🗂 Dataset
Source: Goodreads Dataset on Kaggle
Columns used:
--book_id – Unique identifier for the book
--title – Book title
--authors – Author(s) of the book
--average_rating – Average Goodreads rating
--genre – Manually added column for book genres

📂 Project Workflow – ReadSmart
1️⃣ Data Collection
Downloaded Goodreads dataset from Kaggle (books.csv).
Selected relevant columns:
title
authors
average_rating
Manually added genre column to classify books into categories (Fantasy, Mystery, Romance, etc.).

2️⃣ Data Preprocessing
Loaded dataset using Pandas.
Checked for missing values and cleaned where necessary.
Converted genre and title values to lowercase for consistent matching.
Ensured average_rating was numeric for filtering.

3️⃣ Strategy A – Top Rated Recommendation
Input: Preferred genre and minimum rating.
Process:
Filter the dataset by chosen genre.
Filter further by average_rating >= min_rating.
Sort results by rating in descending order.
Return the top N highest-rated books.

4️⃣ Strategy B – Similarity-Based Recommendation
Input: Favorite book title and genre.
Process:
Filter the dataset by chosen genre.
Create a text field combining title and authors.
Use TF-IDF Vectorizer to convert text into numerical features.
Compute cosine similarity between all books in that genre.
Recommend the top N most similar books to the input title.

5️⃣ Output
Display recommendations for both strategies:
Strategy A: Table of top-rated books.
Strategy B: Table of similar books.
