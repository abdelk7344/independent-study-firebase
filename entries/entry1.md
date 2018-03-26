# Processing and Firebase

## Firebase Overview

Firebase is an application of application add-ons. Really really cool add-ons. Real-time databases and authentication are two components of firebase but, these are the ones that intrigue me the most. 
When constructing Sinatra applications, I always wondered if there was a way for me a web application structured as a site: with multiple of pages, a navigation bar, and more services.
However, it was more difficult and tricky to save the users input from page to page.
Furthermore, I also wanted to personalize the webpage for every user but, yet again, that needed a way to authenticate users into the app and a database to store certain unique features from user to user. (NOTE: The following is going to sound like an advertisement, but believe me it’s not) 
Firebase helps you build a versatile app whether its an android, IOS, or web app with a real-time database, authentication, cloud storage, and much much more. I could talk much more about its speed and effectiveness, but I would rather show the power you could harness with Firebase. Sooooo, without further ado, let's jump right in.  

## How do you eat an elephant?

While many argue that there is definitely more than one way to eat an elephant, the most logical way is to eat it One Bite At A Time. 
Firebase can offer so much but is really complicated to wrap your head around how it all works. To get started with Firebase, you need to have a working javascript or node.js web app. 
While Ruby and Javascript are very similar in terms of mechanisms, they are different in syntax. In order to get accustomed to Javascript and Firebase better, I decided to follow Daniel Shiffman’s Tutorial on incorporating p5js, an interactive art javascript library, with Firebase.
Since I learned p5js in 10h grade, I had still a bit of familiarity with the language. Moreover, I had made a final game project in p5js in which I would have liked to incorporate a real-time leaderboard. This would require a realtime database (aka. Firebase!).

## Getting Started

I will be using my p5js bowling project to create this real-time leaderboard. I found it more convenient to put my game in a javascript file as opposed to having everything in one html file. Therefore, I created app.js and an index.html file and linked app.js as you would link any other javascript file: 

```html
<script src="app.js" type="text/javascript"></script>
```
 
In order to create a leaderboard, I am going to have to take in two values: a name and score. In order to create an input and a submit button in p5js, the p5.dom library is required(which can be obtained at the p5js website or this project’s github repo in the next section). This is how to create a basic text box and submit button in p5js respectively:

``` javascript
var intialInput = createInput('Name')

var submitButton= createButton('Submit')
```
Now it's time for Firebase. From the home page, it is pretty easy to add a project. I am creating a web application so as soon as it brought me to my project page, I clicked ‘add Firebase to web app’ and it gave me the following:

``` html
<script src="https://www.gstatic.com/firebasejs/4.12.0/firebase.js"></script>
<script>
  // Initialize Firebase
  var config = {
    apiKey: "Random Key",
    authDomain: "Random Domain",
    databaseURL: "Random databaseURL",
    projectId: "Project Name",
    storageBucket: "Random storageBucket",
    messagingSenderId: "Random messagingSenderId"
  };
  firebase.initializeApp(config);
</script>
```

I will be using my p5js bowling project to create this real-time leaderboard. I found it more convenient to put my game in a javascript file as opposed to having everything in one html file. Therefore, I created app.js and an index.html file and linked app.js as you would link any other javascript file

In order to create a leaderboard, I am going to have to take in two values: a name and score. In order to create an input and a submit button in p5js, the p5.dom library is required(which can I obtained at the p5js website). This is how to create a basic text box and submit button in p5js respectively:

Now it's time for Firebase. From the home page, it is pretty easy to add a project. I am creating a web application so as soon as it brought me to my project page, I clicked ‘add Firebase to web app’ and it gave me the following:
I took the first script tag and placed it within the header of my index.html file as a reference to the general firebase library. Then I am going to place what is inside the second script tag inside my ‘function setup()’ in my app.js file which makes sense because everytime the app loads it's going to have the all the info that references back to this project’s database. I had to go back to my project’s database section in order to set the rules ‘read and write’ to true in order to push the data I wanted from the app into the database(NOTE: This is only for development purposes modifying the rules to ‘true’ can make it easy for anyone to read and write your app’s data).

To save the data(Name and Score) to the Firebase database, I had to first set my firebase database into a variable in which I could modify or push in data. 

```javascript
var database = firebase.database(); //entire realtime database in a variable
```

Next, in order to structure my data, I need to create a reference point in which I will send the data to. In order to that I will need to create another variable: 

```javascript
var ref= database.ref('scores')
```
However, I needed to keep in mind that I would need to declare this variable one the user actually submits scores. Therefore, I created a function called submiteScores in which I organized the data as a JSON object:   

``` javascript
var data={
         initials: intialInput.value(),
         score: scoreNum
     }
var ref= database.ref('scores')
```
An aside: thinking about the structure of your data is extremely important because you need to decide how you going to approach and use your saved data(consider how you will iterate through your data).

Finally, to push the data up to Firebase you will simply need to refer to the reference point simply push the data as follows:
```javascript
ref.push(data)
```

This will push the data successfully in Firebase; however, there will be special token dedicated to each data passed.

__Key Takeaways__: Structuring data, reference points, and pushing data to Firebase

__Next Steps__: Retrieving data, using data, starting a Firebase WebChat Tutorial to expand knowledge on authentication and databases  


## "Standing on the Shoulders of Giants"

Once finishing this Daniel Shiffman’s tutorial, I myself will share the github repository with hope to help others in understanding Firebase. That being said, I couldn’t have learned so much without Shiffman’s very informative and helpful [video](https://www.youtube.com/watch?v=7lEU1UEw3YI) regarding this topic.  



