# Steam-Top-100-Played-Games

This project is a Python application that creates an interactive dashboard using Dash and Plotly Express to visualize and analyze the "Steam Top 100 Played Games" dataset. The dashboard provides insights into game genres, prices, and player statistics.

### Code Organization

The code is organized into four main sections:

#### 1. Import Libraries
- **pandas**: For data manipulation and cleaning.
- **plotly.express**: For creating interactive and themed visualizations.
- **dash, dash_core_components, dash_html_components**: For building the interactive web application.
- **collections.Counter**: For counting occurrences of genres.

#### 2. Load and Clean Dataset
- **Loading Data**: The dataset is loaded from a CSV file.
- **Data Cleaning**:
  - **Price**: Converts `Free To Play` to `0.0`, removes the `£` symbol, and converts values to float.
  - **Current Players & Peak Today**: Removes commas from numeric strings and converts them to integers.
  - **Genre Tags**: Splits the genre tags into lists by comma, removes the `+` symbol and extra spaces, and filters out empty strings.

#### 3. Analyze Dataset
- **Genre Tags Analysis**:
  - Counts the frequency of each genre across the dataset using `Counter`.
  - Creates a DataFrame (`genre_df`) and extracts the top 10 genres (`top_genres`).
- **Analysis of Top Genre Tags and Game Price**:
  - Explodes the genre tags and computes the average game price per genre.
  - Filters to include only the top 10 genres and sorts by average price in descending order.
- **Analysis of Top Genre Tags and Peak Today**:
  - Computes the average `Peak Today` value per genre.
  - Filters to include only the top 10 genres and sorts by average `Peak Today` in descending order.
- **Top 10 Free and Paid Games by Peak Today**:
  - Identifies the top 10 free games (`Price = 0`) and top 10 paid games (`Price > 0`) based on `Peak Today`.
- **Top Genres in Free and Paid Games**:
  - Filters free and paid games separately.
  - Counts genre occurrences in each subset and extracts the top 10 genres for free and paid games.

#### 4. Visualization and Create a Dash App
The visualizations are created using Plotly Express with a dark theme and arranged in the following sequence:

- **Top Genre Tags**: A bar chart of the top 10 overall game genres.
- **Top Genre Tags and Game Price**: A bar chart showing the average game price per top genre.
- **Top Genre Tags and Peak Today**: A bar chart displaying the average `Peak Today` value per top genre.
- **Distribution of Genre Tags**: A histogram illustrating the distribution of game counts across genres.
- **Top Genres in Free Games**: A bar chart of the top 10 genres in free games.
- **Top Genres in Paid Games**: A bar chart of the top 10 genres in paid games.
- **Top 10 Free to Play Games by Peak Today**: A bar chart for the free games with the highest peak player counts.
- **Top 10 Paid Games by Peak Today**: A bar chart for the paid games with the highest peak player counts.
- **Distribution of Current Players by Game Price**: A histogram aggregating current players by price.
- **Relationship Between Price and Current Players**: A scatter plot with marginal histograms and a rug plot to show the correlation between price and current players.

### Choice of Visualization Types
- **Bar Charts**: Used for categorical comparisons (e.g., genre popularity, price, and player count). Bar charts are ideal for clearly showing the differences in frequency and averages across categories.
- **Histograms**: Used for distribution analysis (e.g., genre distribution, player distribution by price). Histograms provide insights into how values are spread across different categories.
- **Scatter Plots with Marginal Histograms**: Used for correlation analysis (e.g., price vs. current players). This visualization effectively highlights outliers and patterns in relationships between numerical features.

Finally, all these visualizations are integrated into a Dash application with a dark theme. The app layout is defined using Dash components and runs in debug mode for development.
