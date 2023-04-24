
![](FaS-BldTrnsprnt.png)

## Table of contents

* [Overview](#overview)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Development History](#development-history)
* [Deployment](#deployment)
* [Contact Us](#contact-us)
* [Team](#team)
* [Team Contract](#team-contract)

## Overview

[Taste Technologists](https://github.com/taste-technologists) is a web application designed for college students with limited kitchen resources, minimal cooking skills, and limited access to groceries. Our application is for college students who would like to eat healthier and spend less money on eating out. This application is based on [Toaster Oven Lovin'](https://courses.ics.hawaii.edu/ics314s23/morea/final-project/reading-project-toaster-oven-lovin.html).

Taste Technologists gives students (on-campus or off) a variety of easy and delicious recipes that:
* Can be made using minimal kitchen facilities (at a minimum, a toaster oven).
* Can be made out of ingredients that are available within walking distance of UH.
* Suit local taste sensibilities.
* Can be filtered via dietary restrictions (gluten-free, vegan, etc).
* Have an estimated cost per serving.
* Has an estimated number of servings per recipe.
* Has an estimate of how long it takes to make.


The project illustrates various technologies useful to ICS software engineering students, including:
* [Meteor](https://www.meteor.com/) for Javascript-based implementation of client and server code.
* [React](https://reactjs.org/) for component-based UI implementation and routing.
* [React Bootstrap](https://react-bootstrap.github.io/) CSS Framework for UI design.

It also provides code that implements a variety of useful design concepts, including:

* Vendor, admin and default users (students).  Admins can edit all content in the system, remove inappropriate content and establish users having a vendor role. Vendors can establish a profile including their locations and hours and for each ingredient in the system indicate the stock, cost, and quantity. Regular users can also change ingredient price and availability.  From ingredient information the system can automatically calculate all the places nearby campus that has the ingredient and the prices for each ingredient at each place. 


## User Guide

This section provides a walkthrough of the Taste Technologists user interface and its capabilities.

### Landing Page

The landing page is presented to users when they visit the top-level URL to the site.

![](M2_Landing.png)

### Sign In and Sign Up Page

Click on the "Login" button in the upper right corner of the navbar, then select "Sign in" to go to the following page and login. You must have been previously registered with the system to use this option:

![](M1_SignInPage.png)


Alternatively, you can select "Sign up" to go to the following page and register as a new user:

![](M2_SignUp.png)

### Favorites Page

The list recipes page provides a display of all the recipe cards in the database. 

![](M2_Favorites.png)

### Search Page

The search page provides the ability to filter the recipe database and display the results in the page. 

![](M2_Search.png)

### Individual Recipe Page

The individual recipe page provides the necessary information of the selected recipe. The recipe card should include but not limited to:

* Minimal kitchen facilities 
* Dietary restrictions 
* Cost, servings, time
* Available ingredients 
* Nearby grocery stores

![](M2_RecView.png)

### My Recipes Page
The my recipes page will display all of the recipes that the user has added to the application. Here they can access the edit link to edit their own recipes.

![](M2_MyRecipes.png)

### Add Recipes Page
The add recipes page gives users the ability to add their own recipes to the application. Each time a recipe is added by a user, the user's email will be set as the recipe's owner.
![](M2_RecAdd.png)


### Edit Recipes Page
The edit recipes page gives users the ability to edit their own recipes in the application.
![](M2_RecEdit.png)


### Vendor Page

The vendor page lists all of the available stores, locations, hours, and the updated inventory. If a user is assigned to the vendor role, they will be able to edit the inventory for their store.

![](M2_VendorList.png)

### Vendor Add Page
*** Add Description ***

![](M2_VendorAdd.png)

### Vendor Edit Page
*** Add Description ***

![](M2_VendorEdit.png)

### Vendor Inventory Page
*** Add Description ***

![](M2_VendorInv.png)

### Add Inventory Page
*** Add Description ***

![](M2_InventoryAdd.png)

### Edit Inventory Page
*** Add Description ***

![](M2_InventoryEdit.png)


### Admin Dashboard Page
*** Add Description ***

![](M2_AdminDash.png)


### Admin Edit Role Page
*** Add Description ***

![](M2_AdminEditRole.png)

### Admin Vendor List Page
*** Add Description ***

![](M2_AdminVendorList.png)

## Developer Guide


### Installation
<details>
<summary>Click for Installation Instructions</summary>
First, [install Meteor](https://www.meteor.com/install).

Second, go to [https://github.com/taste-technologists/taste-technologists](https://github.com/taste-technologists/taste-technologists), and download a copy of Taste Technologists.

Third, go to your newly created repository, and click the "Clone or download" button to download your new GitHub repo to your local file system.  Using [GitHub Desktop](https://desktop.github.com/) is a great choice if you use MacOS or Windows.

Fourth, cd into the app/ directory of your local copy of the repo, and install third party libraries with:

```
$ meteor npm install
```

### Running the system

Once the libraries are installed, you can run the application by invoking the "start" script in the [package.json file](https://github.com/taste-technologists/taste-technologists/blob/main/app/package.json):

```
$ meteor npm run start
```

The first time you run the app, it will create some default users and recipes. Here is the output of the current version:

```
$ meteor npm run start

> meteor-application-template-react@ start /Users/user/Documents/GitHub/taste-technologists/app
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/Documents/GitHub/taste-technologists/app ]]]]]

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
I20230412-14:08:22.799(-10)? Creating the default user(s)
I20230412-14:08:22.812(-10)?   Creating user admin@foo.com.
I20230412-14:08:22.917(-10)?   Creating user vendor@foo.com.
I20230412-14:08:23.007(-10)?   Creating user john@foo.com.
I20230412-14:08:23.200(-10)? Creating default recipes.
I20230412-14:08:23.201(-10)?   Adding: Feta-Spinach Puff Pastry Bites (john@foo.com)
I20230412-14:08:23.317(-10)?   Adding: Parmesan Thyme Crisps (admin@foo.com)
=> Started your app.

=> App running at: http://localhost:3000/
       
```

Periodically, you might see `Error starting Mongo (2 tries left): Cannot run replSetReconfig because the node is currently updating its configuration` after the `=> Started HMR server.`. It doesn't seem to be a problem since the MongoDB does start.

### Viewing the running app

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/taste-technologists/taste-technologists/blob/main/config/settings.development.json), or else register a new account.

### ESLint

You can verify that the code obeys our coding standards by running ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```
</details>

## Deployment

### Digital Ocean Setup

<details>
<summary>Click for Deployment Instructions</summary>
For our project, we used [Digital Ocean](https://www.digitalocean.com/) to set up the server and host the application.

To Deploy Taste Technologists, you will need to complete the following steps:
#### 1. Sign up with Digital Ocean
Go to [Digital Ocean](https://www.digitalocean.com/) and click on the 'Sign Up' button to create your account.

Note that you will need a credit card to complete the sign up. Currently (as of 4/12/23) Digital Ocean is offering a free $200 credit for 60 days.

#### 2. Create an Ubuntu Server
Find the Create Droplets page and choose your preferred settings. Once you are finished selecting your settings, click the 'Create Droplet' button at the bottom of your screen.

The following are some recommended settings:

![do-1.png](do-1.png)
* Ubuntu Server - Version 22.10 x64
* Droplet Type - Shared CPU - Basic

![do-2.png](do-2.png)

* CPU options - Regular - Disk type: SSD
* Plan - $6/mo with 1GB/1CPU - 25GB SSD Disk - 1000 GB transfer

![do-3.png](do-3.png)
* Authentication Method - Create a root password

Once you have successfully created your droplet, you will find the information under your first project.
![do-4.png](do-4.png)

#### Local Setup
The rest of the deployment instructions must be carried out via your computer.

#### 3. Clone and install a copy of Taste Technologists.
If you have not already done so, clone the repository for Taste Technologists and run the installation instructions.

#### 4. Install Meteor Up
Install Meteor Up onto your computer by running

```$ npm install --global mup ```
#### 5. Create app/.deploy/mup.js and app/.deploy/settings.json

Create an IntelliJ Project for your local copy of Taste Technologists.

In the app/.deploy directory, you’ll find two files: mup.sample.js and settings.sample.json. Make a copy of mup.sample.js called mup.js, and a copy of settings.sample.json called settings.json. When you’re done, the .deploy directory should look like this:

![do-5.png](do-5.png)

These files should be git-ignored, so you may safely store credentials here.

#### 6. Configure mup.js
To do the initial deployment, you only need to edit the mup.js starting template.
````
module.exports = {
servers: {
one: {
host: '111.222.333.444',
username: 'root',
password: 'changeme'
}
},

app: {
name: 'meteor-application-template-react',
path: '../',

    servers: {
      one: {},
    },

    buildOptions: {
      serverOnly: true,
    },

    env: {
      ROOT_URL: 'http://111.222.333.444',
      MONGO_URL: 'mongodb://mongodb/meteor',
      MONGO_OPLOG_URL: 'mongodb://mongodb/local',
    },

    docker: {
      image: 'zodern/meteor:latest',
    },

    enableUploadProgressBar: true
},

mongo: {
version: '5.0.5',
servers: {
one: {}
}
},
};
````
There is one occurrence of the string “changeme”, and two occurrences of the string “111.222.333.444”.

Change the string “changeme” (i.e. the server root password) to the Droplet root password you specified earlier.

Change the string “111.222.333.444” to the IP address associated with your Droplet. Be sure to use the “ipv4” address, not the “Private IP” address!

Note that the “host” value is just the IP address, but the ROOT_URL is “http://” followed by the IP address.

#### 7. Run mup setup
Once you have completed configuring the mup.js file, you can now setup the application and MongoDB database.

Inside the app/.deploy directory, invoke “mup setup” (or “mup.cmd setup” on Windows).

```` 
$ mup setup 

Started TaskList: Setup Docker
[111.222.333.444] - Setup Docker
[111.222.333.444] - Setup Docker: SUCCESS

Started TaskList: Setup Meteor
[111.222.333.444] - Setup Environment
[111.222.333.444] - Setup Environment: SUCCESS

Started TaskList: Setup Mongo
[111.222.333.444] - Setup Environment
[111.222.333.444] - Setup Environment: SUCCESS
[111.222.333.444] - Copying Mongo Config
[111.222.333.444] - Copying Mongo Config: SUCCESS

Started TaskList: Start Mongo
[111.222.333.444] - Start Mongo
[111.222.333.444] - Start Mongo: SUCCESS

Next, you should run:
    mup deploy
````

#### 8. Run mup deploy
If the previous step was successful, you can now start running your application on the Droplet.
Inside the same directory as before (app/.deploy), invoke "mup deploy" (or, on Windows “mup.cmd deploy”).

```` 
$ mup deploy
Building App Bundle Locally

Started TaskList: Pushing Meteor App
[111.222.333.444] - Pushing Meteor App Bundle to the Server
[111.222.333.444] - Pushing Meteor App Bundle to the Server: SUCCESS
[111.222.333.444] - Prepare Bundle
[111.222.333.444] - Prepare Bundle: SUCCESS

Started TaskList: Configuring App
[111.222.333.444] - Pushing the Startup Script
[111.222.333.444] - Pushing the Startup Script: SUCCESS
[111.222.333.444] - Sending Environment Variables
[111.222.333.444] - Sending Environment Variables: SUCCESS

Started TaskList: Start Meteor
[111.222.333.444] - Start Meteor
[111.222.333.444] - Start Meteor: SUCCESS
[111.222.333.444] - Verifying Deployment
[111.222.333.444] - Verifying Deployment: SUCCESS
````

#### 9. View your application
The Taste Technologists application should now be available at at http://111.222.333.444, where '111.222.333.444' is replaced by the IP address for your Droplet.
</details>


## Development History
As our team implements this application, we will be working according to three milestones.  For our first deployment our main concerns were creating the base pages and basic components of the page.  We used the react template to give us the framework of the website. Additionally, we added in basic user functionality like being able to see all recipes and individual recipes.  We also created logos and have a draft of a basic theme.  In the M2 we want to create more collections as well as functionality for users, vendors and admins.  Depending on how much tasks we finish in M2 we could also create beyond the basics features.  

[Milestone 1](https://github.com/orgs/taste-technologists/projects/1)

[Milestone 2](https://github.com/orgs/taste-technologists/projects/7)

[Milestone 3](https://github.com/orgs/taste-technologists/projects/8)


## Deployment
The deployed application can be viewed [here](https://taste-technologist.site).

## Contact Us

### Team
Our team consists of five developers: [Amanda Achiu](https://blesssyouu.github.io/), [Iwalani Campbell](https://iwalanicampbell.github.io/), [Christina Mende](https://mendechris.github.io/), [Tsz Ching Wong](https://twong9.github.io/), and [Christianne Young](https://clyyoung.github.io/).

If you have any questions or comments about Taste Technologists, you may find the contact information for our team members by clicking a link above.

Coordination strategy:
* One meeting in person, one virtually via Discord
* Short meetings on Discord if needed
* Issues will be self-assigned

### Team Contract
In order to efficiently work together as a group, we have come up with a [team contract](https://docs.google.com/document/d/1sjqEOUAvMnTnnFC-cFGRXGMhvwe6CVLrR_du6l2pfGI/edit?usp=sharing). 
