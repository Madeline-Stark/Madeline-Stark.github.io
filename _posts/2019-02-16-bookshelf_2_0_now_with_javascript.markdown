---
layout: post
title:      "Bookshelf 2.0: Now With Javascript"
date:       2019-02-16 15:13:56 -0500
permalink:  bookshelf_2_0_now_with_javascript
---



![bookshelf](https://i.imgur.com/npadbxt.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;After finishing Flatiron’s Javascript module, I went back and added Javascript functionality to my Rails project, [Bookshelf](https://github.com/Madeline-Stark/Bookshelf) . By using jQuery, I was able to add event listeners to HTML elements and load AJAX calls without having to refresh the page.

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bookshelf is an application I built to track books a user has read or is currently reading. For now, I’ve only incorporated javascript into the views for the author class. All of my functions are in the author.js file. I’ve created event listeners for button clicks to load an index of authors, information on a single author and his books, a new author form, and to clear the page. In this file there is also an author class with an object constructor and a static function to load the author index. I decided to use a static function for this because accessing all authors is a call you would make on a class, not an instance. I also added a prototype to create the html for the author show page. Prototypes allow us to store attributes while saving memory. 
        
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;One unexpected challenge to this part of my project was dynamic urls. My getAuthor() function loads on the author show page. The author show page url changes depending on the id of the author the user is accessing. This raised the issue of what to store as the url for the AJAX request. At first I tried interpolating and concatenating the author id in, but neither of those options worked. Then for a while I just hardcoded in a url of /authors/1 so that I could build out and test my function. I eventually found location.href. Location.href is a way of accessing the url of the current page. By setting the value of url to location.href, I was able to write an AJAX call that works for a url that is constantly changing.
        
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; I also added some additional styling to Bookshelf, using Bootstrap. Bootstrap provides sleek default CSS with minimal effort. However, in the future I’d like to swap  out Bootstrap for my own CSS so that I can present books as thumbnails on a Bookshelf. Unread books will stay piled up on a coffee table and users can drag the books to the bookshelf when they’re finished reading them. For now though, I’m very happy with how the app looks and functions and I’m excited to move on to the React/Redux module of the Flatiron curriculum.




