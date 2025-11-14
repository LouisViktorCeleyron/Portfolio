# Intro
> Personal Project    
> 2 Months   
> Unity - C#  
 
![Banner](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Intro/Pictures/Banner.png)

## Context 
>[!Warning]
>Hola que tal

In the summer of 2024 I decided to make a system based game to have something to show and to share to my student as an exemple. 

These last years I have been playing a lot of Deckbuilding Rogue like (Balatro, Slay the spire, Astrea, Wildfrost etc...) and I have been thinking about my take on the genre for a little while. The project I wanted to do for my students was the occasion to put this Idea to the test. 

![Deckbuilders](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Intro/Pictures/Banner.png)

My idea was to make a game where the player can launch action by combining elements. I started brainstorming and a lot of ideas came to my mind so I launched Unity and worked on the first prototype. 


## **Concept**

The game is a rogue like deckbuilder. 

The elevator pitch of the game is : 

> *Battle oponent in turn based battle by combining elements to create powerful and various consequences. Each victory will grant you more elements and ressources to experiments and find the most powerfull combos to face randomly generated foes*

Here's what a standard game would look like :

> * Choose a starter deck of elements
> * Enter the 1st realm and fight the 1st foe 
> * In battle drag'n'drop elements onto another to launch consequences
> * Each time you'll defeat a foe you'll win monney and play the lotterie to win a random element to add to your deck
> * At the end of the battle you do not heal
> * From time to time you'll enter a shop  or rest area
> * At the end of every realms you fight a boss, once you win you enter the next realm and heal all of your HP 
> * If you loose you'll start all over again but you can try a new starter deck and/or try to manages your ressources differently

## TL;DR

This devlog document is a lot more long that I anticipated so If you only want to know the big lines of my experience on this project :

- I have a finished prototype with 3 level and a fully functioning system
- I used my Unity Editor skills and my sens of code architecture to create a very flexible project
- I made few mistake and faced few problems, mainly with some deep editor related stuffs and I'm happy to have learned a lot thanks to that
- I needed to polish an old Unity plugin that I made so I finished it ! ([link here]())
- I'm proud of my documentation, my design and code architecture really helped me to not go in every directions and to keep the scope of the project realistic
- I had, like always, a lot more trouble making simple stuffs than making a big system 

[Link to download the prototype]()
[Link to the project repo]()
[Link to the project documentation](https://docs.google.com/spreadsheets/d/1h9zG16REBftnj_vJVHQ-YPOQ1HlRdiy30p6ICMqrrNc/edit?usp=sharing)

Anyhow if you have the time to read the whole devlog I really appreciate it 😀

## **Concept** Part II

### Glossary

> **Element** : *Your deck is filled with elements. By combining them you can launch consequences.*

> **Consequences** :  *Theses are the actions you can launch with elements, your foes will launch one consequence every turn too. They can buff you, heal, inflict dammage and more !*

> **Status Effects** : Some consequences will give you or your opponent status effects. They can do a lot of different things like healing or damaging but also affect your precision, block dammages, and even generate elements!

> **Rest Area** : That's where you can either delete elements from your deck or heal few HP

> **Shop** : That's where you can buy new elements to add to your deck


### Battle

![Deckbuilders](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Intro/Pictures/Banner.png)

The Battle screen looks like that :


> * You can drag elements to eachother to preview what consequence this combo will unleash.
> * If you release the mouse the consequence will be launched.
> * You can hover your mouth over the foe to preview what they will do
> * You and your foe both have a life bar. 
> * You can see what status effects you and your foe are under.
> * At any time during your turn you can press the "End turn" button to end your turn
> * At the start of your turn, you draw 2 elements among the ones available in your deck 
> * If your deck is empty your discard pile shuffles to your deck 
> * Once either your or the foe's HP drop bellow 0 the battle ends

### Map

The map screen looks like that, click on the swords icons to go to battle, to the bed icons to go to the rest area and to the bag icons to go to the shop. 



## **1st Scope and future of the project**

I wanted to make a 1st prototype of the project that would allow me to experiment with the concept and show a peak of the gameplay loop without going in all directions.

Here's what I hoped to do at the start of the project and what I've done.

### Gameplay 🎮

|Objective|Done|Comment|
|---|---|---|
|3 Realms|✅||
|4 types of foes and 1 boss/Realm|✅||
|10ish elements|✅||
|20ish Consequences|✅||
|Small Feedbacks and Fxs|✅|Really small stuffs like fade in/out animations HP update etc...|
|Shop and rest area|✅|
|Ergonomic and QOL|✴️|You can preview what the foe is going to do and what combinaison your going to have but some stuffs are missing|
|Job System|❌|I did not implement jobs with abilities and stufss but you can choose differents starting decks|
|Relics and items|❌|I focused on having a strong system and didn't want to mess it up by adding more stuffs|

### Tech 🔧

|Objective|Done|Comment|
|---|---|---|
|Scriptable Object architecture that'll allow me to create a lot of consequences|✅||
|Tools that facilitate consequence management|✅||
|Observer pattern Implementation for UI and feedbacks|✅||
|Procedural management |✴️|Each foe is randomly selected from a selected pool and the items you can buy are random but there are no procedure or algorithme yet|
|InGame Debug Tools|✅| I have cheat Code and stuff ingame


### Future of the Project

Now that I programmed a strong and flexible system, I would like to add more content (elements, consequences, status, etc...) and a true structure to the game. 

Here's the stuffs I have been thinking about :

- Job/Character system
- Skins
- Relics and Items
- Game Progression (Unlockable Decks, elements, etc...)
- 2 Currency (one in run/ one to unlock stuffs outside of the runs)
- Other Game mode (Puzzle/Challenge, etc...)
- Seed system
- 

I'm writing everything without taking the scope in consideration. I know some of this stuff is scope ++++++!

## Architecture

I wanted to make a system that allowed me to create a lot of content quickly. To do that I had to have a really good hierarchy and architecture.

You can find here a rough diagram of my code structure. 

![Architecture](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Intro/Pictures/IMG_Architecture.png)

### Elements

I started by coding Elements and consequences. This stuff would be really data oriented so I choosed to use Unity's Scriptable Object. 

Elements are key part of the project structure but they didn't need to be realy complicated. They only needed to have informations that will be used by other scripts. 

A name, a base price for the shop, a description, a color, and few elements that could combine with it to gives hint to the player. 

```cs 
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

[CreateAssetMenu(fileName ="New Element", menuName ="MyStuffs/Element")]
public class Element : ScriptableObject
{
    public Sprite icone;
    public int basePrice=111;
    public string description;
    public Color color;
    public Element[] potentialMix;


    public string GetColoredElementName()
    {
        return name.ColorizeString(color);
    }
}
```
In Unity Elements Scriptable Objects look like this :

![Elements]()

### Consequences

On the other hand, consequences needed to be a bit more complex. 
I needed to make consequences to have theses caracteristics : 
- Easy to call in battle,
- Easy to experiment with (add and remove new behaviour, status, etc...)
- Can be called by the player and the foes

The best course of action for me was to use a mix of the composite, decorator, and observer design pattern. 

I created an abstract parent Consequence class that will be called by the *Fighting Instance* (Player character and foes) in battle, and will manage : 

- Who call the consequence
- Who is the target of the consequence
- If the consequence have consequence special effect (or CSE) (Discarding elements, healing, drawing new elements, etc...) ([see bellow](#cse))
- Some data stuffs (name, description, icon, etc...)

Every consequence have a ***Call Consequence*** function that will be called by the *Fighting Instance*. This function has two parameters, both are *Fighting Instances* the launcher and their opponent.

> ***Call Consequence*** 1st determine who is the target (launcher or opponent), call the main consequence (dammage, status, etc...) then, if the consequence have CSE they are called, then feedbacks are called. 

[The Consequence Script]()

I then think about the best way to use inheritance on this class to have the least amount of child classes: 

- I needed a class that would inflict status to the target (more on that later)
- I needed the status class to have a child class that might inflict status and add or remove HP to the target.
- I needed a special class for the factory consequences. 

I know I could have merge the consequence parent class and the status consequence class but I liked the Idea to have a non-status related parent 

#### Status Consequences

The status were a huge part of the project, a lot more than I anticipated, but I'm really satisfied with the result. 

For the status I choose to only use inheritance to structure and observer to apply them. 

> The *FightingInstances* have few delegates (at the start and end of the turn, when attacked, etc...) the status structure goal is to call every status at the right time with theses delegates

The parent class has :
- A ref to the target, so the status can affect its stats, hp, etc...
- An amount  variable, that can be changed by coresponding methods 
- A Subscribe and Unsubscribe methods to choose to which one of the delegates this status will be bind
- UI stuffs I will describe more [here](#display-of-status-in-ui)


The amount variable is used in different ways for every status effects, some will define the power of the status, some the number of turns the status will affect the target etc...

I faced few problems to create a system that would take account of most of possible exceptions. That's why I have methods called before and after the amount is changed, when the status is inflicted, when the status is removed, etc... I tried to not overload my scripts though !

[The folder where you can find all status related scripts]()


#### CSE

CSE are extra effect that could be called by any consequences, to avoid an inheritance hell (like having a class for status effect that can draw, one for attack that can draw, one for attack that can draw AND heal, etc...) I used the decorator pattern.

I created a class called *ConsequenceSpecialEffect*, i created a child class for every type of CSE I needed, and I created a *CseCollection* to avoid making the Consequence Script too messy. 

I had a problem to make the CSE as easy as possible to edit in the inspector, but I talk a bit more about this issue [here](#editor)

I'm pretty happy of how the CSE turned out: I can put as many as I want in my consequences and they are highly editable. 
The only thing a bit annoying is to have to create a new class for every kind of CSE. 

You can see how they turned out in the editor: 
![CSE](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/Intro/Pictures/IMG_CSE.png)

[The CseCollection Script]()

[The ConsequenceSpecialEffect Script]()



## Combinator and Battle Scene

## UI

### Display of status in UI

## Managers

### Battle Manager

## Other stuffs

### Colorizing my Debug Logs

### Descriptions

## Problems I encountered

### Infinite Loop

### Editor 


### Simple stuffs 

# Game informations and guide

You can find my game design doc, with every elements, combinaison, etc... [here](https://docs.google.com/spreadsheets/d/1h9zG16REBftnj_vJVHQ-YPOQ1HlRdiy30p6ICMqrrNc/edit?usp=sharing)

***

[Get back to the project page](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/Projects/MyProjects.md)  
[Get back to the main page](https://github.com/LouisViktorCeleyron/Portfolio/blob/master/README.md)
