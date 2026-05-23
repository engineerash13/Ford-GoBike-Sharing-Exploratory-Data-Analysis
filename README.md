# Ford GoBike Sharing: Exploratory Data Analysis

An individual EDA project analyzing Ford GoBike (now Lyft Bikes) trip data from the San Francisco Bay Area. The project uncovers user behavior patterns, temporal trends, station demand, and gender-based usage differences — with actionable business recommendations for optimizing bike-sharing operations.

**Author:** Ashwin Suryawanshi | **Type:** Individual Project

---

## Files in This Repository

| File | Description |
|------|-------------|
| `Ford Go Bike Sharing Project.ipynb` | Full EDA notebook — data wrangling, 12 Plotly/Seaborn charts, business recommendations |

---

## Tools & Technologies

- **Python** — Pandas, NumPy
- **Visualization** — Plotly Express, Plotly Graph Objects, Matplotlib, Seaborn
- **Jupyter Notebook** — Google Colab

---

## Dataset

**Source:** `201812-fordgobike-tripdata.csv` (December 2018)
**Size:** 131,363 rows × 16 columns

| Column | Description |
|--------|-------------|
| `duration_sec` | Trip duration in seconds |
| `start_time` | Timestamp when trip started |
| `end_time` | Timestamp when trip ended |
| `start_station_id` | Unique ID of start station |
| `start_station_name` | Name of start station |
| `start_station_latitude` | Latitude of start station |
| `start_station_longitude` | Longitude of start station |
| `end_station_id` | Unique ID of end station |
| `end_station_name` | Name of end station |
| `end_station_latitude` | Latitude of end station |
| `end_station_longitude` | Longitude of end station |
| `bike_id` | Unique bike identifier |
| `user_type` | Subscriber (member) or Customer (casual) |
| `member_birth_year` | Birth year of user |
| `member_gender` | Male, Female, or Other |
| `bike_share_for_all_trip` | Bike Share for All programme participation (Yes/No) |

---

## Data Wrangling (4 Steps)

| Step | Action |
|------|--------|
| 1 | Dropped rows with nulls in critical columns: `start_station_name`, `start_station_id`, `end_station_name`, `end_station_id`, `member_birth_year`, `member_gender` |
| 2 | Converted `start_time` and `end_time` to datetime objects |
| 3 | Engineered new features: `day_of_week`, `hour_of_day`, `duration_min` (converted from seconds) |
| 4 | Removed outliers in `duration_min` using IQR method (1.5 × IQR threshold) |

---

## Charts (12 total — UBM Framework)

### Univariate Analysis
| # | Chart | Type | Key Finding |
|---|-------|------|-------------|
| 1 | Distribution of trip duration | Histogram + rug plot | Right-skewed — most trips are 5–7 minutes; mean pulled right by longer trips |
| 2 | Bar chart of user types | Bar | Subscribers dominate: 109,746 vs 13,198 Customers |
| 3 | Distribution of member gender | Pie | Males 75.5%, Females 22.9%, Other 1.6% |
| 11 | Bike Share for All trip distribution | Bar | Majority of trips are NOT under the Bike Share for All programme |

### Bivariate Analysis
| # | Chart | Type | Key Finding |
|---|-------|------|-------------|
| 4 | Start hour distribution | Bar (color gradient) | Peak trips at 8 AM (12,952) and 5 PM (12,860) — clear commuter pattern |
| 5 | Top 10 start stations | Horizontal bar | SF Caltrain Station 2 (Townsend St at 4th St) leads with 2,636 trips |
| 6 | Top 10 end stations | Horizontal bar | SF Caltrain Station 2 also top end station with 3,193 trips |
| 7 | Trip duration by user type | Box plot | Customers take longer, more variable trips; Subscribers are shorter and consistent |
| 9 | Trip duration by gender | Violin plot | Females show slightly higher median and longer tails; all genders peak at 5–10 min |
| 10 | Average trip duration by start hour | Line chart | Longest avg trips at 8 AM and 3–5 PM; lowest at 4–6 AM |
| 12 | Trip count by day of week | Bar (color gradient) | Weekdays dominate (18K–20K trips); Sunday is the lowest — commuter-driven usage |

### Multivariate Analysis
| # | Chart | Type | Key Finding |
|---|-------|------|-------------|
| 8 | Trip count by hour and gender | Grouped bar | Males dominate all hours; all genders spike at 8 AM and 5–6 PM commute hours |

---

## Key Insights

- **Commuter-driven usage** — peak hours are 8 AM and 5 PM on weekdays; Sunday has the least trips
- **Subscribers are the core user base** — 109,746 subscribers vs 13,198 casual customers
- **SF Caltrain Station 2** is both the top start (2,636 trips) and top end (3,193 trips) station — transit hub dependency
- **Trip durations are short** — most trips fall between 5–7 minutes after outlier removal
- **Customers take longer trips** than subscribers — likely casual/tourist users vs daily commuters
- **Gender imbalance** — males account for 75.5% of trips; female and "Other" are underserved segments
- **Early morning (3 AM)** sees the lowest activity with only 211 trips
- **Bike Share for All** programme has low adoption — most trips don't use it

---

## Business Recommendations

1. **Subscriber retention** — loyalty programs, renewal discounts, referral incentives to keep the core base
2. **Convert customers to subscribers** — trial passes and onboarding promotions targeting the 13,198 casual users
3. **Dynamic bike rebalancing** — prioritize SF Caltrain Station 2 and Market St stations during 8 AM and 5 PM peaks
4. **Weekend promotions** — "Happy Hour" discounts or event partnerships to close the weekday–weekend usage gap
5. **Female and underrepresented gender outreach** — safety features, targeted campaigns to grow underserved segments
6. **Boost Bike Share for All adoption** — in-app awareness and incentives for eligible low-income users
7. **Monitor underperforming stations** — investigate accessibility or visibility issues at low-traffic docking points

---

## Project Workflow

1. Data loading and initial exploration (shape, dtypes, duplicates, missing values)
2. Variable description and unique value checks
3. Data wrangling — null handling, datetime conversion, feature engineering, outlier removal
4. Exploratory visualization — 12 charts across univariate, bivariate, and multivariate analysis
5. Business recommendations based on findings
6. Conclusion and future directions

---

## Topics

`eda` `python` `plotly` `bike-sharing` `data-analysis` `pandas` `seaborn` `san-francisco` `ford-gobike`
