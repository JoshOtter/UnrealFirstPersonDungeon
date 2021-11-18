# UnrealFirstPersonDungeon
## Introduction
As part of The Tech Academy's Game Development Boot Camp, I built a level for a First-Person Dungeon Exploring game as a Live Project. The project was set up as a two week sprint. My level was one in a larger project to which many students had contributed using Unreal Engine 4. My specific task was to build a level that included puzzles to solve and traps to avoid or overcome. Using blueprints to code the logic for both the puzzles and the traps, I designed and built my own level with its own unique functionality. Through this project, I gained proficiency using blueprints and Unreal Engine components, like its static mesh and sequencing systems. I learned to enjoy designing my blueprints to make the game actors behave in the way I wanted.

I also gained experience working in a collaborative environment that made use of Agile/Scrum methodology and DevOps. I took part in daily standup meetings as well as a sprint planning meeting, and a sprint retrospective. I also sent daily reports to my Live Project manager as part of keeping track of my progress throughout the two week period. The project was also broken up into user stories, which I completed one at a time and turned in for review through Azure DevOps.

I also gained additional experience using GitHub desktop for version control. After I cloned the project to my computer, I made a new branch for every story, kept the branches updated with the main branch, made frequent commits as I progressed through each story, and created a pull request through Azure DevOps when I finished each one. Then I moved the finished story from the active column to resolved so the instructors could review and decide whether or not to approve my pull request.

Below is a sumary of each story I resolved with screenshots and gifs showing the level features and the blueprints that run their functionality. You can find the screenshots and gifs in the folders of this repository.

## Table of Contents
- [Story 1: Plan, Design, and Block In](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#story-1-plan-design-and-block-in)
- [Story 2: Replace Brushes with Meshes](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#story-2-replace-brushes-with-meshes)
- [Story 3: Puzzles](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#story-3-puzzles)
- [Story 4: Traps](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#story-4-traps)
- [Story 5: Finalize Props](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#story-5-finalize-props)
## Story 1: Plan, Design, and Block In
For this story, I decided how many rooms I wanted to include in my level and decided how to lay them out. I also made a plan for the main puzzles and traps I wanted focus the design of the level around. I then drew a top down sketch of the level and used that as a basis for building it with brushes. I also added a player start object at the beginning of the level so I could test the initial design. Unfortunately, I forgot to take a screenshot at this stage.
## Story 2: Replace Brushes with Meshes
I went through the level and replaced the brushes with meshes. There were some brushes that I initially applied textures to, but I later learned from my project manager the importance of using meshes instead. I adjusted some of the level construction to work better with the meshes and added some of the large architectual objects, like pillars, doors, trim and other larger objects.

Below are screenshots of each room:

The Entry
![Entry](https://user-images.githubusercontent.com/87107050/142470852-6681ff8e-fc58-4d80-a41d-30bc96dda7c8.PNG)

The Main Hall
![MainStairs](https://user-images.githubusercontent.com/87107050/142471058-82994b96-ade5-40e7-b5ae-cd5ccd1e8a52.PNG)

The Prison
![Prison](https://user-images.githubusercontent.com/87107050/142471122-a06be4e3-619d-4da0-999b-2219f9d935eb.PNG)

The Experiment Room
![ExperimentRoom](https://user-images.githubusercontent.com/87107050/142471157-a5b35fcb-04f7-49d2-a25a-f9df2cfae2f9.PNG)

The Furnace Room
![Furnace](https://user-images.githubusercontent.com/87107050/142471195-a3d13f48-e93e-4283-bc06-00ab5be43b32.PNG)

The Cultic Sanctuary
![Sanctuary](https://user-images.githubusercontent.com/87107050/142471245-c298e041-8dd7-4798-80a8-59763b7a2292.PNG)
## Story 3: Puzzles
- [Main Button Puzzle](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#main-button-puzzle)
  - [Find the Right Button](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#find-the-right-button)
  - [Get the Key to Unlock the Prison](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#get-the-key-to-unlock-the-prison)
  - [Move the Pot to Reach a Button](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#move-the-pot-to-reach-a-button)
  - [Move the False Wall](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#move-the-false-wall)
### Main Button Puzzle
The main puzzle consists of a series of buttons the player must press in the correct order in order to light the candles on the table in the main hall and unlock the door that leads out of the level. Within this puzzle, there are four smaller puzzles the player must solve as they find the buttons in the adjacent rooms. Each of the four buttons has a blueprint that references the end door actor to connect to it's booleans that tell it whether or not the candles have been lit. Here is the blueprint for the first candle. The other three are very similar, have slightly different logic when checking which candles are lit or unlit.
![Button1Part1](https://user-images.githubusercontent.com/87107050/142486184-aeb11dd9-b082-4617-b12e-73fec14bc906.PNG)
![Button1Part2](https://user-images.githubusercontent.com/87107050/142486194-84d9eeb2-ed27-4c84-a37f-0160532f84fb.PNG)
Here you can see an additional event I added that destroys any active flame emitters on the candles. The blueprints call this function any time the player clicks the buttons out of order or if they press one of the buttons more than once.
![BlowOutCandles](https://user-images.githubusercontent.com/87107050/142486636-a8ea5078-e427-47d2-97cf-6b459b79060e.PNG)

You may also have noticed that the first button activates an array of pit fire emitters that turns on the furnace.

![ActivatingFurnace](https://user-images.githubusercontent.com/87107050/142487383-0ac62da4-ce7c-4acb-bc65-a9707370fb71.gif)

This button also activates the first candle to be lit.

![FirstCandleLit](https://user-images.githubusercontent.com/87107050/142488102-97112023-d062-44ef-abd1-1fa489217b44.gif)
#### Find the Right Button
#### Get the Key to Unlock the Prison
#### Move the Pot to Reach a Button
#### Move the False Wall
## Story 4: Traps
## Story 5: Finalize Props
