# Amazon Product Count Automation using Selenium
## Name: Dharunyadevi S
## Register Number: 212223220018
## Project Description

This project automates the Amazon website using Python and Selenium WebDriver.

The program:
1. Opens the Amazon website.
2. Searches for a product.
3. Navigates to the search results page.
4. Finds all the products displayed on the page.
5. Counts and displays the number of products.
## Program:
```py
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
driver = webdriver.Chrome()
driver.maximize_window()
driver.get("https://www.amazon.in/")
wait = WebDriverWait(driver, 10)
search = wait.until(
    EC.presence_of_element_located((By.ID, "twotabsearchtextbox"))
)
search.send_keys("laptop")
search.submit()
products = wait.until(
    EC.presence_of_all_elements_located(
        (By.CSS_SELECTOR, "div[data-component-type='s-search-result']")
    )
)
print("Number of products:", len(products))
print("Test executed successfully...")
input("Press Enter to close...")
driver.quit()
```
## Technologies Used

- Python
- Selenium WebDriver
- Google Chrome
- ChromeDriver

## Requirements

Install Python and Selenium before running the program.

Install Selenium using:

```bash
pip install selenium
```

## How to Run

Run the Python file:

```bash
python amazon_product_count.py
```

The browser will open automatically and navigate to Amazon.

The program searches for:

```text
laptop
```

After the search results are loaded, Selenium counts the products displayed on the page.

## Code Logic

The program uses:

```python
find_elements()
```

to locate all product elements.

Then:

```python
len(products)
```

is used to count the number of products.

### Why `find_elements()`?

`find_element()` returns only one matching element.

`find_elements()` returns all matching elements.

Since we need to count multiple products, `find_elements()` is used.

## Sample Output

```text
Number of products: 16
```

The exact number may change because Amazon's search results can change dynamically.

## Automation Flow

```text
Open Amazon
      |
      v
Search for "laptop"
      |
      v
Display Search Results
      |
      v
Find All Products
      |
      v
Count Products
      |
      v
Display Product Count
```

## Learning Outcome

This project demonstrates:

- Selenium WebDriver automation
- Browser navigation
- Finding web elements
- Using `find_elements()`
- Counting multiple web elements
- Using explicit waits with `WebDriverWait`
- Basic web automation using Python
## Output
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8eac234f-de8f-4a77-90ae-324d2a32d254" />
