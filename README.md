# Final_Project_nzha0346_9103_tut1

# **Apple tree_Time Based**

## **Project Overview**

This is an interactive animation project based on p5. js, showcasing the complete lifecycle of an apple tree from growth to fruiting to apple drop. Based on our group assignment, I chose Time Based animation as my personal creative direction for this project.

![image of tree](image.png)

## **Interaction description**
### **1.Auto-play :** 
Upon opening the page, the apple tree will automatically commence its growth process (5-10 seconds).

### **2.Restart :** 
Press the spacebar to restart the entire growth process, generating a brand-new random apple tree each time.

### **3.Gravity control :** 
During the apple-falling phase, press the spacebar to toggle gravity direction (upwards/downwards).

## **Personal Creative Realisation** 
**Animation Drive Method:** 
I selected time-based animation to drive my personal code, employing precise temporal control to simulate the natural growth process of trees.

**Animation Characteristics and Distinctiveness:** 
Unlike other group members, my implementation focuses on

**Sequential Growth Animation:** 
Branches grow hierarchically, progressing from the main trunk to smaller branches

## **Progressive Apple Appearance** 
Apples emerge only after branch growth is complete, adhering to natural patterns

## **Randomised Elements** 
Tree form, apple positions, and timing are randomly generated each iteration

## **Complete Lifecycle**
For my part, I opted to employ time-based animation to drive the entire scene. My objective was to have the apple tree progress from an initial state through a complete, natural life cycle: from branch growth to fruit formation, culminating in the fruit's eventual fall.

### 1. **Time Control** 
let growthStart = 0;
let totalGrowDuration = 7000;
let rawSegments = [];
let appleSpecs = [];

### 2. **Branch Growth Animationz**
-By extending the Segment class, add time control attributes and interpolation calculations

 class Segment{
    constructor(){
         this.revealTime = 0;
        this.growDuration = 500;
    }
    draw(){
        let progress = contrain((currentTime - this. revearlTime) / this.growDuration, 0, 1);
        let  X = lerp(this.x, this.x2, progress);
        let  Y = lerp(this.y, this.y2, progress);
    }
 }

### 3.**Randomised design**
 -Morphological randomness: Random variation in branch bifurcation angles
  -Temporal randomness: Random shifts in growth duration and element emergence timing
 -Positional randomness: Random distribution of apples along branches

   let angleOffsetL = random(radians(30), radians(90));
   let angleOffsetR = random(radians(25), radians(85));
   let jitter = random(-radians(8), radians(8));

### 4.**Chronological Sequence**
Apples appear strictly after their respective branches have completed growth

  appearTime = seg.revealTime + seg.growDuration + random();

 These refinements collectively create a dynamic effect where growth progresses sequentially from trunk to twig, apples naturally form and randomly fall, generating uniquely shaped appple trees with each reset.

# **Summary** 
By combining time control(millis, revearlTime), smooth animation(lerp), randomness(random), and layering order, I successfully simulated an apple tree growth animation through code. This animation adheres to natural laws(branches appear first, followed by fruit, then falling) while remaining rich in variation and charm. With each interaction, users witness a sapling possessing its own unique life trajectory.

