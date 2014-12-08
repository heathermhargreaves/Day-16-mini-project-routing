mini-Routing
============

##Objectives
For this mini-project you're going to create a basic angular Application from scratch. Getting used to structuring your Angular application is an important skill to get right. Many times as beginners the hardest part about Angular is having the question of 'what goes where?'. Hopefully this project will get you on the right path for structuring all your Angular projects in the future.

###Step 1: Angular Skeleton 
* Fork this repo, then clone your fork.
* Create the basics of your Angular application. Your file structure should look like this
  mini-routing
    index.html
    style.css
    js
      app.js
Remember to include ng-app in your application and call your module 'miniRouting'. Also, remember to include the Angular CDN as a script in your HTML along with app.js. Go ahead and create your 'miniRouting' module in your app.js file. 

###Step 2: Add Routing Skeleton
* Right now you should have a very basic Angular application that has nothing more than an app.js (which created your 'miniRouting' module and a index.html page.
* Now we're going to prep out HTML in order to start using ngRoute. 
* Before we use the ngRoute module to handle our routing, there are a few steps we need to take. First, we need to include ngRoute as a script in our HTML page. For your convenience, (http://ajax.googleapis.com/ajax/libs/angularjs/1.2.27/angular-route.js). 
* Once you've included ngRoute as a script, we need to inject ngRoute into our app as a dependency. Remember how we talked about how our app.js is the hub of our application and it's the only place we use 'angular.module('appName', [])' with the empty array? The reason that empty array exists is because it's where we inject dependencies into our application. Head over to app.js and add 'ngRoute' as a dependency.
* When you're done it should look something like this
```javascript
var app = angular.module('friendsList', ['ngRoute']);
```

###Step 3:
