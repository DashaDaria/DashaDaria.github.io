---
layout: post
title:      "Sinatra Portfolio Project - Circuit Trainer"
date:       2017-11-22 09:11:02 +0000
permalink:  sinatra_portfolio_project_-_circuit_trainer
---


Circuit Trainer is a Sinatra app that helps you track and create your own circuit workouts. The inspiration for this app came from my current workout routine. I've been moving to a new city every month and it has been challenging to keep a steady exercise program. I enjoy circuit training and found myself using Pinterest to find appropriate exercise programs. This has been time consuming and distracting. The Circuit Trainer is my solution to developing your own workouts, tracking your routine and taking a bigger role in your health education.


**App Development Flow**

Before starting to code, I thought about the app overall and established which information is important and relevant for the user. This helped me understand how many models I will need and what attributes each class should have. Next, I drew out the relationships between my models. 

Once I had a good understanding of how I wanted my classes to interact, I created the migration and models files and went into rake console to test my expectations. After making sure that my objects and classes were communicating properly, I created the controllers and views files.

I implemented the RESTful routes design pattern when creating controller actions and mapping them to the views. In order to test my app, I created dummy data and db:seed(ed) it into my database, this facilitated proper testing for all of the CRUD actions and helped debug code in general. 

**Main Discoveries and Takeaways**

There were several decisions I had to make in my code that greatly impacted the overall app. I tried multiple approaches and reached the following conclusions:

* Do not use **has_and_belongs_to_many** relationship. Long story short, this relationship utilizes a join table that DOES NOT have an id attribute, which might limit your code in the future. A good walkthrough on the reasoning behind this can be found [here](http://blog.flatironschool.com/why-you-dont-need-has-and-belongs-to-many/).

* I can use ** inline CSS** for flash messaging. Of course the proper way to go about stylizing your app is to use stylesheets. However, if you want to stylize one element (like a flash message), and your focus is not on the front end of your app at the moment, try this:
```
  <% if flash.has?(:message) %>
    <p style="color:red;"><%= flash[:message] %></p>
  <% end %>
```  

* There's a **titleize** method in Ruby to simply capitalize every word of your string.  


