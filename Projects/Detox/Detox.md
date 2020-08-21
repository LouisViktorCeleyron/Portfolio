# Detox

> La Belle Games - Montreuil  
> Internship - 2019 - 1 Month  
> Unity 3D - C#  
> Team of 2  
> Tool Design and Gameplay Programming  

![Banner](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/Banner.png)


## Context

Detox, is a **platform/couch game** made during a Game Jam. During my internship, I was asked to **restart the project from scratch** and to create **tools to improve the workflow**. I had to work from an office but my colleague and I did not have the sames schedules, I worked a month on this project and I had to change projects very quickly so I didn't have the time to finish what I had started on this project.
​

## What I Did 

I restarted the project from scratch so I had to program the character movements. I used and improved some of my personal tools to quickly prototype the 3c and focus on my main task : a **Level Editor**. 

I did a lot of tests to find the best way to create a Level Editor simple and easy to use.  Eventually I created a **string based serialization system** and I put my **level editor in a build** Instead of an Unity Editor Window.
I wanted to create a flexible tool, to ease the workflow and  I wanted to challenge myself by testing something new!

So I created an executable build, with another unity project, which allow users to create a Level and export it in .txt. In Unity I used a pulling based system on Unity who load the .txt and uses an algorythm to create the right object at the right place.

With this method the level creation is fully independant from unity and it's way easier to optimise than using a big UnityEdito window.

I only worked a month on this project so I couldn't finish my Editor but I implemented a system to create walls and moving platforms. 

***Example of Level Design Code***
![Example of Level Design Code](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/Code.png)


![And It's result](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/Exemple_Of_Level.png)
### And It's result!  


![The Level Editor Executable](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/LevelEditor.png)  
### The Level Editor Executable   


## What I Learned

This internship pushed me to go **out of my comfort zone** of the Unity Editor to test new methods, new software and  new languages. I could test **new ways to create and implement tools** and I really enjoyed it. I also learned the constraint of a production when you can change projects from one day to another. 
​

[Get back to the project pages](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/MyProjects.md)