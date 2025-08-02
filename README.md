# 🕷️ Freelancer Job Scraper (Python-Focused)

This Python script scrapes recent job postings from [Freelancer.com](https://www.freelancer.com/) with a focus on **Python development** work. It filters listings based on relevancy, urgency, and budget, then saves the job links and full descriptions into structured CSV files for further analysis or automation purposes.

---

## 🔍 Features

- Scrapes latest jobs from multiple pages (default: 5 pages).
- Filters listings using:
  - Python-related keywords
  - Reasonable deadlines (excludes “urgent” jobs)
  - Minimum budget threshold ($9)
  - Excludes hourly jobs
- Stores data in two stages:
  - `pending_links_<DATE>.csv` — titles, links, prices
  - `job_details_<DATE>.csv` — full job descriptions
- Avoids duplicate entries.
- Designed to run continuously with a 5-minute delay between cycles.

---

## 📁 Directory Structure

```bash
project/
│
├── data/
│   ├── pending_links_YYYY-MM-DD.csv
│   └── job_details_YYYY-MM-DD.csv
├── main.py  # (or your filename)
└── README.md
````

---

## ⚙️ Requirements

Install required Python libraries (if not already):

```bash
pip install requests beautifulsoup4
```

---

## 🚀 Usage

Run the script from the terminal:

```bash
python main.py
```

The script will:

1. Scrape job listings from `freelancer.com/jobs`.
2. Filter and save relevant job links.
3. Scrape detailed job descriptions for each saved link.
4. Save results in the `data/` folder.

The script loops indefinitely, scraping every 5 minutes.

---

## 🎯 Filtering Logic

* **Keywords**: Filters by relevant Python-related terms like `python`, `django`, `web scraping`, etc.
* **Urgency**: Skips jobs with terms like `urgent`, `asap`, `within 1 hour`, etc.
* **Budget**: Requires a minimum fixed-price budget of **\$9** (excludes hourly jobs).
* **Duplicate Handling**: Only saves new job links that have not been recorded before.

---

## 📦 Output Example

### pending\_links\_YYYY-MM-DD.csv

| title                    | client\_price | link                                                                    | timestamp  |
| ------------------------ | ------------- | ----------------------------------------------------------------------- | ---------- |
| Build Python web scraper | \$50          | [https://freelancer.com/projects/](https://freelancer.com/projects/)... | 1 hour ago |

### job\_details\_YYYY-MM-DD.csv

| title                    | client\_price | link                                                                    | timestamp  | description                                              |
| ------------------------ | ------------- | ----------------------------------------------------------------------- | ---------- | -------------------------------------------------------- |
| Build Python web scraper | \$50          | [https://freelancer.com/projects/](https://freelancer.com/projects/)... | 1 hour ago | I need a Python script to scrape product prices from ... |

---

## 🛑 Notes

* **Do not abuse** the site. Use reasonable intervals and respect Freelancer.com's [Terms of Service](https://www.freelancer.com/about/terms).
* This is intended for **educational** and **internal productivity** use only.

---

## 📅 Author & License

Created by \[Your Name].
Licensed under the MIT License.

```
