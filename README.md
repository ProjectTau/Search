# Search

Project Tau Search is an open source distributed search engine.

Each user will download an app to there desktop, once installed and working they will be able to use the search engine using some form login system. See **Search Engine**. The central server and potentially the app will contain web crawlers which will search the web and store relavent data about each web page. See **Web Crawlers**

The project will be devloped in go. With a javascript and html frontend. The app will most likely be devloped using electron, and a web assembly version service written in go.

## App Rough Outline/(The app is one type of search appliance)
The app will store a gigabyte of web data to search through. The app will poll the central server for search quaries relating to its data. It will search its data and respond with a result or an negative awknowlage. The app may also act as a web crawler tbd.

## Search Engine
The Central Server will hand the request to a request server with the least load and lowest ping to the user. (Lowest ping will be done based on ip locations, then real ping tests)

1. The Request Server will do pre processing to determine the search appliance to send it to.
2. The Search appliance will recive the request and process it.
3. The Request Server Recive the result of that request and send it to a ranking server.
4. The ranking server will decide the final ranking of results and send it to the central server.
5. The Request server will show the user the results.

### Pre Processing
1. Strip non key words out of search request R to produce RL.
2. It will determine the Search Appliances that have RL keywords in the keyword list.
3. It will pass the request to the appropriate search appliances, and trigger Mid Processing.

### Mid Processing
1. Wait for search appliances to return results or delay notices(asks the Mid processing to wait), if a server does not respond in time with either a result or a delay notice it is considered to be down.
2. Pass resutls to ranking server.

### Search Appliances 
A search appliance will be a computer that can process a search request. (Or more likely one part of a search request)
-The app will be one type of Search Appliance

## How a search will be ranked
1. Does it contain all the words searched for
2. How close together are the words that were searched for.
3. Which section of the text contains the words
4. How frequently is the domain visted by our search engine users.
5. How frequently is the page visted by our search engine users.

## Web Crawlers

### Crawler Appliance