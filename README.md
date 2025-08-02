# 🕷️ Freelancer Job Scraper – Python Developer Focus

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

This Python script automatically scrapes job postings from [Freelancer.com](https://www.freelancer.com/) with a strong focus on Python development roles. It is designed to assist freelancers, data analysts, or automation engineers in finding relevant Python-related gigs that are not urgent, not hourly, and above a minimum price threshold.

---

## 🔍 Features

- ✅ Searches for jobs containing Python-specific keywords
- ✅ Filters out jobs that are too urgent or hourly-based
- ✅ Skips jobs below a defined minimum budget (default: $9)
- ✅ Collects and saves:
  - Job title, link, price, timestamp
  - Full job description
- ✅ Saves all results to structured CSV files in the `/data` directory
- ✅ Automatically avoids duplicate links
- ✅ Runs on an infinite loop with a pause between scraping sessions

---

## 📁 Output Directory Structure

```

project/
│
├── data/
│   ├── pending\_links\_YYYY-MM-DD.csv     ← List of filtered job links
│   └── job\_details\_YYYY-MM-DD.csv       ← Full descriptions of each job
├── main.py                              ← Your Python script
└── README.md

````

---

## 🛠️ Installation

1. Clone this repository or copy the script locally.
2. Install the required libraries:

```bash
pip install requests beautifulsoup4
````

---

## 🚀 How to Run

Simply execute:

```bash
python main.py
```

The script will:

* Scrape the first 5 pages of job listings on Freelancer.com
* Store filtered job links in a CSV file
* Extract job descriptions and save them in a separate CSV
* Repeat the entire process every **5 minutes**

You can stop the process manually by pressing `Ctrl + C`.

---

## 🧠 Filtering Logic

| Criteria      | Rule                                                                   |
| ------------- | ---------------------------------------------------------------------- |
| 🔑 Keywords   | Must contain relevant Python terms like `django`, `web scraping`, etc. |
| ⏱️ Deadline   | Must **not** contain phrases like `urgent`, `asap`, `in 1 hour`, etc.  |
| 💲 Budget     | Minimum of **\$9**, hourly jobs are excluded                           |
| ✅ Relevance   | Uses case-insensitive search through job title and price text          |
| 🚫 Duplicates | Skips links already saved in previous CSV files                        |

---

## 📦 Output CSV Example

### `pending_links_2025-08-02.csv`

| title                | client\_price | link                                                                             | timestamp  |
| -------------------- | ------------- | -------------------------------------------------------------------------------- | ---------- |
| Build Python scraper | \$50          | [https://freelancer.com/projects/abc123](https://freelancer.com/projects/abc123) | 1 hour ago |

### `job_details_2025-08-02.csv`

| title                | client\_price | link                                                                             | timestamp  | description                  |
| -------------------- | ------------- | -------------------------------------------------------------------------------- | ---------- | ---------------------------- |
| Build Python scraper | \$50          | [https://freelancer.com/projects/abc123](https://freelancer.com/projects/abc123) | 1 hour ago | I need a script to scrape... |

---

## ⏳ Auto-Loop Behavior

After finishing one complete scraping session (link + detail), the script will:

* Sleep for `300 seconds` (5 minutes)
* Automatically repeat the process

This ensures fresh data is collected regularly.

---

## ⚠️ Disclaimer

* Do not use this tool for spamming or scraping against Freelancer.com's terms.
* This is intended for **educational**, **research**, and **personal productivity** use only.
* Respect `robots.txt` and terms of service of any website you scrape.

---

## 📅 Author & License

Created by **Art Matic Studio** – \[[ sumberagungabadijaya05@gmail.com]( mina120trf@gmail.com)]
Licensed under the **MIT License**. See [`LICENSE`](./LICENSE) file for full details.

```
