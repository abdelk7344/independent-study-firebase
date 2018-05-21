# The Fantastic Booklastic

## This Intro Will Not Need A Title.

Have you ever felt like the entire universe conspired all together to help you with a single task? I hate to break it you (or maybe not), but I haven’t had that feeling yet. I had a different feeling composed of mixed emotions of frustration, stress, confusion, and endless excitement. You might be wondering why the excitement part with all those negative feelings. Well……… I LAUNCHED MY FIREBASE APP!!! As I said earlier, I really wished that destiny would help me out a bit, but I was able to get it done through hard work and dedication. I know you always hear that once someone accomplished something, but my type of dedication involves sitting in the same place for almost 8 hours at a time. Woah! I know. I also said that by the eighth hour. That being said, I really want to note that this independent study was really a roller coaster ride that I am really glad I had the opportunity to have. Nevertheless, I felt like this intro did not need a title because I believe that all I said in this intro should have been the title, but I guess it wouldn’t really be a title then. Anyways, let's dive right in!

## Creating a Bootstrap Card Div in jQuery

As always, I will be going the challenges I faced and how I overcame them. I wanted to create a card div in order to have the book title, book image, book author, and an add or remove button in one place. Therefore, I researched and researched and finally came to the answer…...jQuery! I was always scared of jQuery for some reason, but I honestly learned how powerful it can be when completing my project. I really want to learn jQuery now! Anyways, appending certain div elements as parent and child functions got the whole card element to work in jQuery.
We transformed this:
``` html
<div class="card" style="width: 18rem;">
  <img class="card-img-top" src="..." alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
``` 
Into this:

```javascript
var cardDiv = document.createElement("div")
        cardDiv.className = "card col-md-3"
        cardDiv.setAttribute("id", "testDiv");

        // create image top for card
        var images = document.createElement("img");
        images.className = "card-img-top"
        images.setAttribute("src", novelImg);
        images.setAttribute("height", "400px");
        images.setAttribute("alt", "Card image cap");

        // create card body div
        var cardBody = document.createElement("div")
        cardBody.className = "card-body"

        // create card title
        var titles = document.createElement('h5')
        titles.className = "card-title"
        titles.innerHTML = title;

        // create card authors
        var authors = document.createElement("p")
        authors.className = "card-text"

        try {
            authors.innerHTML = "Written by " + author.join(", ")
        }
        catch (err) {
            authors.innerHTML = "Unknown Author"
        }


        // create button
        var buttonLink = document.createElement("a")
        buttonLink.className = "btn btn-primary"
        buttonLink.setAttribute("value", author)

        // console.log(buttonLink.value)
        buttonLink.innerHTML = buttonText
        buttonLink.setAttribute("style", "color:white;");
        if (buttonText == "Add Me!") {
            buttonLink.onclick = function() {
                $(cardDiv).remove();
                pushToFirebase(title, novelImg, author);
            };
        }
        else {
            buttonLink.onclick = function() {
                deleteFomFirebase(title, novelImg, author);
            };
        }

        cardDiv.appendChild(images);
        cardDiv.appendChild(cardBody);
        cardBody.appendChild(titles);
        cardBody.appendChild(authors);
        cardBody.appendChild(buttonLink);

        var currentDiv = document.getElementById("test");
        document.body.insertBefore(cardDiv, currentDiv);
```

## Deleting an item from Firebase

In entry two, I discussed on how to push data through unique tokens. So a user can add their favorite books to their database, but they need to be able to also delete them. In order to delete them, the data of the pressed button needs to equate the data that is in the database. Therefore, I persisted in googling for anotherand found the following snippet of code:
``` javascript
ref.orderByChild('title').equalTo(data.title).once('value').then(function(snapshot) {
    snapshot.forEach(function(childSnapshot) {
        ref.child(childSnapshot.key).remove();
    });
});
``` 
This allowed me to delete the entire token element once the title of both the data of the card element and the database equated.

## Conclusion and Takeaways

I have bad news and good news. The bad news is I will not share the URL of the firebase app in this entry because I am still working on some CSS updates and working on a final bug in the program. I was a little down about not being able to share the URL of the app, but both of partners told me that I should wait till we finalize the product. The good news is my takeaway. This is perhaps my biggest takeaway from this independent study, so listen well. I am going to put it in an analogy: coding is like a chess match. You have to think five steps ahead of you because you can not go back. At times when I was coding, I wanted to go back and improve the way I did things, but I was already completely into coding a function in a certain way, and, if I did change something, I would have to change the entire javascript file. Therefore, I want you when you code to spend five minutes or even two minutes and think wisely before you write a function or a line of code. Think about the most efficient way to get it done. Think about what you want to do next. Think about how you going to use it later with other parts of your program. That being said, I can’t wait to share my project with you in the next entry! 



