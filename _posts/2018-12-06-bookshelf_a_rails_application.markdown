---
layout: post
title:      "Bookshelf: A Rails Application"
date:       2018-12-06 19:21:08 -0500
permalink:  bookshelf_a_rails_application
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For my Rails portfolio project I built an app called [Bookshelf](https://github.com/Madeline-Stark/Bookshelf) that tracks books that a user has read or is currently reading. I came to Rails after learning Sinatra and I don’t think I will ever go back. Although I appreciate the deeper understanding I gained from learning Rails, Rails offers up a lot more “magic”. What took lines of html before is now much simpler to execute. Now instead of writing out an href element, I can just use link_to. And forms are much cleaner now with form_for. Routing is also simpler now that rendering is implicit. If I create a new action, the controller automatically knows what view I want to render.  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;With added capabilities though also comes the potential for more complicated problems. For this project, I really struggled with getting my nested form to work. I wanted users to be able to modify attributes of the join table (user_books) while filling out the form for a new book. I figured it would be simple using fields_for, but the content was not showing up in the browser. One of my most frustrating errors was leaving out an equal sign in the fields_for erb tag. One little typo can cause so many problems! Once I got the new book page working, I had to adapt the form partial to work for the edit form. An interesting problem editing on join table attributes presents is that instead of showing you a single attribute, the edit form will show you attributes for all that book’s joins. I dealt with this by directing readers to a user_books#edit page whenever they wanted to change their relationship with that book (e.g. whether or not they finished the book). 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Down the line, I’d love to add more functionality to this project. I especially want to work on the design. For the user show page, instead of a text list of books, I plan on creating a visual bookshelf filled with thumbnails of the user’s books. I could pre-make thumbnails for popular books and also allow user’s to upload images. They could even drag and drop books from unread (on a book table) to read (on the bookcase). 
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I’m excited to continue working on this project and later incorporate what I learn in the JavaScript section.  
