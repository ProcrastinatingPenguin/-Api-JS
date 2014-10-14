Welcome to api-js.
===================


Hey! I'm Josh. This is the github repo for my latest project **api-js**. **Api-js** is a javascript library built for people who want to access apis without writing complex scripts for days.

I designed **api-js** to save people time, and allow all developers to access the fantastic json apis out there. I first started building **api-js** for my own use whilst building a Reddit web application.

What is it? How does it work?
-------------

**api-js** provides you with a set of javascript functions to easily, and quickly use apis in your code.

> **Note:**

> - **api-js** is still in development.
> - Not All Planned Functions Have Been Implemented Yet. Please Check Here Lately for New Updates
> - Currently Only Supports JSON apis.

How To Add it To Your Code?
-------------
Its Easy! Set Up a Normal HTML Document and Add:
```
    <script src = "api.js"></script>
```
Inside Your Header

The **getJSON** function
-------------
##### Used For GET-ting JSON Apis. (Such as Reddit and Github)
  To get a basic JSON Api you use this syntax:
  ```
   getJSON(url, successfunction);
   ```
  
> ##### What Are The Parameters?

> **URL** - The URL you wish to get the JSON from.

> - eg. **http://api.reddit.com/r/funny/top** Is the URL for the top posts in r/funny
> - eg **http://api.reddit.com/r/funny/top?limit=10** Is the URL for the top 10 posts in r/funny.

> **Successfunction** - The function to be called when the data is returned.

> - eg. **getJSON(url, function(data){console.log(data)})** Logs the returned data in the console
> - eg  **getJSON(url, myfunction)** Executes a function you declair called myfunction.


#### A Extremely Basic Demo

What Really Shows How Useful **api.js** can be is this demo:
  Using a question on stackoverflow (http://stackoverflow.com/questions/10341135/example-of-using-github-api-from-javascript) asking for help using the github api the complex solution required 8 lines of code, mine required 2 and produces perfectly readable code.
```
 getJSON('https://api.github.com/users/funchal', function myfunction(data) {
            console.log(data.name + " has " + data.public_repos + " public repositories!"); });
```

#### A More Advanced Demo

The code below when executed collects the top posts in /r/aww then executes the function I declaired called **success**.
The **success** function then sorts out an array of the posts from the json data. The function then goes through the posts one by one writing to an element called container a link to the image and the caption.

```
<body>
    <h1> Demo A. </h1>
    <div id="Container"></div>
    <script>
        getJSON('http://api.reddit.com/r/aww/top', success);
        
        function success(data) {
            redditPosts = data.data.children;

            for (i = 0; i < redditPosts.length; i++) {
                Post = redditPosts[i].data;
                document.getElementById("Container").innerHTML += "<a href = '" + Post.url + "'>" + Post.title + "</a><br>";
            }
        }
    </script>
</body>
```
> **Note:** Previously before using api.js to write out the exact same data required 24 lines. Using api.js it required 8 lines of javascript.

### Support My Library

Please Support My Project By Using it!

