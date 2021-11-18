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
After pressing the first button, the player must find their way to the next button in the experiment room, where they are faced with six button options. Only one of them will light the candle, while the rest will activate the [trap floor](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#trap-floor).

![PressingButtonTwo](https://user-images.githubusercontent.com/87107050/142489457-5232f65c-9428-4649-aa35-8e739481f3ef.gif)

This will activate the second candle.

![SecondCandleLit](https://user-images.githubusercontent.com/87107050/142489886-6f768a2f-18d5-47f6-b632-f9a89aafa0c1.gif)

#### Get the Key to Unlock the Prison
Before the player can press the third button located in the prison, they must first find the key that unlocks the cell doors. When the player clicks on the key, it changes a boolean variable in the cell door blueprints and then destroys itsself to make it feel like the player has picked it up.

![KeyBlueprint](https://user-images.githubusercontent.com/87107050/142492389-49d378ff-ef6e-4817-b507-1b9dcf200590.PNG)
![PickingUpKey](https://user-images.githubusercontent.com/87107050/142492245-a68295e7-088c-4e32-b504-72c9e7ce0b92.gif)
![OpeningCellDoor](https://user-images.githubusercontent.com/87107050/142492948-89abcddf-fdd3-48b7-87bb-dbd0497e54d8.gif)

#### Move the Pot to Reach a Button
The next part of the puzzle comes when the player realized the third button is on the ceiling in one of the cells and that it cannot be reached from the ground or even by jumping. They have to find another solution, which is to push one of the pots from the other side of the cell under the button, so they can jump onto the pot and then jump up from there to click the button on the ceiling.

![JumpingButton](https://user-images.githubusercontent.com/87107050/142494519-f3508f59-4c02-4269-ab52-54f2d3d47f1b.gif)

At this point the third candle will be lit.

![ThirdCandleLit](https://user-images.githubusercontent.com/87107050/142495078-6dca3a5f-080d-4b9d-93f2-69554806e413.gif)

#### Move the False Wall
The final puzzle to get to the fourth button in the Sanctuary requires the player to light the two candles on the altar by clicking on both of them. When this is done, the false wall hiding the button will be removed.

![AltarCandles](https://user-images.githubusercontent.com/87107050/142495582-8c35dbd4-2c7f-4a89-9270-5d482007062e.PNG)
![AltarCandles](https://user-images.githubusercontent.com/87107050/142496067-41dbf5eb-0b48-4b0c-82da-581c4f6d618e.gif)

After the player clicks the fourth button, the final candle will be lit, and the player may open the door leading to the end of the level.

![FourthCandleLit](https://user-images.githubusercontent.com/87107050/142496891-f45e84ee-506a-4118-ae23-13e62c94d834.gif)
![ExitDoor](https://user-images.githubusercontent.com/87107050/142497517-9ed6fec3-b22f-43d9-9737-682be23ef189.gif)

## Story 4: Traps

- [Trap Floor](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#trap-floor)
- [Falling Cage](https://github.com/JoshOtter/UnrealFirstPersonDungeon/blob/main/README.md#falling-cage)
### Trap Floor
The first trap the player will encounter comes when he is looking for the second button among the six in the experiment room. For this trap I made a new mesh actor and built a new blueprint and made two sequences in which the trap floor opens and closes.

![TrapFloorButton](https://user-images.githubusercontent.com/87107050/142498688-7f9f9e6a-9948-4bcf-a153-a787a02c2fdc.PNG)

Here is the blueprint for the trap floor buttons:

![OpenTrapFloorFunction](https://user-images.githubusercontent.com/87107050/142498729-b07c779b-71a5-42f6-89a0-69f4f48e9206.PNG)

When the player clicks on one of these buttons while standing on the trap floor, they will fall into the furnace room and have to go back and try again. 

![PressingTrapButton](https://user-images.githubusercontent.com/87107050/142499407-42d00e16-0cbb-407d-92af-7b5ff05b68ad.gif)

### Falling Cage
The final and most annoying trap is a cage hidden in the shadows in the ceiling that will fall on the player if they try to open the exit door before all the candles are lit. For this trap made a new mesh out of several other components, added custom colliders to it, a collision box, a blueprint, and a movement sequence.

![ExitDoorBlueprint](https://user-images.githubusercontent.com/87107050/142500181-8f7dcffd-8d81-4ae0-b780-630680e8fc6d.PNG)
![DropCageFunction](https://user-images.githubusercontent.com/87107050/142500197-98fe9c74-16ca-42c1-a0cb-88902580d0cb.PNG)
![CapturedByCultists](https://user-images.githubusercontent.com/87107050/142500605-d7e7cbb9-7ba5-48de-83bf-06c9ea0dd2a8.gif)

The collider in the cage opens a new menu map after a 3 second delay that forces the player to either restart or quit the level.

## Story 5: Finalize Props

