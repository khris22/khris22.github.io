---
layout: post
title:      "Trekking it on Rails"
date:       2019-12-14 13:54:06 -0500
permalink:  trekking_it_on_rails
---


TrekIt is an app that I made for my Ruby on Rails project. This app is used to track outdoor activities the user has been doing.  I have started out as having really big plans and design for this project (which I will still continue to do) but then reality hit me that there was a time limit and big possibilities of debugging many errors. That seems to be the life of a programmer so I settled with the MVP (“Minimum Viable Product”) first and then plan on expanding it in the future. 

### Planning
One of the most important things that I have learned in this project is in the planning stage. The more you plan and think about your models and its associations, the less problems you’ll encounter in the course of making your project. Since associations were discussed in our [Sinatra project](https://khris22.github.io/activerecord_is_a_very_active_gem) I have been very curious about the more complex associations like `has_many` and  `has_many: , through: `.  This is what I wanted my project to look like. Plan A is make the MVP first which includes the User, Adventure, and Location. Once Plan A is working proceed to Plan B which is adding the Category. 

<a href='https://photos.google.com/share/AF1QipOO3kzcB6V2zce9EzotMa0KAIdcjXwKwSCfb2NuWUPKzK_h_dEAtEg3zsus_gAuZg?key=QmE4ODdTQkxmZ0dBNXdxQ1JhN2lLNVJ2NnJwY1hn&source=ctrlq.org'><img src='https://lh3.googleusercontent.com/zLNRSQYi8fFIb32-mBMbUAAbwrzJXBenziyuUNq49mJxk_UvFEJHTb460E888IcQKjBKJ1-s5sVjvWVv6fDKV0W_3-66Xkn0cVar-Ihg_BGzTS6HR8ew7IIjfZbRrVM8FjXF0bsGvw=w2400' /></a>

The biggest hurdle for me is not the associations but how to render the views when it is a nested resource and when it is using the same form that I have for the unnested route. There were lots of trial and error, jumping back and forth from my controller and views, rereading past lectures, and unending Google and StackOverflow search. 

For using the same form on your nested route hidden field is necessary so you will get the proper id:

<a href='https://photos.google.com/share/AF1QipMpxp8olWWa4ANWiFBhgtFc4v6yvmSF4YtBjfMc5zwHDqXD-eX3nFMnBIi-3h6WVA?key=YzhsbUduMlR3NWR5aUxzcW4zWkMtUzBuUzdhRDVB&source=ctrlq.org'><img src='https://lh3.googleusercontent.com/fl2DpfjK1WSaIEBzkmNc-iq73NXu4bG2y4Dt-j4XHASk55-VZHbnEOO8YyeIz10-lMPH0Ajr_szebSFIAL0uQ9UaSzxQnlHBMcNKxCxWnjdQEtg8XLbjmxLQHXmJarCOKpCXcVaynA=w2400' /></a>

This helped me get the location_id in my `locations\:id\adventures` when I am trying to create a new adventure in a particular location. I also added a custom setter for my nested attributes instead of [`accept_nested_attributes_for`](https://api.rubyonrails.org/classes/ActiveRecord/NestedAttributes/ClassMethods.html) so that there will not be any duplicates of the same exact location. If there are many adventures that happened in specific location then all the details of those adventures are located in one `:location_id`. 

<a href='https://photos.google.com/share/AF1QipPey_SQfYh5I8dCTAHh_88X6Ko5G7t20nmt1BAGhbTcU7j7KkIRomrVdzKshqzrSg?key=NU5yTHhBOGFMTElJTjRTOV9SYTlMS2VGLWZxRWRB&source=ctrlq.org'><img src='https://lh3.googleusercontent.com/7k-YCf2TWug_oS5kJ0qjBrV212-zm8Ra_kkyq_ZN6UuhVwelHN5bN9pWDPVRW72PATpSA5l0Upx7LHyHRTQa5YmGzyGHmtiq4sAPpG6CdpMuYpVpJ9b_b-U2vQk4ct2sUeXR66AC5A=w2400' /></a>

### Learning from my mistakes
Now that I have made a project that is required for this project. I am now ready to add more it and expand. In fact, it made me want to work more and make more projects for myself. There is so much more to learn in Rails and it is definitely a powerful language to use.  I have learned a lot from making tiny mistakes in this project. In code, little things matter. It could be a spelling mistake, a wrong syntax or an order in your routes that took so much of your time but now that I know the different possibilities of where unexplainable errors are coming from, I now have a checklist in my mind what to check. 

### A big stepping stone for me!
“Information Overload” is what I had been saying all the time going through the Rails curriculum.  There were so many challenges that I encountered for this project. It was one heck of a ride. 
I was ready to give up and have started questioning whether this is for me. Time, patience and perseverance are keys and as the old saying goes ‘slowly but surely’. Also with the great support that I have, I was get through this project.

Additional Gems/Lessons that I have learned: `gem ‘omniauth-github’`, `gem ‘faker’`, `gem ‘dotenv-rails’`, and `gem ‘thin’`. I have also learned and applied bootstrap for the first time! 

Future Plans: Learn how to use and incorporate `gem ‘devise’`, add additional models and scope methods!








