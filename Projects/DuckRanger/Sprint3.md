 # Sprint 3 

I'm still dabbling with what I'm doing here but I think I might have goal oriented rahter than time oriented sprints. This way at the start of a sprint I know I'm going to focus on X Design task X Coding task etc...

That way I'm not letting myself be overflowed by an infinite number of tasks. Of course some task are note finite but I'll see as I go. 

Anyway the weather is MUCH more bearable now and it's time to work with ducks. 

![alt text](Projects/DuckRanger/Screenshots/image.png)
> A wonderful wood duck

## Goals 

For this sprint this is what I want to focus on :

#### Design
- Design the combo system
- Design the support system
  
#### Producing 
- Create a Moscow like doc for the project

#### Code
- Implement the combo system
- Implement the support system
- Create a design sheet


#### Art
- Create a first batch of rough Background elements  
- Draw at least 2 New ducks 
  
#### R&D
- Look for how to do particles in Godot 
- Look at other Dev Log to see if I can write stuff better
  

## Design 
### Combo System 

As I was saying in the last dev log, in the original Pokémon Ranger the combo system adds a fourth of the capture rate every 5 loops. 

I like this idea of every **X loops the combo adds Y% of the base capture rate**. A nice bonus is that the X and Y value can be variables affected by Ducks stats. 

I came with this formula for the capture rate combo calculator :

```
CaptureRate = OriginalCaptureRate + Loops%LoopCombo*(ComboPercentage of OriginalCaptureRate)
```

The capture rate is also clamped with a **max combo value**. This way the game is less breakable and it's a new stats that can be toyed with ducks' stats and abilities. 

With this I can precisely know how many loop is needed to capture a Duck and I can adapt their stats to the best possible capture rate at any moment in the game. 

In one of my next sprints I'll try dabbling with capture rate when multiples ducks are circled by the same loop. 

![[PkmnGS_WobbuffetCapture.png]]

I then had to think about my stats. What my starting capture rate is going to be ? What my final capture rate is going to be ? 

I obviously can't decide that now without test and stuffs but I can decide of a magnitude for the game. I think I'm going to focus on making a working system then I'll take care of the metrics. 
#TOBECONTINUED
### Support System 
## Producing
## Code

### Combo and feedbacks

To implement the combo system I simply put the formula from my design before sending the capture rate to the capturable. 

```cs
private void CapturableOnCircle(Capturable capturable)  
{  
    _loop++;  
    var processedCaptureRate = _captureRate + (_loop/_loopCombo) * (int)(MathF.Round(_comboPercent * _captureRate));  
    capturable.RiseCaptureRate(Math.Clamp(processedCaptureRate,0,_maxCaptureRate));  
}
```
> Part of the *CaptureManager.cs* Script

Because it was pretty simple and I wanted to spend a little extra time on this task I dabbled with **ParticleEffect** on Godot. I learned that if you use a **ViewportTexture** you can use a viewport content as a particle. So i did this! I created a label in a viewport and assigned this as a particle system. The particle system is enabled and the label is updated via signal when the capturable is looped. 

![[G_Combo.gif]]

### Debugging Tools

- Binded to signal 
- 
## Art
## R&D

### Design and productivity tools

In the age of AI and low data privacy I wanted to search for new tools to use instead of SaaS. So i needed a replacement for Google Docs/Sheets for my design documents and my producing documents. 

I was intrigued by **Obsidian** for a while and I figured it was a good opportunity to try it. Before testing it I looked for alternative and tried **Trilium Note**. I'm going to use Obsidian for my projects and   
## Conclusion
### TL;DR
### Idea box

- For the feedbacks of the combo I can change the colors every combo and add a new random color for example OR I can add a mathematical formula that create new random colors that tends to certain tones or contrasts.
- As reward for curious player I can add line renderer skin. 
- I thought about some negative status that could be inflicted by Ducks like lowering capture rate, increasing the number of loops needed for combos, make the pointer slower or line tiner for example.
- Feedback displaying the combo (Number of loops)
- Ducks have to lose some capture points if not captured for some times
- Particles for a successful loop and a successful capture
### What did I learned 

- Basic understanding of the Godot Particle system
- You can put viewport in particles (think of the possibilities)