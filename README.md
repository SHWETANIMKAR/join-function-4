# Pandas Join Function - Join Function 4

This project demonstrates different types of JOIN operations in Pandas using Movie Details and Movie Ratings tables.

## Code Overview

### Creating Two Tables
import pandas as pd

# Table 1: Movie details
movies = pd.DataFrame({
    "Genre": ["Drama", "Action", "Comedy", "Thriller"],
    "Year": [2016, 2023, 2009, 2022]
}, index=["Dangal", "Jawan", "3 Idiots", "Drishyam"])

# Table 2: Movie ratings
ratings = pd.DataFrame({
    "Rating": [8.4, 7.0, 8.4, 8.2],
    "Votes": [2000, 1500, 1800, 1200]
}, index=["Dangal", "Jawan", "PK", "Drishyam"])

print("MOVIES TABLE")
print(movies)

print("\nRATINGS TABLE")
print(ratings)

### Output
MOVIES TABLE
             Genre  Year
Dangal       Drama  2016
Jawan       Action  2023
3 Idiots    Comedy  2009
Drishyam  Thriller  2022

RATINGS TABLE
          Rating  Votes
Dangal       8.4   2000
Jawan        7.0   1500
PK           8.4   1800
Drishyam     8.2   1200

## Types of Join Performed

### 1. Left Join
print(movies.join(ratings, how='left'))

Output:
          Genre  Year  Rating  Votes
Dangal    Drama  2016     8.4  2000.0
Jawan    Action  2023     7.0  1500.0
3 Idiots Comedy  2009     NaN     NaN
Drishyam Thriller 2022    8.2  1200.0

Left table ka sara data rahega, match nahi hua to NaN.

### 2. Right Join
print(movies.join(ratings, how='right'))

Output:
          Genre    Year  Rating  Votes
Dangal    Drama  2016.0     8.4   2000
Jawan    Action  2023.0     7.0   1500
Drishyam Thriller 2022.0    8.2   1200
Pathaan     NaN     NaN     7.8    900

Right table ka sara data rahega.

### 3. Inner and Outer Join
print(movies.join(ratings, how='inner'))
# Sirf common movies - Dangal, Jawan, Drishyam

print(movies.join(ratings, how='outer'))
# Dono tables ka sara data - Dangal, Jawan, 3 Idiots, Drishyam, PK, Pathaan

## Key Concepts
- join() function index ke basis par tables ko jodta hai
- how='left' - left ka pura data
- how='right' - right ka pura data
- how='inner' - dono me jo common hai
- how='outer' - dono ka sara data

## Library Used
- pandas
- Jupyter Notebook

## Author
SHWETA NIMKAR
