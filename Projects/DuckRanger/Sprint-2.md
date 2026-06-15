# Sprint 2 -

> Start : 08/06/2026  
> End : 21/06/2026

After few month without looking at the project for personal reasons I slowly noted some ideas until I decided to fully get back on it. 

I was pleased to see that my code wasn't so bad even if I could always improve. After looking at my last devlog I identified some goals for this sprint. 

I'm also not sure of which structure is the best to support the capture gameplay (adventure or rogue-like or something else). I like the scalability of the rogue like but I also like the mystery/easter-egg/search for the rare encounters of the adventure games. 

## Goals 

### Producing
- Make a Moscow for the project
- Put this devlog and the project on my website
- Decide a clear objective/project end  
- Godot R&D

### Design 
- Decide between linear adventure or roguelike
- If I decide start working on environement/Level/Biome etc....
- Design secondary mechanics (How to use support ducks, XP, Shops etc....)
- Document and design some duck abilities 
  
### Code-
- Implement a singleton manager system
- Make the capture mechanic work on more than one ducks
- Make the duck attack system 
- Make the duck support system 
- Start working on the support gameplay loop (xp/Shop/etc...)
### Art 
- Try particles in godot
- Try to do some mockup/rough background
- Try to do some mockup/rough UI 
- Low priority but it's always fun to design ducks


## Design 

## Coding

### Manager system
### Refactoring the capture mechanic

I'm moving a lot of the code that was in the Cursor script into a **CaptureManager**. This way I can access it frome anywhere in the game and add tuto, bonus or other stuffs. 

I also ditched the Geometry2D.Polygon approach to use another Area2D as I did for the breaking line mechanic. This way I can detect multiples object at once with GetOverlappingBoddies(). 


Nevermind I tried a shapecast2D update cast
pb concave convex
## Art

## Conclusion

### TL;DR

|Goal   | Description                |Done|
|---|----------------|--|
|  **Making the line**    | A Line 2D follow the mouse when the right click is pressed |✔️                         
|  **Closing the circle**    | The line detect when it's making a circles |✔️
|  **Detecting inside**    | I can detect what's indside the cirle, for now it only works for one duck|➖
|  **Duck Behaviour**    | The duck can only move randomly on the screen|➖
|  **Duck interraction**    | The duck can break your line but not attack|➖
|  **Hierachy**    | What I did was functional but I can factorise more stuff (especialy around the duck behaviour)|➖
|  **Art** | I started to dabble in pixel art |➖

### Idea box

### What did I learned 
- I deepend my undertanding of area 2D especially since GetOverlappingBody did not work