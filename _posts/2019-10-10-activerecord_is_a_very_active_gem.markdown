---
layout: post
title:      "ActiveRecord is a Very Active Gem"
date:       2019-10-10 03:16:44 -0400
permalink:  activerecord_is_a_very_active_gem
---

Activating ActiveRecord is as easy as typing in `gem install activerecord` or simply just adding it in your Gemfile and running bundle. Then you have to make the [connection between Active Record and your database](https://apidock.com/rails/ActiveRecord/ConnectionHandling/establish_connection).

Once the connection has been established, we need to link our model/s to ActiveRecord by inheriting from `ActiveRecord::Base`. Once this has been our model/s has now a whole bunch of methods that can be used like `.create` or `.find`. We do not even need to indicate our `attr_accessor` since ActiveRecord already has this method built in. 

Since ActiveRecord acts as a bridge between our model/s and our database (in this case SQLite). It has made it easier to [create tables and columns, manipulate,  and delete information in our database.](https://guides.rubyonrails.org/active_record_basics.html#crud-reading-and-writing-data)

To add more this gem’s awesomeness, it also creates a user [input validation](https://guides.rubyonrails.org/active_record_validations.html) behind the scenes. It can validate whether the username or email is unique, if the user has filled out details on your forms before it persists bad data in your database. All these things and more can be done just because of one gem! How cool is that?!

While I was doing my Sinatra project, I realized how active this gem is and one thing that I want to learn more about ActiveRecord is how it creates associations between objects. For my project I have done a `has_many` and `belongs_to` association. I have a user that has_many adventures and an adventure belongs_to a particular user. In my database I have put a user_id column in my adventures table since it belongs to one particular user. In my model/s, I have made the association by using the ActiveRecord macros:

![](https://lh3.googleusercontent.com/4zi6zZ7HOmXE3stqk--Y8wQ0fD2cBYsGz0xLOqZuI5ZgNCOgRZsjf4wU790ipk5l9PGRMdVPvA-0nGNfYbJhoaRQbNrcWHxg4LHsbNt_YGNp96fLZD4iku7edX_cZtd_HlX6H_cSew=w2400)

For example:


``` 
alexa = User.create(name: “Alexa”) *Alexa’s user_id = 1
Yosemite = Adventure.create(title: “Yosemite Adventure, user_id: alexa.id) 
* This adventure belongs_to Alexa.

Because of these associations, I can perform these methods:
@adventure.user.name => Alexa
@user.adventures.title => Yosemite Adventure 
```

Now, one thing that I want to learn more on is the [`has_many :through` relationships](https://guides.rubyonrails.org/association_basics.html#the-has-many-through-association) . I was hoping to do it for this project but due to the limited time that I have, I want to understand it better by writing this blog and apply it later. Let’s say I have added another model in my project, now the structure will look like this:

![](https://lh3.googleusercontent.com/-iNMLGpwrklTAtyJ58rqkpD75uQSNKF-rn13VOIKMG7d0WOGo2DeQsEjF6hCaoYL1gyiGD-OzTW6JLAIMDQdsT7jzM5miBzyo7-M8xLe4MX_p76bZsLg7iFbLoK_S6SgButUEZzUrQ=w2400)

In this particular instance, I have a user of my AdventureTracker app named Alexa. Alexa has been going to so many adventures and each adventure that she had was in different locations. So her adventures belongs to her (the user of the app) and to the Location model. In each location, there are many adventures happening and through those adventures of course there are many users who are doing those adventures. The `has_many through` association makes it easier to know all about the locations that our users have been through their adventures and we would be able to know all the users who have been in that particular location through their adventures. As each instance of each model will have a unique id in our database, it makes these associations easier to call.

![](https://lh3.googleusercontent.com/vLkoBfeeTr9O3la38DJQH0A0_To6TAKUsYrlK7gNQwtWDF9eIFyrd_5iRThGt7yoJkaw95906ABdcOphoDNxdEkPNKJb-fCs-knryna36cPajObKIQutiMQdybYz9fKT7QaEN699nw=w2400)

There are still a lot more associations that can be done in ActiveRecord. As a newbie, I’m quite amazed by the things that this one gem can do. My goal is to get comfortable in using these associations and know when and how to use each one.




