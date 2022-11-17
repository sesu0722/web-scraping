#  Mission to Mars

I built a web application (app.py) that scrapes various websites for data related to the Mission to Mars and load to database (Mongodb) then displays the information in a single HTML page (index.html). 


## Part  1: Scraping

Complete the initial scraping using Jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.

* Create a Jupyter Notebook file called `mission_to_mars.ipynb`. Use this file to complete all scraping and analysis tasks. The following information outlines what is going to be scraped.

### NASA Mars News

* Scrape the [Mars News Site](https://redplanetscience.com/) and collect the latest News Title and Paragraph Text.

### JPL Mars Space Images—Featured Image

* Visit the URL for the Featured Space Image site [here](https://spaceimages-mars.com).

* Use Splinter to navigate the site and find the image URL for the current Featured Mars Image, then assign the URL string to a variable called `featured_image_url`.

### Mars Facts

* Visit the [Mars Facts webpage](https://galaxyfacts-mars.com) and use Pandas to scrape the table containing facts about the planet (compare to earth) including diameter, mass, etc.

* Use Pandas to convert the data to a HTML table string (to save into MongoDB later on).

### Mars Hemispheres

* Visit the [astrogeology site](https://marshemispheres.com/) to obtain high-resolution images for each hemisphere of Mars.

* Click each of the links to the hemispheres in order to find the image URL to the full-resolution image.

* Save the image URL string for the full resolution hemisphere image and the hemisphere title containing the hemisphere name. Use a Python dictionary to store the data using the keys `img_url` and `title`.

* Append the dictionary with the image URL string and the hemisphere title to a list. This list contains one dictionary for each hemisphere.

- - -

## Part 2: MongoDB and Flask Application

Use MongoDB with Flask templating to create a new HTML page that displays all the information that was scraped from the URLs above.

* Start by converting the Jupyter notebook into a Python script called `scrape_mars.py` by using a function called `scrape`. This function should  execute all your scraping code from above and return one Python dictionary containing all the scraped data.

* Next, create a route called `/scrape` that will import your `scrape_mars.py` script and call your `scrape` function.

  * Store the return value in Mongo as a Python dictionary.

* Create a root route `/` that will query Mongo database and pass the Mars data into an HTML template for displaying the data.

* Create a template HTML file called `index.html` that will take the Mars data dictionary and display all the data in the appropriate HTML elements.

- - -

## Reference

* NASA news url https://mars.nasa.gov/news

* NASA's JPL Mars space image url https://spaceimages-mars.com

* Mars facts url https://galaxyfacts-mars.com

* USGS Astrogeology url https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars



© 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
