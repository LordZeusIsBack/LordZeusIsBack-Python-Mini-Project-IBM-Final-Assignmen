# Analyzing Historical Stock/Revenue Data and Building a Dashboard

This project is part of the IBM Professional Data Science Certificate offered by Coursera. The goal is to analyze historical stock and revenue data of Tesla and GameStop, and visualize it through a dashboard. The project involves extracting stock data using the `yfinance` library, web scraping revenue data, and plotting the data using the `plotly` library.

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
- [Data Extraction](#data-extraction)
- [Visualization](#visualization)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
This project focuses on:
- Extracting stock data using the `yfinance` library.
- Web scraping revenue data.
- Visualizing the extracted data using `plotly` to create an interactive dashboard.

## Installation
To run this project, you'll need to install the following Python libraries:

```bash
pip install yfinance==0.2.38
pip install pandas==2.2.2
pip install plotly
pip install beautifulsoup4
pip install requests

## Usage
1. Clone this repository.
2. Install the required libraries using the commands listed in the Installation section.
3. Run the Jupyter Notebook file `Final Assignment.ipynb`.

## Functions

### `make_graph(stock_data, revenue_data, stock)`
This function generates a dashboard with two subplots:
- Historical Share Price
- Historical Revenue

**Parameters:**
- `stock_data` (DataFrame): DataFrame containing stock data with columns 'Date' and 'Close'.
- `revenue_data` (DataFrame): DataFrame containing revenue data with columns 'Date' and 'Revenue'.
- `stock` (str): Name of the stock.

## Data Extraction
The data extraction process is divided into two main tasks:

1. **Extract Stock Data using yfinance**

Example:
```python
import yfinance as yf

# Extracting Tesla stock data
tesla = yf.Ticker("TSLA")
tesla_data = tesla.history(period="max")
tesla_data.reset_index(inplace=True)

# Extracting GameStop stock data
gme = yf.Ticker("GME")
gme_data = gme.history(period="max")
gme_data.reset_index(inplace=True)
```

2. **Web Scrape Revenue Data**

Example:
```python
import requests
from bs4 import BeautifulSoup

# Web scraping Tesla revenue data
tesla_url = "URL_CONTAINING_TESLA_REVENUE_DATA"
tesla_html_data = requests.get(tesla_url).text
tesla_soup = BeautifulSoup(tesla_html_data, "html.parser")
# Parse the data as required

# Web scraping GameStop revenue data
gme_url = "URL_CONTAINING_GME_REVENUE_DATA"
gme_html_data = requests.get(gme_url).text
gme_soup = BeautifulSoup(gme_html_data, "html.parser")
# Parse the data as required
```

## Visualization
The visualization part involves using the `make_graph` function to plot the stock and revenue data. The plots are interactive and provide insights into the historical performance of Tesla and GameStop.

## Results
The project generates a comprehensive dashboard displaying the historical stock prices and revenue data for Tesla and GameStop, enabling a clear understanding of their financial performance.

## Contributing
If you'd like to contribute to this project, please fork the repository and use a feature branch. Pull requests are warmly welcome.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
```

This `README.md` should cover all the necessary details to understand and run the project. If there are specific URLs or additional details in the Jupyter Notebook that need to be included, you can modify the placeholders accordingly.
