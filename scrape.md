**Scrapping** simply means extracting information

web scrapping simply means to extract content from any rete website  . 
in webscrapping we scrape the html content of a website and render it according to our need.

in webscrapping we usually make request to a page for its html and then we can use it 
as we want .

all search engines say like google use webscraping to index their content

webscrapping can be done in different programming languages but this blog is javascript oriented

#before you start
   - you should have basic knowledge of html , dom and javascript
   - you must be having node js installed on your machine

you are ready to start but before that you need some tools to make request and to 
use that response data.

 ## cheerio 
  - cheerio is like jquery for node there are a lot of web scrapping libraries out
 there  but why we are using cheerio well cheerio is used by most of the developers 
 as it is robust and very easy if you have used jquery that you must have then its syntax
 will look much familiar to you.
  ## request 
   to  make request to a remote website


 ####>lets start scrapping

```javascript
     -app.js
       const cheerio = require('cheerio')
       const $ = cheerio.load('<p id="para">hello world i am going to be scrapped:-)</p>')
          const text = $('#para').text()
           console.log(text)
```
 
  
 - output : hello world i am going to be scrapped:-)
   looks familiar to jquery :-)
   

similarly you can scrape a remote website 

```javascript

 - app.js
var request = require('request');
var cheerio = require('cheerio');


->const url =https://en.wikipedia.org/wiki/Sachin;
 request(url, function (error, response, html) {
  if (!error && response.statusCode == 200) {
    console.log(html);
  }
});
  
```
   - if everything works fine then you should be seeing the html contents of this 
   page in your console.

```javascript

request(url, function (error, response, html) {
  if (!error && response.statusCode == 200) {
     let $ = cheerio.load(html);
     let heading  = $('#firstHeading').text();

       console.log(heading)
       //output:sachin 



    });
  }
});
```



**ok so in above example we have scraped the title of a wikipedia page 
similarly you can scrape any content of that webpage or you can make 
clone of wikipedia too as you have got full access of that page using cheerio
happy scraping:-)**