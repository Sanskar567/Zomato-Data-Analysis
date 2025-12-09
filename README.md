# Zomato Data Analysis Project

## Project Overview
This notebook performs an exploratory data analysis (EDA) on a dataset containing information about restaurants listed on Zomato. The goal is to understand various aspects of the restaurant data, including ratings, votes, cost for two people, and online order availability, based on the type of restaurant.

## Dataset
The dataset used is `Zomato-data-.csv`, which includes the following columns:
- `name`: Name of the restaurant
- `online_order`: Whether online ordering is available (Yes/No)
- `book_table`: Whether table booking is available (Yes/No)
- `rate`: Rating of the restaurant (e.g., '4.1/5')
- `votes`: Number of votes received
- `approx_cost(for two people)`: Approximate cost for two people
- `listed_in(type)`: Type of restaurant (e.g., 'Buffet', 'Cafes', 'Dining')

## Analysis Steps
1.  **Data Loading and Initial Inspection**: The dataset was loaded into a pandas DataFrame, and the first few rows were inspected using `data.head(10)`.
2.  **Data Cleaning - Rate Column**: The `rate` column was cleaned by extracting the numerical part and converting it to a float. For example, '4.1/5' became '4.1'.
3.  **Data Information and Null Check**: `data.info()` was used to check data types and non-null counts, and `data.isnull().sum()` confirmed no missing values.
4.  **Restaurant Type Distribution**: A count plot visualized the distribution of different restaurant types (`listed_in(type)`).
    *   **Insight**: 'Dining' restaurants are the most numerous in the dataset.
5.  **Votes by Restaurant Type**: A line plot showed the total number of votes received by each restaurant type.
    *   **Insight**: 'Dining' restaurants garnered the highest number of votes, followed by 'other' types and 'Cafes'.
6.  **Restaurant with Maximum Votes**: The restaurant with the highest number of votes was identified.
    *   **Insight**: 'Empire Restaurant' received the maximum votes (4884).
7.  **Online Order Distribution**: A count plot illustrated the distribution of restaurants offering online orders ('Yes' vs. 'No').
    *   **Insight**: A significant number of restaurants do not offer online ordering, which was highlighted by customizing the bar colors.
8.  **Ratings Distribution**: A 2D histogram (heatmap) was generated to show the distribution of ratings across different ranges of votes.
    *   **Insight**: This plot helps visualize how ratings are clustered with respect to the number of votes.
9.  **Approximate Cost Distribution**: A count plot showed the distribution of approximate costs for two people.
    *   **Insight**: The most common approximate costs for two people fall within certain ranges, such as 300, 400, 600, and 800.
10. **Online Order Availability by Restaurant Type**: A heatmap was created using a pivot table to visualize the count of online/offline orders for each restaurant type.
    *   **Insight**: 'Dining' restaurants have a high count for both 'No' online orders and 'Yes' online orders. 'Cafes' show a higher count for 'Yes' online orders compared to 'No'.

## Key Findings
- **Dining restaurants dominate** in both quantity and total votes received.
- **'Empire Restaurant' is highly popular** based on the number of votes.
- **Online ordering is not universally adopted**, with a substantial number of restaurants not offering it.
- There are **popular price points** for dining, with several cost brackets frequently appearing.
- The **heatmap of online orders by restaurant type** provides a clear picture of which types of restaurants are more likely to offer online services or primarily rely on walk-in/dine-in customers.
