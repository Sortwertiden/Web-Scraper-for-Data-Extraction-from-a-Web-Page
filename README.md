# Web-Scraper-for-Data-Extraction-from-a-Web-Page
Use BeautifulSoup to extract data from a web page.
from bs4 import BeautifulSoup
import requests

def web_scraper(url):
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    # For example, extract headlines
    headlines = soup.find_all('h2', class_='news-headline')
    for idx, headline in enumerate(headlines):
        print(f"News {idx + 1}: {headline.text}")

url = input("Enter the URL to scrape: ")
web_scraper(url)
