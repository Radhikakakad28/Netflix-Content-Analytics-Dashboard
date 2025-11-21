📊 Netflix Content Analytics Dashboard (Power BI)

This project is a Power BI dashboard built using the Netflix Movies & TV Shows dataset.
It provides insights into content distribution, ratings, trends over time, and country-wise availability.

🚀 Project Features
✔ 1. Key Metrics

Total Titles

Total Movies

Total TV Shows

G-rated Titles

Adult Content Titles

✔ 2. Visualizations

Area chart showing content added over time

Donut chart for content ratings

Pie chart for Movie vs TV Show distribution

Bar chart for release-year distribution

100% stacked area chart for comparison

World map (optional) for country availability

✔ 3. Theme

Fully styled using a Netflix Red & Black Theme consistent across all visuals.

📂 Project Files
File	Description
netflix_titles.csv	Raw Kaggle dataset
netflix_cleaned.csv	Cleaned dataset with transformed fields
Netflix_Dashboard.pbix	Final Power BI dashboard
dashboard_final.png	Final exported dashboard image
netflix_ultra_red_black_theme.json	Custom Power BI theme
README.md	Documentation file
🧹 Data Cleaning Process

The dataset was cleaned using Python (Pandas):

Converted date_added to datetime format

Split and expanded country column

Removed null values

Saved as a clean dataset ready for Power BI

📌 Code Used (Python)
import pandas as pd

df = pd.read_csv('netflix_titles.csv')
df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')
df['country'] = df['country'].fillna('Unknown').str.split(', ')
df = df.explode('country')
df.to_csv('netflix_cleaned.csv', index=False)

📊 DAX Measures Used
Total Titles = COUNTROWS('netflix_cleaned (1)')

Total Movies =
CALCULATE(
    COUNTROWS('netflix_cleaned (1)'),
    'netflix_cleaned (1)'[type] = "Movie"
)

Total TV Shows =
CALCULATE(
    COUNTROWS('netflix_cleaned (1)'),
    'netflix_cleaned (1)'[type] = "TV Show"
)

G Rated =
CALCULATE(
    COUNTROWS('netflix_cleaned (1)'),
    'netflix_cleaned (1)'[rating] = "G"
)

Adult Content =
CALCULATE(
    COUNTROWS('netflix_cleaned (1)'),
    'netflix_cleaned (1)'[rating] IN {"R","TV-MA","NC-17"}
)

🛠️ Tools Used

Power BI Desktop

Python (Pandas)

Netflix Dataset (Kaggle)

Custom Theme JSON

📸 Dashboard Preview

(Add your final image here)

/screenshots/dashboard_preview.png


⭐ If you like this project, consider giving a star on GitHub!
🧭 3. How to Upload Your Project to GitHub (Step-by-Step)
🔹 Step 1 — Create a new GitHub repository

Go to: https://github.com/new

Repository name:

Netflix-Content-Analytics-Dashboard


Click Create Repository

🔹 Step 2 — Upload Files

Click Add file > Upload files

Upload:

netflix_titles.csv

netflix_cleaned.csv

Netflix_Dashboard.pbix

dashboard_final.png

netflix_ultra_red_black_theme.json

README.md

Click Commit changes

🔹 Step 3 — Add Folders (optional)

GitHub allows uploading folders as ZIP or drag-drop entire folder.

🔹 Step 4 — Post your link on LinkedIn

Example caption:

🚀 Just completed my Netflix Content Analytics Dashboard using Power BI!

This project includes data cleaning in Python, DAX measures, and a custom Netflix-theme dashboard.

🔗 GitHub Repo: <paste_link_here>
📊 Tools: Power BI, Python, Pandas
