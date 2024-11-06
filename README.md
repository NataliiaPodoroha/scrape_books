# Scrape Books Project

Educational project – an introduction to the Scrapy library. This project scrapes data from the ["Books to Scrape" website](https://books.toscrape.com/), aiming to extract detailed information on each of the 1000 books listed.

## Data Collected

For every book, the following information is extracted:

- **Title**
- **Price**
- **Amount in Stock**
- **Rating**
- **Category**
- **Description**
- **UPC** (Universal Product Code)

## Implementation

The scraping is performed using the Scrapy framework with a single spider, ensuring efficient and organized data collection.

### Steps:

#### 1. Parsing Categories
- The spider starts by fetching all category links from the homepage.
- It initiates requests to parse each category.

#### 2. Parsing Books in Categories
- For each category, it extracts links to individual books.
- Handles pagination to navigate through all pages in a category.
- Sends requests to parse each book's details.

#### 3. Parsing Individual Book Details
- Visits each book's detail page.
- Extracts all required information listed above.
- Maps textual ratings (e.g., "Three") to numerical values.

## How to Run

To execute the spider and gather data:

### Prerequisites
- Ensure Scrapy is installed.
- Navigate to the project's root directory where `scrapy.cfg` is located.

### Command

```bash
scrapy crawl books -o books.jl -s FEED_EXPORT_ENCODING='utf-8'
