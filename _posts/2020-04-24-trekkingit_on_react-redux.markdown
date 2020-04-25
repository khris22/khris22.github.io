---
layout: post
title:      "trekkingIt on React-Redux"
date:       2020-04-24 22:32:14 -0400
permalink:  trekkingit_on_react-redux
---


For my final project, I have gone back to what I have focused my past projects on, an adventure tracker which I named trekIt. It’s an app for people like me and my partner who are fond of doing outdoor activities. The idea came from a real map that we have in our house where we put a pin on every park that we have been to and explored. It gives us a sense of accomplishment that we can visually see and track these locations and it makes us excited and motivated to have a goal hence the digital map on this app so we can carry it wherever we go.

(Map picture here! & Digital Map App picture)
![](https://i.postimg.cc/rp6j8vTF/Screen-Shot-2020-04-25-at-7-30-33-AM.png)

To make that happen, I know that I will have to use an api that will help me render this map. At first, I was leaning towards using [Google Maps Api](https://developers.google.com/maps/documentation) and then my cohort lead suggested [MapBox](https://www.mapbox.com/) so I gave it a shot. The Mapbox api has good documentation but it’s mostly targeted for Javascript so I went into this rabbit hole of trying to make it work for this project. I almost gave up and went back to my first option of using google but I found out that Uber has created a [React wrapper for Mapbox](https://visgl.github.io/react-map-gl/).
![](https://i.postimg.cc/6Qjd8gJv/Screen-Shot-2020-04-18-at-8-15-56-AM.png)
That made my life a little easier and I started making good progress producing a map. This wrapper has its own component that you can import to render the map. It also has its own Markers and Popup component that you can easily use to add to your map. In my mapbox component, I have also passed down the state of my app as props so that the users can render markers on the map of all the locations they have saved. 


There are so many things that I have learned from this section of the curriculum and here are a few of them:

Props and State
At the beginning of the curriculum, I was so confused with the difference of these two words! `Props` is short for “properties”. These are passed into the components from parent to children. `State`, on the other hand, holds information/data about the component. `State` is changeable using `setState`. `this.setState` will only cause a rerender of a particular component and its children but `props` is not changeable or should not change. They are immutable. 

Redux

![](https://i.postimg.cc/6Qjd8gJv/Screen-Shot-2020-04-18-at-8-15-56-AM.png)
Image Source: [http://codesheep.io/2017/01/06/redux-architecture/](http://codesheep.io/2017/01/06/redux-architecture/)

This resource was shared to us by our cohort lead. Since I am a visual learner I have learn the flow of what is going on behind the scenes when developers choose to use redux. 


With Redux, it helps us manage the state of our application that is kept in a store. That being said, since our state is  just in one place we are able to access from any component without having to send down props from one component to another. 

The core concepts of Redux are store, actions and reducers. In the `store`, we keep all of our data, `actions`, based on the word itself, are the things we can do to our store and `reducers` act as a bridge between the store and the actions. It basically gets order from the actions and it decides how the store should be changed/updated.
 

