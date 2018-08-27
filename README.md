# Search

Project Tau Search is an open source distributed search engine.

Each user will download an app to there desktop, once installed and working they will be able to use the search engine using some form login system. See **Search Engine**. The central server and potentially the app will contain web crawlers which will search the web and store relavent data about each web page. See **Web Crawlers**

The project will be devloped in go. With a javascript and html frontend. The app will most likely be devloped using electron, and a web assembly version service written in go.

## App Rough Outline/(The app is one type of search Server)

The app will be able to act as one of the server types.

- Request Server
- Search Server
- Ranking Server

**Old**
-The app will store a gigabyte of web data to search through. The app will poll the central server for search quaries relating to its data. It will search its data and respond with a result or an negative awknowlage. The app may also act as a web crawler tbd.

## Search Engine

The Central Server will hand the request to a request server with the least load and lowest ping to the user. (Lowest ping will be done based on ip locations, then real ping tests)

1. The Request Server will do pre processing to determine the search Server to send it to.
2. The Search Server will recive the request and process it.
3. The Request Server Recive the result of that request and send it to a ranking server.
4. The Ranking server will decide the final ranking of results and send it to the central server.
5. The Request server will show the user the results.

## Request Server

### Pre Processing

1. Strip non key words out of search request R to produce RL.
2. It will determine the Search Server that have RL keywords in the keyword list.
3. It will pass the request to the appropriate search Server, and trigger Mid Processing.

### Mid Processing

1. Wait for search Server to return results or delay notices(asks the Mid processing to wait), if a server does not respond in time with either a result or a delay notice it is considered to be down.
2. Pass resutls to ranking server.

### Final Processing

1. Wait for Request Server to return results or delay notices(asks the Mid processing to wait), if a server does not respond in time with either a result or a delay notice it is considered to be down.
2. Pass resutls to user.

## Search Server

A search server will be a computer that can process a search request. (Or more likely one part of a search request)
-The app will be one type of Search Server

## Ranking Server

1. 

## How a search will be ranked

1. Does it contain all the words searched for
2. How close together are the words that were searched for.
3. Which section of the text contains the words
4. Domain Ranking
- Calculation for every domain u <h3>Domain Ranking = ∑ df<sub>u</sub></h3> where pf it the domain frequency of u.
- How frequently is the domain visted by our search engine users.
- How many domains link to this domain, their frequency.
5. Page Ranking
- Calculation for every page u <h3>Page Ranking = ∑ pf<sub>u</sub></h3> where pf it the page frequency of u.
- How frequently is the domain visted by our search engine users.
- How many pages link to this page, their frequency.

## Web Crawlers

### Crawler Server