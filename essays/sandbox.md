---
layout: essay
type: essay
title: Personal Experiences With RadGrad's SandBoxing
# All dates must be YYYY-MM-DD format!
date: 2021-05-21
labels:
  - Sandbox
  - HTML
  - TypeScript
---
RadGrad's coding environment feels quite similar, but very different in many areas compared to InternAloha's coding environment. These tasks are problems that I'm aware of, but are handled in a way I'm unfamiliar with, which makes the experience much more fun.

## Task 1
This task is the standard starter problem for most ICS students, but the approach is something quite new to me. The PageLayout and RadGradSegment components remind me of Semantic UI's but with adding style and other elements as consts. It's also great that typescript forces the code to be exactly how it is intended.

![image](https://user-images.githubusercontent.com/60155925/119190428-0e316900-ba19-11eb-8960-4e5e424e9024.png)

This is how the task resulted as:

![image](https://user-images.githubusercontent.com/60155925/119189388-b8a88c80-ba17-11eb-88ab-b5dd5c83f426.png)

## Task 2
This task has a segment that displays the user who is looking at this sandbox page as well as the user who created this page. The difficulty for me was understanding how to display grab a user from the router URL path. After doing a bit of searching, I realized that you can grab parameters of the URL with ```useParams()```. With the username from the URL, I matched it within the Profiles collection to find the username. So I ultimately grabbed the username from the URL, and displayed it within the segment. Then I defined current user name using Meteor. This was my solution:

![image](https://user-images.githubusercontent.com/60155925/119194568-fa890100-ba1e-11eb-9aec-08ff68fed3cf.png)

This is when the same user navigates to my sandbox:

![image](https://user-images.githubusercontent.com/60155925/119193666-a6315180-ba1d-11eb-9388-2e9c95ea6546.png)

This is when a different user uses the same URL path:

![image](https://user-images.githubusercontent.com/60155925/119194685-2ad09f80-ba1f-11eb-9b75-53c92ec7d0f4.png)

## Task 3
Task 3 has us add a random career card everytime you reload the page. This one stumped me because my preconceived idea to approach this problem was using ```<Card.Group>``` and mapping a random singular card since I assumed that the career data within the career goals tab used a similar method to display it's pages. After talking to a few members, I decided to create the data from scratch by importing data from the careerGoals collection. Getting the length was simple enough, but mapping random career data proved a little difficult. After searching the Markdown usage and looking at the parameters of careerGoal, I modified the segment to show random items. 

<img class="ui center image" src="../images/Task3.gif">

## Task 4
Task 4 has us now add labels to a segment connected our name so that if a tag is in our profile, it will highlight. This problem is much easier after finishing Task 3 as it uses the same concept of importing collections withTracker and adding them to an interface the component will use. The only problem I had was understanding what slugs were at first, but besides that, it was a good refresher on mapping items with their unique id's and displaying them. Another small thing that I wasn't aware of at first was there were more students than in the example page, which was attributed to changing ```.findNonReried();``` to ```.find({ isAlumni: false }).fetch()``` in order to fix it.

![image](https://user-images.githubusercontent.com/60155925/119240582-3ccc4400-baec-11eb-956f-c2df78596ac8.png)





