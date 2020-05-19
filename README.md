# PacXon
## CS110 - Fall 2018
### Team Project: Matthew Damiata, Adiel Felsen, Jack Stanley

***

## Project Description
PacXon is a game where a player controls a Pacman character to fence portions of the screen. The challenge is that the Pacman has to avoid ghosts who are bouncing around the screen. If the Pacman hits into a ghost, he loses a life. The game is over when Pacman runs out of lives or fences in a certain percentage of the screen. There are many levels with a different number of ghosts and even ghosts with special abilities to make the game more challenging. Pacman can also collect powerups of his own to help him succeed. PacXon uses Pacman’s original characters – Pacman and ghosts – but it is entirely a unique game of its own.

***    

### Class and File Relationships
<img src="assets/MVC.png" width="100%"/>

### List of Classes
* **Controller** - The class that defines the logic between the other classes. It includes collisions with powerups and the abilities that come with them and the bouncing of the ghosts on the screen. It also includes the logic behind filling in the screen, Pacman's motion and the loss of lives when Pacman's trail is collided with. It includes all of the game screens (Intro, Instructions, Game Menu, Next Level and Game Over). It includes win and lose logic and displays everything to the screen.
* **Pacman** - A class that defines the Pacman which is the character that the player controls. The character moves in any direction and is able to "fence in" portions of the screen.
* **Pinky** - the pink ghost that Pacman needs to avoid. This ghost bounces off the walls of non-fenced in areas of the screen. If Pinky collides with Pacman or one of the fences he is currently drawing, Pacman loses a life.
* **Inky** - the light-blue ghost that Pacman needs to avoid. This ghost bounces off the walls of fenced in areas of the screen. If Inky collides with Pacman, Pacman loses a life.
* **Binky** - the red ghost that Pacman needs to avoid. This ghost bounces off the walls of the non-fenced in areas of the screen and breaks any block it hits into (excluding the borders). If Blinky collides with Pacman or one of the fences he is currently drawing, Pacman loses a life.
* **Clyde** - the orange ghost that Pacman needs to avoid. This ghost moves along the edge of a fenced in area. If Clyde collides with Pacman, Pacman loses a life.
* **Banana** - one of the powerups that Pacman can collide with. Once collided with, Pacman's speed will double for 50 frames.
* **Banana** - one of the powerups that Pacman can collide with. Once collided with, all ghost speed is halved for 50 frames.
* **Snowflake** - one of the powerups that Pacman can collide with. Once collided with, the speed of the ghosts is set to zero for 50 frames.
* **Heart** - one of the powerups that Pacman can collide with. Once collided with, Pacman gets an extra life.
* **Screen** - this class holds the matrix which includes the state of each box on the grid - filled (state = 1), unfilled (state = 0) or in the process of being drawn (state = .5). This class also has methods to fill in areas of the screen not containing a ghost, reset the matrix, track the Pacman (and remove it), get the percent of the screen filled and get the number of boxes last filled.
* **Box** - this class defines each "box" object of the grid background. This class references the matrix in the Screen class for changing the images of the objects.  
* **Bottombar** - this class holds all of the data that is displayed to the user (Lives, Level, Percent, Highscore and Score). A method called data() returns the two lines that are displayed to the user.

**Final GUI Interface**
 <p float="center">
 <img src="assets/gamescreenshots/Startscreen.png" width="49%"/>
 <img src="assets/gamescreenshots/Instructionsscreen.png" width="49%"/>
 </p>
 <p float="center">
 <img src="assets/gamescreenshots/Gamescreen.png" width="49%" />
 <img src="assets/gamescreenshots/Levelscreen.png" width="49%" />
 </p>

 <p float="center">
 <center>
 <img src="assets/gamescreenshots/Gameoverscreen.png" width="49%"/>
 </center>
 </p>

***        

## Tasks and Responsibilities

### Software Lead - Adiel Felsen

Worked with back end on the creation of some classes. Specifically worked on the fillMatrix functionality of the Screen class. Worked closely with front end specialist on the bouncing of ghosts and Pacman collisions. Added Pacman's animation and changed the scoring system. Also cleaned up much of the code to follow the DRY rule. Generally worked through many issues on the front end and the back end to get the code to work properly and commented much of the code to make it clear to understand.

### Front End Specialist - Matt Damiata

Used pygame to create most of the visual aspects of the game. Created the Start Screen, Instructions Screen, Next Level Screen and Game Over Screen and the display of the Bottombar class. Worked closely with software lead on the bouncing and abilities of the Ghosts and worked on Pacman collisions. Worked on generating ghost objects and implemented the "Heart" powerup. Also generally worked on fixing the code to make it work properly.

### Back End Specialist - Jack Stanley

Worked on creating many of the major classes to be used in the game and wrote docstrings to make each methods' functionality clear. Created Bottombar class which displays relevant information to the user. Worked with Software Lead and Front End on finishing the project and implementing object functionality in the Controller class.

***

## Testing

### Game Testing

When the game screen loads after pressing SPACEBAR, we see if all of the ghosts are bouncing around the screen properly. Next, we test movement within the "closed" area of the screen. When we press an arrow key once Pacman should move one box in the arrow's direction. When we hold an arrow key, Pacman should move in the arrow's direction until released. We then test movement in the "open" area. When an arrow key is pressed once, Pacman should move in the direction of the key until a collision with a closed area. If another key is pressed before colliding with the closed area, Pacman should change direction. After testing Pacman's movement, we test to see if all Powerups are working properly by colliding with them and seeing if their effects work as expected.

Next, we check to see if general gameplay is working. While playing, we make sure all ghosts and powerups are spawning and that the ghosts are bouncing correctly. We check to see if Pacman creates a trail behind him when he moves in the open area and that all enclosed areas without ghosts are filled in. We also check to see if Pacman loses a life and resets when a ghost collides with his trail. We press "q" to check if it properly exits the game during gameplay.

We then try to reach win state by filling in 80% of the screen. If we are successful, the NEXT LEVEL screen should display its text properly and pressing SPACEBAR should reset the game at the next level. Lives should increase as well. After this we try to reach fail state by allowing ghosts to collide with trail or letting Pacman collide with his own trail. Lives should decrease by 1 each time. Once lives = 0, the GAME OVER screen should display properly. Pressing SPACEBAR should restart the game.

At the end, we reopen the game and check that pressing "q" quits from the MAIN MENU page.
