# Books Are Far More Complicated Than We Think

## My First Messy Intro
It's official. I have started my final independent study project using everything I have learned that past six weeks. Bear with me because this intro is going to be very complicated because, as we are embarking on creating an MVP(minimum viable product), brain monsters are consuming are very ideas at the moment. Don’t worry. I am okay. Kind of… Anyways, let's get back to business. My original plan was to create a restaurant javascript app, but, due to the very complicated authentication process that would have probably taken us another week to understand, we decided to change our topic to books. Therefore, we are currently creating a book javascript app that will ultimately allow the user to search, add, and delete books using their own personal account aka. Firebase. Sounds simple and cute right? It isn’t and I am going to show you why now.

Local Storage and JSON….Shazam!
Once we were able to get the user's input to search for books, we had to list the books. Now the tricky part is we wanted to list those books on another page. You might be screaming at me now LOCALSTORAGE, but believe me, I tried this:

``` javascript
// Setting a local storage variable
localStorage.setItem("globalVar",actualVar)
```

Along with this

``` javascript
// Setting a local storage variable
localStorage.getItem("globalVar")
```

There was definitely no error in the syntax so, I was freaking out because I kept getting “null” when I consol logged the local storage variable. However, when I did end up searching “Local storage and array,” something very surprising came up. It turns out the local storage can only store one string, but more importantly, people have actually figured a way to get that done using a JSON method:

``` javascript
// setting a global storage array as a string variable  
var array = [];
localStorage.setItem("names", JSON.stringify(array));

// reconstructing the array from string JSON format
var storedNames = JSON.parse(localStorage.getItem("names"));

``` 

Once I consoled the local storage variable, I was able to find some hope, but that only lasted quite a bit guys…

## Why Harry Potter?
The local storage variable was working fine at first, then it only limited the user to one response and, finally, it wasn’t working at all. The one response it limited the user to was Harry Potter. Don’t get me wrong, I love Harry Potter, but why? Was the computer trying to communicate with us that there might be a magical world wanting to recruit us? Who knows? However, when I did console logged the local storage variable it always worked on the index page, but never on the results page which was really weird. Overall, we have learned a lot by connecting the many topics we have already used and connected in this project; however, in order to transform our app into something we can utilize for firebase, we need local storage to work. Therefore, our main focus in the next few days is to keep debugging and probably trying to find another alternative. More importantly, we need the users to be able to get authenticated into this app by utilizing the one and only firebase.

## Conclusion and a Key Takeaway
I will start with a single key takeaway I wish I had given myself earlier. I have used almost everything I learned in the past six weeks in the app I am currently building; however, it is tough because, while I did comment on code, I did not comment well enough to understand the line code by just looking at once again. I know it might seem redundant saying this, but I have learned that I legitimately have to comment my code looking from the perspective of my future me because if future me cannot understand it then he will spend another 10 minutes trying to.  I have already mentioned that this week will be the week that either makes me or…. Destroy me. Just joking, but this week will probably be where we ultimately merge between firebase and this newly built app. Hopefully. Stay tuned for next week folks.         
