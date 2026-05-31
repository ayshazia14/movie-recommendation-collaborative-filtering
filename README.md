# Movie Recommendation System — Collaborative Filtering

A recommendation system that suggests similar movies based on user rating correlations, implementing item-based collaborative filtering using the MovieLens dataset.

---

## Overview

This project builds a correlation-based movie recommendation engine. By constructing a user-movie pivot table from rating data and computing Pearson correlation between movies, the system identifies which films tend to be rated similarly — and recommends them accordingly.

---

## Dataset

**MovieLens Dataset** — loaded from local CSV files (`movie.csv`, `rating.csv`)

| File | Columns Used | Description |
|---|---|---|
| `movie.csv` | `movieId`, `title` | Movie metadata |
| `rating.csv` | `userId`, `movieId`, `rating` | User ratings |

The two files are merged on `movieId`. The notebook uses the first 1,000,000 rows of the merged dataset.

> Download the MovieLens dataset from [GroupLens](https://grouplens.org/datasets/movielens/) and update the file paths in the notebook.

---

## Workflow

1. Load movie and rating CSVs into pandas DataFrames
2. Merge on `movieId` to create a combined dataset
3. Subset to 1,000,000 rows for performance
4. Build a user-movie pivot table (users as rows, movies as columns, ratings as values)
5. Compute Pearson correlation between a selected movie and all others using `corrwith`
6. Sort by correlation score and display the top 10 most similar movies
7. Repeat for a second reference movie (`Bad Boys (1995)`)

---

## Example Output

For **Toy Story (1995)** and **Bad Boys (1995)**, the system returns the top 10 most correlated movies based on shared user rating patterns.

---

## Technologies Used

- Python
- NumPy
- pandas
- matplotlib
- os

---

## How to Run

1. Download the MovieLens CSVs and place them in your working directory.
2. Update the file paths in the notebook:
   ```python
   movie = pd.read_csv("movie.csv")
   rating = pd.read_csv("rating.csv")
   ```
3. Run the notebook:
   ```bash
   pip install numpy pandas matplotlib
   jupyter notebook Task_4.ipynb
   ```
