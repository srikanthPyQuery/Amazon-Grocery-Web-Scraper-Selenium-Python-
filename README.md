# Amazon-Grocery-Web-Scraper-Selenium-Python-
Automated Amazon.Grocery Web Scraper using Selenium — extracts product names, prices, ratings, and number of reviewers across multiple pages, then cleans and pre-processes data using Python, Pandas, and Regex.
📦 Amazon Grocery Web Scraper (Selenium + Python)
This project is a web-scraping automation script built using Selenium WebDriver to extract grocery product data from Amazon India.
It collects useful product information such as:
•	🛒 Product Name
•	💰 Price
•	⭐ Rating
•	👥 Number of Raters
The script automatically scrolls through all result pages, scrapes the data, stores it in a DataFrame, and performs a small sample of data cleaning.
________________________________________
✅ Project Overview
This scraper:
1.	Opens Amazon.in using Selenium
2.	Searches for "groceries" automatically
3.	Sorts search results by “Best Sellers”
4.	Scrapes product details from every page
5.	Navigates through the Next Page until the last page
6.	Stores everything in Pandas DataFrame
7.	Creates a cleaned version of the dataset
8.	Extracts numeric rating counts (ex: converting “5K” → 5000)
The code uses:
•	Selenium WebDriver
•	webdriver_manager (auto-handles ChromeDriver)
•	NumPy
•	Pandas
•	Regex-based cleaning using regex module
________________________________________
🧰 Technologies Used
Tool	Purpose
Python 3.x	Core programming
Selenium	Automate browser actions
ChromeDriver Manager	Automatically downloads correct ChromeDriver
Pandas	Data storage + cleaning
NumPy	Handling missing values
Regex	Cleaning Raters column
________________________________________
📄 Code Description
1️⃣ Launching Browser & Opening Amazon
The script opens Chrome and navigates to Amazon India using Selenium.
driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()))
driver.get("https://www.amazon.in")
________________________________________
2️⃣ Searching for Groceries
Uses the search bar to type "groceries" and click search.
enter_bar.send_keys("groceries")
search_btn.click()
________________________________________
3️⃣ Sorting by Best Sellers
Clicks Amazon’s sort dropdown → selects Best Sellers.
________________________________________
4️⃣ Scraping Product Details
For each product card, it extracts:
•	Product name
•	Price
•	Rating
•	Rating count
Each value is wrapped in a try/except to avoid breaking the scraper on missing data.
________________________________________
5️⃣ Pagination Loop
The script uses a while True loop to move through all pages until:
•	Next button becomes disabled
•	Or no more pages are found
This ensures full data coverage.
________________________________________
6️⃣ DataFrame Creation
Creates a structured dataset:
df = pd.DataFrame({
    "Product": Product_Name,
    "Price": Price,
    "Rating": Rating,
    "Raters": Raters
})
________________________________________
7️⃣ Data Cleaning Sample
A copy is created for safe cleaning:
df1 = df.copy()
Cleans "Raters" column:
•	Extracts numeric part
•	Converts formats like 5K → 5000
df1["Raters"] = df1["Raters"].apply(lambda x: float(...))


⚠️ Important Note (Ethics + Disclaimer)
This project is for educational purposes only:
•	Do not use it for commercial scraping
•	Respect Amazon’s terms of service
•	Scraping too fast may lead to IP blocking
Use responsibly.



