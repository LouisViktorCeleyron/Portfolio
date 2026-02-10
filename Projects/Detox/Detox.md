# Detox

> La Belle Games - Montreuil  
> Internship - 2019 - 1 Month  
> Unity 3D - C#  
> Team of 2  
> Tool Design and Gameplay Programming  

![Banner](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/Banner.png)


## Context

Detox, is a **platform/couch game** made during a Game Jam. During my internship, I was asked to **restart the project from scratch** and to create **tools to improve the workflow**. I worked from an office but my colleague and I did not have the sames schedules, I worked a month on this project and I had to change projects very quickly so I didn't have the time to finish what I had started on this project.
​

## What I Did 

I restarted the project from scratch so I programed the character movements. I used and improved some of my personal tools to quickly prototype a physics and the 3c and focus on my main task : a **Level Editor**. 

I did a lot of tests to find the best way to create a Level Editor simple and easy to use.  Eventually I created a **string based serialization system** and I put my **level editor in a build** Instead of an Unity Editor Window.
I wanted to create a flexible tool, to ease the workflow and  I wanted to challenge myself by testing something new!

So I created an executable build, with another unity project, which allow users to create a Level and export it in .txt. In Unity I used a pulling based system on Unity who load the .txt and uses an algorythm to create the right object at the right place.

With this method the level creation is fully independant from unity and it's way easier to optimise than using a big UnityEdito window.

I only worked a month on this project so I couldn't finish my Editor but I implemented a system to create walls platforms but also select them to make them move. 


***Creation of a Level***  
![The Level Editor Executable](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Gifs/DetoxLevelCreation.gif)     

***The Level Serialization Code***  
```c++
4HN7m1102WALLEA1~1Vv3m1002WALLEA1~3885m0902WALLEA1~1Nyjm0802WALLEA1~0Btgm0702WALLEA1~Rl54m0602WALLEA1~Dsj5m0502WALLEA1~95Q0m0402WALLEA1~G303m0302WALLEA1~j7h0m0202WALLEA1~j3x2m0102WALLEA1~LZ2Wp0002WALLEA1~YN6Ip0102WALLEA1~K094p0202WALLEA1~Td58p0302WALLEA1~P2lMp0402WALLEA1~4Zi7p0502WALLEA1~4624p0602WALLEA1~F8X9p0702WALLEA1~4F26p0802WALLEA1~L57Vp0902WALLEA1~1Gz6p1002WALLEA1~5V7yp1102WALLEA1~5om1p1202WALLEA5~7653m1202WALLEA7~TXaWm1201WALLEA4~7HEym1200WALLEA4~z6m7p1201WALLEA3~n1Rmp1200WALLEA3~eAH5p1101WALLEA0~51rgp1100WALLEA0~3u7Sp1001WALLEA0~0h3dp0901WALLEA0~2Kkbp0900WALLEA0~3B2up0800WALLEA0~50RHp0700WALLEA0~iLF8p0600WALLEA0~85E7p0500WALLEA0~Wv92p0400WALLEA0~1B4ep0300WALLEA0~Vxf0p0200WALLEA0~233Gp0100WALLEA0~S693p0000WALLEA0~87ohm0100WALLEA0~512Tm0200WALLEA0~CiA5m0300WALLEA0~lD1Lm0400WALLEA0~Xs80m0500WALLEA0~3W89m0600WALLEA0~2r7cm0700WALLEA0~82Esm0800WALLEA0~SNT5m0900WALLEA0~P238m1000WALLEA0~fo96m1100WALLEA0~19aEm1101WALLEA0~KHI5m1001WALLEA0~8t8xm0901WALLEA0~vR42m0801WALLEA0~04pXm0701WALLEA0~YMy9m0601WALLEA0~x91qm0501WALLEA0~93dTm0401WALLEA0~1wr7m0301WALLEA0~46x2m0201WALLEA0~axYgm0101WALLEA0~75atp0201WALLEA0~l31Up0101WALLEA0~lJAWp0001WALLEA0~CoW5p0301WALLEA0~4jE9p0401WALLEA0~2800p0501WALLEA0~BHZSp0601WALLEA0~hVpBp0701WALLEA0~4fq1p0801WALLEA0~A129p1000WALLEA0~Ep58m1007PLALE2m1007²~qfo4m0907PLALE2m0907²~7466m0807PLALE2m0807²~5779m0707PLALE2m0707²~179hm0607PLALE2m0607²~z653m0507PLALE2m0507²~312Np0507PLALE2p0507²~d0l1p0607PLALE2p0607²~6z3Cp0707PLALE2p0707²~1U3Pp0807PLALE2p0807²~yl49p0907PLALE2p0907²~084Wp1007PLALE2p1007²~264Em0212PLALE2m0212²m0510²p0110²~833am0112PLALE2m0112²m0410²p0210²~1Yq8p0012PLALE2p0012²m0310²p0310²~O3G8p0112PLALE2p0112²m0210²p0410²~oq32p0212PLALE2p0212²m0110²p0510²~5uNtp0312PLALE2p0312²p0010²p0610²~ 
```

***And It's result in game!***  
![And It's result](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Gifs/DetoxLevelExecution.gif)


***Exemple of behaviour I created for the 3C of the Game***  
![Behaviour I created for the 3C](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Detox/Pictures/ExempleOfInspector.png)

## What I Learned

This internship pushed me to go **out of my comfort zone** of the Unity Editor to test new methods, new software and  new languages. I could test **new ways to create and implement tools** and I really enjoyed it. I also learned the constraint of a production when you can change projects from one day to another. 
​
***
[Get back to the project page](https://louisviktorceleyron.github.io/Portfolio/Projects/MyProjects.md)  
[Get back to the main page](https://louisviktorceleyron.github.io/Portfolio/README.md)
