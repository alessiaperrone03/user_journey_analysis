# User Journey Analysis

This project analyzes user journey data to derive valuable insights into user behavior. The analysis includes various functions to explore the most common page visits, page combinations, destinations, and overall journey lengths. The data used is a CSV file containing user journeys, with each entry representing a sequence of pages visited by a user.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Functions](#functions)
3. [Example Usage](#example-usage)
4. [Setup](#setup)

## Project Overview

This project is designed to help analyze user journeys from a website or application. It identifies frequent page visits, the most common sequences of page combinations, and calculates the average journey length. The analysis can be filtered based on user subscription plans (All, Monthly, Quarterly, Annual) to derive insights specific to different user segments.

## Data

The data file `user_journey.csv` should be placed in the same directory as the script. It is expected to contain a column `user_journey`, which holds the sequences of pages visited by each user.

## Functions

### `page_count(data, plan = "All", sort = True)`
Counts the total number of occurrences for each page across all user journeys.

#### Parameters:
- `data`: DataFrame containing the user journey data.
- `plan`: Subscription plan to filter by ("All", "Monthly", "Quarterly", "Annual").
- `sort`: Whether to sort results by frequency.

Returns a dictionary with page names as keys and their respective counts as values.

---

### `page_presence(data, plan = "All", sort = True)`
Identifies the presence of pages in user journeys and counts how many times each page is visited.

#### Parameters:
- `data`: DataFrame containing the user journey data.
- `plan`: Subscription plan to filter by ("All", "Monthly", "Quarterly", "Annual").
- `sort`: Whether to sort results by frequency.

Returns a dictionary with page names as keys and the count of how many times each page is visited.

---

### `page_destinations(data, plan = "All", sort = True)`
Identifies the destination pages (last pages in the user journeys) and counts their occurrences.

#### Parameters:
- `data`: DataFrame containing the user journey data.
- `plan`: Subscription plan to filter by ("All", "Monthly", "Quarterly", "Annual").
- `sort`: Whether to sort results by frequency.

Returns a dictionary with destination page names as keys and their respective counts as values.

---

### `page_sequences(data, number_of_pages = 3, show_results = 10, plan = "All", sort = True)`
Finds the most frequent sequences of consecutive pages visited in user journeys.

#### Parameters:
- `data`: DataFrame containing the user journey data.
- `number_of_pages`: The number of consecutive pages to consider as a sequence.
- `show_results`: The number of top sequences to display.
- `plan`: Subscription plan to filter by ("All", "Monthly", "Quarterly", "Annual").
- `sort`: Whether to sort results by frequency.

Returns a dictionary with page combinations as keys and their respective counts as values.

---

### `avg_journey_length(data, plan = "All")`
Calculates the average length of user journeys, defined by the number of pages visited.

#### Parameters:
- `data`: DataFrame containing the user journey data.
- `plan`: Subscription plan to filter by ("All", "Monthly", "Quarterly", "Annual").

Returns a float representing the average journey length.

## Example Usage
python
Copy
Edit
import pandas as pd

# Load the user journey data
data = pd.read_csv('user_journey.csv')

# Check page count
print(page_count(data, plan = "All", sort = True))

# Check page presence
print(page_presence(data, plan = "All", sort = True))

# Check page destinations
print(page_destinations(data, plan = "All", sort = True)['Homepage'])

# Check top 10 page sequences
print(page_sequences(data, number_of_pages = 3, show_results = 10, plan = "All", sort = True))

# Check average journey length
print(avg_journey_length(data, plan = "All"))

## Setup

To run this project, you'll need to have Python installed, along with the following libraries:

- pandas
- warnings

You can install these dependencies using pip:

  ```bash
  pip install pandas
