mini-Routing
============

##Objectives
The purpose of this Mini Project is to get you used to structuring your Angular and routing. These two things are some of the trickiest to wrap your head around so if something doesn't make sense as you're going through this, let us know and we'll come over to help you. 

###Step 1: Angular Skeleton 
* Fork this repo, then clone your fork.
* Create the basics of your Angular application. Your file structure should look like this
  mini-routing
    index.html
    style.css
    js
      app.js
Remember to include ng-app in your application and call your module 'miniRouting'. Also, remember to include the Angular CDN as a script in your HTML along with app.js. Go ahead and create your 'miniRouting' module in your app.js file. Once you're done doing that add these styles to your style.css page.
```css
html, body{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

.menu {
  width: 200px;
  float: left;
  height: 100%;
  background: #e2e2e2;
}

.view-container {
  text-align: center;
}

.view-container h1{
  margin-top: 0;
}
```

###Step 2: Add Routing Skeleton
* Right now you should have a very basic Angular application that has nothing more than an app.js (which created your 'miniRouting' module and a index.html page.
* Now we're going to prep out HTML in order to start using ngRoute. 
* Before we use the ngRoute module to handle our routing, there are a few steps we need to take. First, we need to include ngRoute as a script in our HTML page. For your convenience, (http://ajax.googleapis.com/ajax/libs/angularjs/1.2.27/angular-route.js). 
* Once you've included ngRoute as a script, we need to inject ngRoute into our app as a dependency. Remember how we talked about how our app.js is the hub of our application and it's the only place we use 'angular.module('appName', [])' with the empty array? The reason that empty array exists is because it's where we inject dependencies into our application. Head over to app.js and add 'ngRoute' as a dependency.
* When you're done it should look something like this
```javascript
var app = angular.module('friendsList', ['ngRoute']);
```

###Step 3: Revamp Folder Structure
* As we talked about in the lesson, Angular can dynamically change the template or controller based on what the URL is. For example, if we're at '/users' we can tell Angular to use the 'userController' controller as well as the 'userTemplate' html sheet (or view). 
* As you can imagine your app starts to get really large as you have different routes. The Angular community has found that the best way to organize your application is by feature. For example, in our app we're going to have a home page, a products page, and a settings page. Go ahead and create those three folders. Once you've created those folder makes your file structure looks like this.
  mini-routing
    index.html
    style.css
    js
      app.js
      home
        homeCtrl.js
        homeTmpl.html
      products
        productsCtrl.js
        productsService.js
        productTmpl.tmpl
      settings
        settingsCtrl.js
        settingsTmpl.html
Note that each feature has it's own controller and template (products also has it's own service). Once you're done making the folders and files above, be sure to include all your JavaScript files in your index.html page as scripts.

###Step 4: Revamp index.html
* What's nice about routing is that we can have certain parts of the page be static (it never changes), while other parts of the page are dynamic (changes) based on the URL. What we're going to do is have a side menu that will always stay the same no matter what page the user is on. Then, we'll use <ng-view></ng-view> which will be where our router kicks in. 
* Head over to your index.html page and inside the "<body>" above your "<script>" tags add this template
```html
    <div class="menu">
      <ul>
        <li><a href="#/"> Home </a></li>
        <li>
          Products
          <ul>
            <li><a href="#/products/shoes">Shoes</a></li>
            <li><a href="#/products/socks">Socks</a></li>
          </ul>
        </li>
        <li><a href="#/settings"> Settings </a></li>
      </ul>
    </div>
    <div class="view-container">
      <ng-view></ng-view>
    </div>
```

Notice we have a side menu and then we have our ng-view that will change depending on our router (which we will specify in our next step.

###Step 5: Routing
