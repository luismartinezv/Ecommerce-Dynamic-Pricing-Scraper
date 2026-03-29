# 🕸️ Ecommerce Dynamic Pricing Scraper

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)
![Web Scraping](https://img.shields.io/badge/Web_Scraping-Selenium_|_BS4-darkgreen)
![Data Cleansing](https://img.shields.io/badge/Data_Cleansing-Regex-black)

## 📌 The Business Need
In modern retail and e-commerce, static pricing is obsolete. Companies must constantly monitor competitors' prices to feed their own dynamic pricing models. However, competitor data is rarely available via clean APIs.

**The Objective:** Build an automated data-gathering pipeline capable of navigating an e-commerce platform, overcoming dynamic rendering barriers, and cleansing messy textual data into a structured format ready for analytics.

## ⚙️ The Technical Challenge
Extracting data from modern websites presents specific challenges that simple HTTP requests cannot solve:
1. **Dynamic Content Rendering:** The target e-commerce platform utilizes JavaScript/AJAX to render product cards.
   * *Solution:* Implemented **Selenium WebDriver** with explicit waits (`WebDriverWait`) to ensure the DOM is fully loaded before extraction.
2. **Unstructured & Messy Data:** Raw price extractions often contain mixed text (e.g., `"$122.00Ex Tax..."`).
   * *Solution:* Applied string manipulation and **Regular Expressions (Regex)** `re.sub(r'[^\d.]', '', ...)` to isolate pure float values for downstream econometric or machine learning models.

## 🛠️ Tech Stack & Methodology
* **Automation & Browser Control:** `Selenium` (Chrome WebDriver)
* **HTML Parsing:** `BeautifulSoup4` (`html5lib` parser)
* **Data Cleansing:** `re` (Regex)
* **Data Structuring:** `Pandas`

## 🚀 How to Run Locally
To reproduce this pipeline in your local environment, install the required dependencies using the provided requirements file:

```bash
# Clone the repository
git clone [https://github.com/TU_USUARIO/Ecommerce-Dynamic-Pricing-Scraper.git](https://github.com/TU_USUARIO/Ecommerce-Dynamic-Pricing-Scraper.git)

# Install dependencies
pip install -r requirements.txt
```

## 📂 Repository Structure
* `/src`: Contains the core extraction notebook `competitor_pricing_scraper.ipynb`.
* `/data`: The output dataset `ecommerce_pricing_data.csv` containing cleaned product names and prices in USD.
* `requirements.txt`: Standardized list of Python dependencies for environment reproduction.

---
*Developed by **Luis Martínez Vicente** - Economist & Data Scientist*
*[Connect on LinkedIn -> Still to be updated](https://www.linkedin.com/in/luis-mart%C3%ADnez-77a857331/)*
