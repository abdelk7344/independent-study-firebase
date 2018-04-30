# Pause...Deploying Messenger 2.0

## A Brief and Breezy Intro
I wanted to do so much week four; however, everything did not go as planned. I was time constrained and conflicted with another firebase issue that I had not taken into account. After completing the lab, I noticed that people cannot actually utilize it because it was in development mode. Therefore, I dedicate this week to trying to quickly figure that out and then learning javascript with APIs. Unfortunately, I was able to only deploy my friendly web chat app, but, fortunately, you can utilize this app by clicking this [link](https://friendlywebchat-5f5ac.firebaseapp.com). In the following entry, I will briefly talk about the challenges I faced deploying this web application utilizing firebase.

## Database Security Rules 
This was an optional step before deployment, but these rules ensure that only users can read and write their own Firebase Cloud Messaging device tokens. I followed step one correctly and updated firebase rules with the rule given in the lab; however; I kept receiving an error once I commanded database deployment. After multiple of hours of debugging, I noticed that even though firebase.json did include all the code snippets that the lab required, it also had additional code that might have hindered the program from actually function correctly. Therefore, I took those additional code lines out and the deployment was successful. 

## Storage Security Rules
I have continuously noticed that even a very tiny mistake can totally hinder an application. I am the type coder that gets really excited about actually working and getting the end product that I fly through it. However, as excitement encourages speed, it also welcomes a lot of mistakes. In the file storage.rules, a single letter difference made the difference between a running and crashing program. It took me less than a second to make such a mistake and even more time trying to fix it.

## Deploying
Firebase is really cool because of its simple deployment program. I just needed to command “firebase deploy” and select both the cloud messaging and database features to cannot get my web app to deploy. 

Really Important Tip: If you do want to change something to your app after deployment you can type the same command and it will re-deploy

## Takeaways and Next Steps 

My single and most important takeaway would be dedicated to the importance of patience. I know that sometimes it's hard to contain excitement or frustration, but, when coding, these emotions tend to lead you to a lot of mistakes. Therefore, I have made n effective system for myself in order to check for any syntax or code mistakes. First, I will read the written code twice. Then, I will create a comment for every line I code(even for the simple ones in order to attain that constituency). On the other hand, my next step would be to undoubtedly to learn Javascript with APIs this week in order to develop an app that I will utilize with firebase in my final project. 