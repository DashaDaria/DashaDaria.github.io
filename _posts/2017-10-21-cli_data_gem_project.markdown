---
layout: post
title:      "CLI Data Gem Project"
date:       2017-10-21 07:14:56 +0000
permalink:  cli_data_gem_project
---


I was expecting to be stuck on this first project for some time. I was especially anxious to have to write a program from beginning to end without any helper methods, instructions or some sort of guideline, as it was almost a norm for me from previous labs. 

My expectation was met, as I dug myself deep into a coding hole with infinite possibilities and no clear certainty of which one was the right one. There were moments when I felt that I was never going to get out of this loophole but I am grateful for the hardship as it brought more clarity to working with code. 

I think it would be helpful to recognize some of the initial issues I was having that got me going into endless directions and provide the main takeaways that might help others who are struggling:

1. **Scraping:** I focused a lot on the scraper method(s). I started off in the right direction by creating simple classes and passing fake data into the scraper method to make sure everything was working as it should. But before getting my cli controller class completely in sync, I switched focus to the actual css selectors. This took me down a rabbit hole that started to influence the way I had my classes set up. I was sure that the return value of my scraper method was too complicated to pass in as an argument upon instance instantiation. 
**Take away:** do make sure that the website is scrapable but leave the scraping for the end. Do not let it dictate your code. You can always manipulate the return value to be what you need.   

2. **Classes:** I was convinced that my classes needed to know as much about each other as possible. Again, because I was not sure that my scraper data was sufficient to draw a link between classes.
**Take away:** keep asking yourself - whose responsibility is it to know this information? What should one class know about the other? The answer will never be *everything. *

3. **Putting it together**, aka what's the order: I could not make a decision about which class should be responsible for which method which got me into trying every order. This is good for practice, but not necessary. 
**Take away:** make a decision and stick to it. There are many solutions to a coding problem and they can look very different. See your decision through and then refactor. 

4. Suddenly **nothing makes sense**: the combination of all of the uncertainties from previous issues got me in a state of sudden chaos. Nothing made sense and I was sure I was stuck forever. 
**Take away:** get out of your head! It can me a maze. Also, breathe and probably go do some stretching. 

5. **Fix your iteration, fool**: At some point I started to realize that my iteration for the scraper method is not producing my desired return value. Pry was not helping, turns out using 'puts' for testing is much more efficient.    
**Take away:** when in doubt always check your iterations! And don't forget to properly indent!



