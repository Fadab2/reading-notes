# Web Scrape with Python

<br />

* Web scraping is accessing a website using a software and extracting the needed information.
* Web scrape helps us automate data collection from websites. Instead of clicking and downloading each file for example, we can write a code that does that work in large amount in less time.
* When we web scrape we have to comply the terms and conditions of the websites we are scraping on how to use their service and data collected from them.
* Usually it starts by finding the links to the data you want to scrape.
* We usually need the following library to our program;
```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

```

* We set url of the website we want to scrape to a variable as in `url = '<http://somewebsite.com`
* Then connect to the url using `response = requests.get(url)`
* BeautifulSoup then is used to parse the html.
* New forms of web scraping invovle monitoring data feeds using JSON to transport and store data.
* Some website prevent web scraping by detecting and blocking bots. But some crawling technique simulate human browsing to avoid detection.

## Web scraping techniques history:

 * #### Human copy-and-paste
     * Manually copy/pasting data from web into text files.
* #### Text pattern matching
    * Extracting information from web pages based on the UNIX grep command.
* #### HTTP programming
     * Using HTTP requests to servers using socket programming.

Other examples of scraping include:

#### HTML parsing
#### DOM parsing
#### Vertical aggregation
#### Semantic annotation recognizing
#### Computer vision web-page analysis.

## Web Scraping best practice
If you don't follow a website's terms and policies of crawling you might get blocked.
* Follow website's crawling policies
* Robots.text has good practice that should be respected.
* Make the crawling slower.
* Do not follow the same crawling pattern.
* Make requests through Proxies and rotate them as needed
* Rotate User Agents and corresponding HTTP Request Headers between requests
* Use a headless browser like Puppeteer, Selenium or Playwright
* Beware of Honey Pot Traps
* Check if Website is Changing Layouts
* Avoid scraping data behind a login
* Use Captcha Solving Services


<br />

## References

[How to Web Scrape with Python in 4 Minutes](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

[Web scraping](https://en.wikipedia.org/wiki/Web_scraping)

[Web Scraping best practices to follow](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)


<br />

## [<-- Back](README.md)
