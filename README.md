# Cricket Data Analytics Project
**Web Scraping | Python | Pandas | Power Bi**

![CDA LOGO](https://github.com/KumarBoste/Cricket_Data_Analytics_Project/blob/main/CDA%20LOGO.png)

## Introduction 
This project aims to perform an end-to-end data analysis on T20 international cricket players. The primary goal was to automate the collection of player statistics from web sources, process and clean the data, and build an interactive Power BI dashboard. This dashboard facilitates the strategic selection of players for a hypothetical "Final 11" team based on their performance metrics, categorized by their playing roles (Power hitters, Anchor, Finisher, All-rounder, Specialist Fast Bowlers).

## Tools & Technologies Used
- Web Scraping & Data Processing: Python
- Python Libraries:
  - pandas - For data manipulation and analysis.
  - requests & BeautifulSoup (or Selenium) - For web scraping and parsing HTML content.
- Data Visualization & Reporting: Microsoft Power BI
- Version Control: Git (Optional, but recommended)

## Methodology
The project was executed in three distinct phases:
#### Phase 1: Data Acquisition (Web Scraping)
- Source: Cricket statistics websites (e.g., ESPN Cricinfo, ICC Official Site).
- Process: A Python script was developed to scrape tabular data containing player performance metrics. The scraped data included:
  - Player Demographics: Name, Team, Batting Style, Bowling Style.
  - Batting Metrics: Innings Batted, Runs, Batting Average, Strike Rate.
  - Bowling Metrics: Innings Bowled, Wickets, Economy, Bowling Strike Rate.
- Output: Raw data files (likely in CSV or JSON format) for further processing.

#### Phase 2: Data Wrangling & Transformation
The raw, scraped data was often messy and inconsistent. Using the pandas library, the following data cleaning steps were performed:
- Handling Missing Values: Identified and filled or dropped null values in critical columns.
- Data Type Conversion: Ensured numerical fields (like Runs, Strike rate) were stored as integers or floats, and text fields were stored as strings.
- Standardizing Values: Corrected inconsistencies in team names, player names, and bowling styles (e.g., "Right hand Bat" vs. "RHB").
- Feature Engineering: Created new, meaningful columns or tables to categorize players, as evidenced by your files:
  - All Rounders / Lower Middle Order: Players with significant contributions in both batting and bowling.
  - Anchors / Middle Order: Players known for stabilizing the innings (likely high batting average).
  - Power Hitters : Who Batting with highest strike rate.
  - Finishers / Lower Order Anchor: Players who accelerate scoring at the end of an innings (likely high strike rate).
  - Specialist Fast Bowler : Bowling specialist in death overs and in pressure.
- Data Integration: Combined data from different scraping sessions into a unified, analysis-ready dataset.

#### Phase 3: Data Visualization & Dashboard Creation
The cleaned and transformed data was loaded into Power BI to create an interactive dashboard. Based on the provided image files, the dashboard includes:
- Role-Based Analysis: Tabs or sections dedicated to All-Rounders, Anchors, and Finishers, allowing for a focused comparison of players within a specific role.
- Player Comparison Metrics: Key Performance Indicators (KPIs) like Batting Average, Strike Rate, Economy Rate, and Bowling Strike Rate are displayed for easy comparison.
- "Final 11" Team Builder: A core feature of the dashboard is an interactive team selector. This allows users to:
  - Search and filter players.
  - Assign a custom batting order.
  - View the aggregate team performance metrics (like overall Team Batting Avg., Team Economy, etc.) that update in real-time as players are selected.
 
  ## 4. Key Findings & Insights
(This section will be greatly enhanced once you share the dashboard image. For now, here are hypothetical insights based on the data files.)
All-Rounders: Sikandar Raza (Zimbabwe) stands out with the highest runs (219) in this category, while Shadab Khan (Pakistan) has taken the most wickets (11). Rashid Khan (Afghanistan) boasts the best bowling economy (6.42) among the listed all-rounders.
Anchors: The data suggests a focus on top-order batters from teams like India and New Zealand, who are crucial for building a solid innings foundation(like Virat Kohli).
Finishers: Players like Glenn Maxwell (Australia) and Marcus Stoinis (Australia) show a very high strike rate (>160), confirming their role as aggressive finishers. Hardik Pandya (India) also plays a key finishing role while providing a vital bowling option.
Team Balance: The "Final 11" feature demonstrates that a balanced team requires a mix of these roles—anchors to stabilize, all-rounders for flexibility, and finishers to maximize the final overs.

## 5. Challenges & Solutions
- Challenge 1: Dynamic Web Content.
  - Solution: Utilized advanced scraping tools like Selenium to handle JavaScript-rendered content on modern sports websites.
- Challenge 2: Inconsistent Data Formatting.
  - Solution: Implemented robust data cleaning pipelines in pandas using string manipulation and conditional logic to standardize player names and statistics.
- Challenge 3: Defining Player Roles Algorithmically.
  - Solution: Combined domain knowledge of cricket with statistical thresholds (e.g., a player with >X wickets and >Y runs is an all-rounder) to create the role categories.
 
  ## Conclusion
This project successfully demonstrates the power of data analytics in sports. By building an automated pipeline from data collection to an interactive dashboard, it transforms raw cricket statistics into actionable insights. The final Power BI dashboard serves as a powerful tool for fans, analysts, and team selectors to make data-informed decisions about player selection and team composition for T20 cricket.

## Future Work
- Incorporate Real-Time Data: Schedule the Python scripts to run periodically (e.g., using cron jobs or Apache Airflow) to keep the dashboard updated with live match data.
- Advanced Metrics: Integrate more sophisticated metrics like "Player Impact Score," "Pressure Handling Index," or predictive analytics for player performance.
- Opposition Analysis: Add a feature to analyze player performance against specific opposing teams or in certain conditions (home vs. away).
- Dashboard Enhancement: Include more interactive filters, such as filtering by tournament, date range, or specific opponent.

##  Project Structure
```text
cricket-data-analytics/
│
├── scripts/
│   ├── data_scraper.py          # Web scraping scripts
│   ├── data_processor.py        # Data cleaning & processing
│   ├── role_analyzer.py         # Player role classification
│   └── utils.py                 # Utility functions
│
├── data/
│   ├── raw/                     # Raw scraped data
│   ├── processed/               # Cleaned data files
│   └── final/                   # Analysis-ready datasets
│
├── dashboards/
│   ├── cricket_team_builder.pbix    # Main Power BI dashboard
│   ├── power_hitters_analysis.pbix  # Power hitters dashboard
│   ├── specialist_bowlers.pbix      # Bowlers analysis dashboard
│   └── assets/                 # Dashboard images & resources
│
├── docs/
│   ├── project_report.pdf       # Detailed project documentation
│   └── dashboard_guide.md       # Dashboard usage guide
│
├── requirements.txt
├── main.py                      # Main execution script
└── README.md
```
