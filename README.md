# Article Scraper

This repository contains scripts and configuration for scraping the latest articles from Ledger Insights and Blockworks websites, and appending the data to a single CSV file. The notebook ensures that the CSV file is not overwritten but appended with new data. This project is designed to be run on a weekly basis for research purposes.

## Files in this Repository

### 1. `article_scraper.ipynb`
This Jupyter Notebook combines the scrapers for Ledger Insights and Blockworks, leveraging Selenium and BeautifulSoup to extract article data such as headlines, links, and publication dates. The notebook is structured with markdown cells for easy reading and understanding of the code.

### 2. `config.json`
This JSON file contains configuration parameters used by the scraper scripts. It includes paths, URLs, keywords, and other settings necessary for running the scrapers.

{
    "webdriver_path": "C:/Program Files/chromedriver-win64/chromedriver.exe",
    "ledger_insights_url": "https://www.ledgerinsights.com/tokenization/",
    "blockworks_url": "https://blockworks.co/search",
    "keywords": ["digital assets", "digital securities", "tokenized", "tokenization", "bond", "security", "asset", "token"],
    "searchword": "tokeniz",
    "num_clicks_li": 20,
    "num_clicks_bw": 20,
    "csv_file_path": "scraped_articles.csv"
}

### 3. `scraped_articles.csv`
This CSV file contains the output of the scrapers. It includes columns for headlines, links, and publication dates. The file is appended with new data each time the scrapers are run.

## Requirements

To run the scrapers, you will need the following:

- Python 3.6 or higher
- Jupyter Notebook
- Google Chrome and ChromeDriver
- Required Python packages: `selenium`, `beautifulsoup4`, `pandas`

## Setup Instructions

### Install Google Chrome and ChromeDriver:

1. Download and install Google Chrome from [here](https://www.google.com/chrome/).
2. Download ChromeDriver from [here](https://sites.google.com/a/chromium.org/chromedriver/downloads) and place it in the path specified in `config.json`.

### Clone the Repository:

```sh
git clone https://github.com/suni639/article_web_scraper_v2
cd article_scraper

## Update Configuration:

Ensure the paths and parameters in `config.json` are correct before running the scrapers.

## How to Use

### Configure `config.json`:

1. Update the `webdriver_path` to the correct location of ChromeDriver on your system.
2. Ensure URLs for Ledger Insights and Blockworks are correct.
3. Modify keywords and other parameters as necessary.

### Run the Notebook:

1. Open `article_scraper.ipynb` in Jupyter Notebook.
2. Execute the cells in sequence to run the scrapers and append data to `scraped_articles.csv`.

### Review Scraped Data:

The scraped articles will be appended to `scraped_articles.csv` with columns for headlines, links, and publication dates.

## Common Issues

### ChromeDriver Path Issues:

Ensure that the `webdriver_path` in `config.json` points to the correct location of ChromeDriver on your system.

### Dependencies:

Make sure all required Python packages are installed. Use `pip install -r requirements.txt` to install dependencies.
