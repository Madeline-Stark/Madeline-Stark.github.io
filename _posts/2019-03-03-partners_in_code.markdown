---
layout: post
title:      "Partners in Code"
date:       2019-03-03 21:55:21 -0500
permalink:  partners_in_code
---

![Partners in Code](https://i.imgur.com/N1aj16Y.jpg)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For my final project, I made a React with Redux App with a Rails API called [Partners in Code](https://github.com/Madeline-Stark/PartnersInCode). I wanted to create this app because it can be difficult to find people to pair program with. This app allows you to add yourself to a registry of programmers and look for a potential pair programming match based on factors like languages and time zone. I was so happy to be able to show off everything I've learned throughout this course, but was also intimidated to be employing new technologies: React and Redux. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While at first, I was not a fan of the strange syntax, I now see how helpful it is to split up the DOM with React. Making API calls with Rails was also new for me, but came fairly easy after learning jQuery. There were of course some new challenges with working with both rails and React. At first I didn't realize I needed to set up two separate servers, with one of them on a different port. And both need to be running at the same time in order to access the API in React.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Working with both React and Rails also meant a lot of moving pieces which leaves you open to a lot more errors. One of my most frustrating errors was that user uploaded images were not displaying properly. After a lot of troubleshooting on the React side, I finally opened a Rails console. There I could see that the img_url property was not properly saving. After a little more rooting around, I finally figured out that I forgot to add img_url to accepted params when I ran a new column migration. It's tough keeping track of so many moving parts!

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I'm proud of how my app turned out though and excited to add more functionality in the future. I think it would be interesting to match partners based on a personality or coding test. It also might be helpful to implement some way for users to pair program directly on the site instead of having to use an outside resource like Zoom. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;I'm very happy to be turning in my final Flatiron school project. Reflecting back on my time here, I have learned so much. Not just about specific languages, but about problem solving, grit, and determination. I'm excited to see what's next in store for me!

