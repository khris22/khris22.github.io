---
layout: post
title:      "Keep Exploring"
date:       2019-08-10 15:16:43 -0400
permalink:  keep_exploring
---

## This is my personal take as I reflect on my very first technical project.  

Like what I mentioned on my first few blogs, I have a non-technical background. After studying part-time for a good 2 months here at Flatiron school, I jumped from having zero knowledge in programming to building my very own CLI Data Gem on Ruby. It has not been an easy adventure. Since I knew that I didn't have any technical background, I would have to work harder and make extra effort to make sure I understand all the jargon and concepts in this field. The last couple of weeks have not been easy. It was a rollercoaster ride of being confident and proud to doubting myself and feeling hopeless. Now that my project is finished, I feel a great sense of accomplishment. 

This project did not happen overnight. I started off by choosing a website that I wanted to scrape so I chose something that is personal to me, the National Park Services website (https://www.nps.gov/index.htm). My husband and I love to go on adventures. We actually have a map of all the National Parks here in the US which we use to keep track of all the parks we’ve been so I wanted to make a program that will list out all the parks in each US state and territory. 

I moved on to getting my local environment ready. I followed the supplemental videos on our platform to generate my own gem by typing this: `bundle gem US_Parks` on my terminal. This creates a skeleton for my project. Once that is done, I needed  to make sure that the operating system is interpreting my file through the programming language that I am using which in this case is Ruby. I did that by typing this shebang line: `#!/usr/bin/env ruby` in my program’s file under the bin directory. On that same file, I put `require “US_Parks”`. That file serves as my environment and with that my app will know where  all my other files are. 

Looking back at past lessons, remembering what we did in study groups in my cohort, and also attending the supplemental study groups; I proceeded in making files that I needed in my library with this framework in mind:


![](https://lh3.googleusercontent.com/T_AX64UkQDBp3D_S4FNBJEw8cjPl1WKP8UD-3wlqbnt3G7DRtu1hYS8s_FK_ut0peQ24KjRrKK22TjE0NuvIKCvRBYsTtVuFaiYk2DC51vfXeEAmUsr7cqqFkxv2gfLyWVyZ3VPAjg=w2400)


Before getting into the coding part, I needed to make sure that the files in my library were interacting with each other. So in my file that serves as my environment I used the command `require_relative`. I learned by using this it’s requiring the OS to look for the files listed in my program. Once everything is all set up, the fun part begins: SCRAPING! 

How do I even start? Scraping is like digging in your closet that’s full of stuff you want to keep because who knows when you might need them. Then that day comes that you actually need that item from your closet. You know it’s there, you just gotta have to go through most of the stuff in it and find that specific container where you put it. That’s how I would put scraping. It was a lot of prying and trial and error to be able to grab the data that I needed for my app. I used the gems `Nokogiri`, `open-uri`, and `pry` on this part of the project. The first challenge is scraping all the list of states in the dropdown menu of the NPS webpage. To add to that, I also scraped each state’s url to be able to access the parks they have. Once I got the data I needed, I created a new instance in my `class State`. 

Then I moved on to the second scraping which was getting all the parks in a particular state as well as each park’s attributes like its designation, description, and its url so I can give my user an option to read more about their selected park in detail. Once I got the info that I needed, it was time to pass it as a new instance in my `class Park`. The second scraping will only start working once the user chooses a number of the state they want to explore. This is when I started building my CLI. I had this thought that once I was done with scraping then the heavy lifting was done but I was wrong, very wrong indeed. It was time for me to figure out how to collaborate these files together. The first challenge was to connect my user’s input to get the url that will start up the second scraping. At that point I knew that all my states’ names and urls were already instances of my State. I just needed to access this information by using their index numbers and matching it to my user’s input. 

I wanted to show the relationship between the instances of my `State` and `Park`. I wanted to make my program know that each instance of `State` has many parks and that those instances of `Park` belong to a particular `State`. So I initialized an empty array of parks in my `State` to act as a container for all the parks that belong to that state. 

The process that I created may sound simple but it took me days of going back through all the lessons, videos, asking for help with concepts, and only a few hours of sleep every night to accomplish all of this. It was a difficult feat but it feels very rewarding in the end. I have learned so much since I started this course but I have learned A LOT the last couple of weeks not just about the lessons but also about myself. It has also given me a good glimpse of what it will be like when I do this for a living. 

To those who are starting this journey and especially for people who have a non technical background like me, here are the lessons I learned in the past 2 months of doing this course:

1. Take care of yourself - A lot of times I want to just keep on working and working but I learned the lesson that sometimes stepping away from everything will help me refresh my mind.
2. Ask for help - I would not have done this project without the support of my community of coders. Like what I wrote on my last [blog](https://khris22.github.io/a_community_of_sams), everyone needs a “Sam” in their life. 
3. Hard work pays off in the end - There were many times when I was making this project that I wanted to give up and questioned myself but I know that I just had to keep on pushing myself to keep going.
4. Keep on exploring - there are so many more things to learn and sometimes you will get lost and stuck but you just have to keep on trying to find ways to make some things work. There will always be lessons you will learn along the way.

Here is a preview of my very first CLI project:

![](https://lh3.googleusercontent.com/wWmUMz0vOJRGLy4nIa7oaifp7ZynqsaiOB6REm-BO4xi58vu7E2lZ0t4Ws0hSxsOG9ZXxJD3OTrAqgoKgKJfqVN9oYH14SpSI6G23fYfbqzkTkYOBTCy2rGtMhVmbDHPerNmEViCLw=w2400)



