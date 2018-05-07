# Javascript and APIs 2.0

## Quick-Breezy-Yet-Foggy-Introduction
I know that the title of the entry is pretty boring, but I really did try to make up for it by giving a giving you an amazing section title. It’s actually pretty sunny and warm outside presently; nevertheless, I am always here to talk about my ongoing expedition in creating a Firebase app. It does sound pretty bold putting my entire motive in a sentence, but it is far more complicated trying to actually accomplish such an independent study. This week, I continued studying javascript with APIs. Specifically, I focused on how to obtain information from the user and then direct them to another page with the information requested from an API. I faced multiple of significant challenges that I will be writing about in this entry two lines from... now. Enjoy!

## User Input: 
I could have written anything in the request above, but I am choosing to explain my first challenge in creating a user responsive Javascript app: inputs. There are definitely many effective ways that programmers can attain user inputs utilizing Javascript; however, I ended up utilizing the method that I felt most comfortable with. I created my input and button on my HTML page and gave both IDs in order to target the information I wanted to use: 
``` html
<p>Enter a show:</p> <input type="text" name="topic" id="userinput"><br>
<input id="button" type="submit" name="button" onclick="PUT FUNCTION HERE: IT WILL RUN ONCE BUTTON IS CLICKED()" />
```
Next, I needed to attain that information in my javascript file in order to make an API request. I used a javascript method in order to get the user input by ID; however, because I was missing the “.value” function, I kept receiving an error as I consoled the user input:
``` javascript
// Before
userinput = document.getElementById('userinput');

// After: a period,a word, and a pair of parentheses can really make a difference
userinput = document.getElementById('userinput').value;
```
## The Storage of the Program
I wanted to title this section “the brain of the program,” but it made more sense to say storage and you will see why in later. Once I was able to use the user input for an API request, I wanted to direct the user to another HTML page with their request. The problem is everytime a new page loads, the javascript program restarts and program variables are erased. I needed to save the data I wanted the user to see from page to page so I needed some type of storage. Luckily, localStorage came to the rescue. In essence, this function sets a variable equal to something then stores it for you to utilize it in another page.
``` javascript
// Setting a local storage variable
localStorage.setItem("globalImg",image)

// Using It
localStorage.getItem("globalImg")

```
## Takeaways and Next Steps
My biggest takeaway involved choosing comfort over effectiveness when learning a new topic. Aforementioned, when I came to this topic there were multiple of ways in which I could have received the input utilizing the DOM library, but I was constantly confused and did not grasp the concept very well. Therefore, I resorted to utilizing a more comfortable and familiar method in order to actually learn the way javascript and HTML can be used in forms. My next step would be to learn how to authenticate APIs using javascript. Currently, it seems very difficult because it involves learning node.js. More importantly, I plan to draft and finalize my final app plan this week in order to acquire a clear vision on how I will divide my work effectively in the next few weeks in order to attain my MVP.

