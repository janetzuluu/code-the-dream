# **Lesson 09: Introduction to Web Scraping**

---

## **Assignment 1: Understanding HTML and DOM**
1. Open the Wikipedia page for "Web scraping" in your browser: [Wikipedia - Web Scraping]).
2. Use your browser's developer tools (Inspect Element) to identify:
   - The title of the page.
   - The structure of the first paragraph.
   - The structure of the headers (h1, h2, h3) and links.
3. Write a short description of how the DOM is structured on this page.

---

## **Assignment 2: Using BeautifulSoup**
1. Modify the code to extract:
   - All bold text (`<b>` tags) on the page.
   - All images (`<img>` tags) with their `src` attributes.
2. Run the modified script and document the results.

---

## **Assignment 3: Ethical Web Scraping**
1. Access the `robots.txt` file for Wikipedia: [Wikipedia Robots.txt](https://en.wikipedia.org/robots.txt).
2. Identify which sections of the website are restricted for crawling.
3. Reflect on why websites use `robots.txt` and write a short explanation of its purpose.

---

## **Assignment 4: Scraping Additional Data**
1. Write a script to extract the contents of the "See also" section (if present) on a Wikipedia page.
   - Hint: Use `soup.find` or `soup.find_all` with appropriate attributes.
2. Test your script on another Wikipedia page of your choice and document the output.

---


