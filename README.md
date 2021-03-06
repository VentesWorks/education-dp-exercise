## Exercise

You are tasked with creating a data-processing app that pre-processes and enriches the data coming from crawlers, with the following requirements.

* INPUT: csv-like data submitted by crawlers
* OUTPUT: clean data in mongodb collections

1. The app is an HTTP API server. Every year, crawlers will submit the data saved in a file, using the API endpoint designed by you.
2. Examples of data the crawlers will submit every year: see `data-2018.txt`, `data-2019.txt`, `data-2020.txt`. You can't change the format of the data.
3. As you can see, the data coming from crawlers is not 100% well-structured, the API should parse it correctly.
4. a repeated submission with the same year should perform an update on the existing yearly data.
5. if there is any error in the submission or processing, the API should return a proper error message with proper HTTP response status
6. For each university, enrich the data with a URL and a text description of it using Duckduckgo API
e.g. https://api.duckduckgo.com/?q=harvard&format=json&pretty=1
7. The app inserts or updates **clean** data in 3 mongodb tables/collections:

 * table 1 - the yearly data table
 * table 2 - the universities
 * table 3 - the top university in each country in the latest year.

"top" is defined as the university with the highest "Alumni Employment" score

8. table 1 contains data from every year, table 2,3 contains only the latest data.
9. the data processing and transformations should be covered by tests.
10. The solution should be in Python programming language, however you may use any 3rd party library you like.

Feel free to clarify the requirements further, if you have any doubts.

### Bonus (Optional)

If you have indicated any DevOps skillsets in your resume, please create a Dockerfile, and using docker deploy the web app onto a free cloud platform, such as Heroku.


### How the solution is assessed

The criteria are as follows (descending importance)

1. Your code should perform the functionalities required
2. Your code should be well-covered by tests
3. Your code should be modular, readable and maintenable by other engineers.
4. Your code should be robust, and can handle failure such as missing field, disconnection from DB or external server.
5. Your code should be efficient and fast.
6. Your code should be pretty.
