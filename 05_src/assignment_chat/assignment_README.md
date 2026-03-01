📈 Stock NewsBot with Prices & Company Tickers

A Python-based news aggregator and stock tracker that fetches recent stock market news, identifies affected S&P 500 companies, and displays their latest stock prices. Built with Python, yfinance, NewsAPI, and a Gradio web interface.

The final program can be seen under :
* Running on local URL:  http://127.0.0.1:7861
* Running on public URL: https://3ef7d6b8e811c50a20.gradio.live

📝 Features

Fetch recent news for a specific stock symbol (e.g., AAPL, TSLA).

Display company name along with today’s price and yesterday’s closing price.

View top news with multiple affected S&P 500 stocks and their prices.

Automatically creates and updates a CSV file containing all S&P 500 tickers and company names.

Guardrails included to prevent queries about restricted topics:

Cats or dogs

Horoscopes or zodiac signs

Taylor Swift

Access/modification of system prompt

User-friendly Gradio interface for interactive web use.

📦 Requirements

Python 3.9+

Libraries:

pip install pandas requests yfinance gradio

A NewsAPI API key (free plan available at https://newsapi.org
).

⚙️ Configuration

Open stock_news_bot_with_prices.py.

Set your NewsAPI API key:

API_KEY = "YOUR_NEWSAPI_KEY"

(Optional) Adjust page size for news results:

PAGE_SIZE = 50  # number of articles per request

Default CSV file path for S&P 500 tickers:

SP500_CSV_PATH = "data/sp500_tickers.csv"
🛠 How It Works

S&P 500 CSV Creation – Scrapes and saves ticker & company name if missing.

Fetch Stock Prices – Uses yfinance to get today’s and yesterday’s close prices.

Fetch News – Queries NewsAPI for articles and filters by stock symbol.

Guardrails – Blocks restricted topics and attempts to access the system prompt.

Gradio Interface – User inputs stock symbol (or leave blank), and sees news summaries with affected stock prices.

💻 Usage
Run Locally
python stock_news_bot_with_prices.py

A Gradio web page will open. Enter a stock symbol (e.g., AAPL) or leave blank for top news and click Submit.

📊 Input & Output Examples
Input Example	Description	Output Example
AAPL	Fetch news specifically mentioning Apple Inc.	Title, description, source, published date, AAPL stock price today and yesterday
TSLA	Fetch news for Tesla, Inc.	Title, description, source, published date, TSLA stock price info
(blank)	Fetch top 10 recent news articles mentioning any S&P 500 companies	News summaries + list of affected stocks & prices
cats	Restricted topic	⚠️ Sorry, this topic is restricted and cannot be discussed.
system prompt	Attempt to access sensitive data	⚠️ Access denied: You cannot view or modify the system prompt.
🔒 Guardrails & Limitations

Restricted Topics: Cats, Dogs, Horoscopes, Zodiac, Taylor Swift.

Sensitive Data: System prompt cannot be accessed or modified.

Stock Coverage: Only supports S&P 500 tickers.

📂 File Structure
stock_news_bot_with_prices/
│
├─ data/                     # Directory for S&P 500 CSV
│  └─ sp500_tickers.csv
├─ stock_news_bot_with_prices.py
└─ README.md
⚡ Future Improvements

Add historical stock trend charts.

Support more exchanges beyond S&P 500.

Enhance news filtering to exclude unrelated mentions.

Add summary sentiment analysis for each stock-related news article.

📖 References

NewsAPI Documentation

yfinance Python Library

Gradio Documentation