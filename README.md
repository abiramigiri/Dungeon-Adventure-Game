# Dungeon-Adventure-Game
A GUI and text based maze style game implemented in java

--README--

1.Overview

This program implements a maze style game with a dungeon full of caves, 
tunnels that have treasure. Players are able to move from start 
to end and collect the treasure in the locations they pass through. The caves have
Monsters called Otyugh's that feed on any organic matter. The caves also have thieves 
that steal a player's treasure. The player is equipped
With crooked arrows which can be used to shoot the monster. The dungeon also has arrows
That can be picked up. A player can detect these monsters by their smell and uses that and some
Hints to attack and kill these monsters and successfully navigate to the end. The player must
Be careful not to fall into one pit in the dungeon. The player can choose between a GUI
and text based interface to play in.

2.List of features

.Text based and a GUI based game adventure with appropriate clues to navigate it to the end and win or lose.
.GUI interface allows a player to shoot, move pickup with mouse and keyboard inputs.
.A player can restart game with the same dungeon or play a new game or quit in the GUI version.
.The player can choose to move, pickup or shoot at any step.
.The player can move to any of the available listed directions.
.The player can shoot in the same available directions in aa distance of 1-5 caves.
.The player can also pickup items if there are any to pickup.
.The players are described with their treasure they hold.
.A player's current location is displayed after every move. 
.The possible moves from a location are displayed.
.A chosen percent of the caves are filled with random treasure and arrows.
.A chosen number of caves contain Otyugh's depending on the game's difficulty.
.A random dungeon is generated with set features such as wrapping, 
not wrapping, with a degree of interconnectivity  as specified, with specific size of rows and columns. Aside from that they also have treasure percentage and difficulty.
.A dungeon is generated with suitable start and end such that they are at least 5 unit distance apart.
.A player can picks up items when they are at a location with treasure or arrows.
.A player can successfully detect an Otyugh's odor. The smell is strong if there are multiple 2 
Steps away or one or more 1 step away. The smell is faint if there is one 2 steps away.
.A player can attempt to shoot the monster in any direction. If they land a hit, they hear the monster's howl. If not their arrow is simply shot into the darkness.
.There is always a monster in the end cave. Once the player navigates these monster's safely 
Or kills them, the player can reach the end and win.
.If a player enters a cave with a monster the player gets eaten and the game ends.
.It takes 2 shots to kill a monster. However a player has 50% chance of escaping a monster that was hit once.
.A player can land a hit only if they specify the exact distance the monster is at from them. (Number of caves away)
.A pit that a player can fall into and die. Players are warned if a pit is one step away.
.Thieves who steal all the treasure of a player when they are in the same location as them.


3.How To Run

.Unzip the “Archive.zip” file.
.Navigate to the “res” folder among the contents of the unzipped file in the terminal on mac/windows.
Execute the command “java -jar dungeon.jar" followed by command line arguments to setup the dungeon.
.For text based game execute the command “java -jar dungeon.jar" *text* *int for row* *int for column* *int for interconnectivity* 
*boolean for wrapping(True = wrapping, False = not wrapping)* *int for treasure* *int for difficulty*
.Sample command with values “java -jar dungeon.jar text 6 6 10 true 100 4"
.Choosing low interconnectivity and high difficulty with low treasure makes the game hard.
.Choosing a high interconnectivity value and high treasure percent with low difficulty makes the game easier to beat.
.For GUI game execute the command "java -jar dungeon.jar graphics".


4.How to Use the Program

FOR TEXT BASED GAME :

.A player must choose between M S P to move, pickup or shoot at each turn.
.At each turn the player's location, items, possible moves are displayed.
.If M is chosen, the player must enter a valid direction. A valid direction is any direction that is displayed after "Doors lead to".
.If P is chosen, any available items in that location are picked up.
.If S is chosen, the player must enter a valid direction which is same as moving. The player must also enter a valid distance
which is a number between 1-5 denoting the number of caves to shoot.
.Smells indicate nearby monsters which can eat the player.
.Players area also alerted if there is a pit near by. Falling into a pit kills the player and ends the game.
.A thief steals all the player's treasure if the player walks into a cave with a thief.
.A howl is heard when an arrow hits the monster, if not the arrow simple goes into the darkness.
.Player wins by reaching the end without getting eaten by the monster.
.Press q to exit the game at any time except when not in the middle of entering input for move or shoot.
.If you wish to exit while shooting or moving, follow. Instructions on screen to complete that then press q.

FOR GUI BASED GAME :

.Click on dungeon settings then new game. 
.Setup dungeon by filling the dialog box and clicking ok.
.Sample values are 10 for every text box and click the iswrapping radio button.
.The player can also click on restart or quit.
.Clicking restart after playing a game, resets the same dungeon and puts the player back in start.
.The goal is to reach the end.
.Click on player items to view items held by player.
.A player can move by pressing W A S D. W to move up, A to move left, S to move down and D to move right.
.Pickup treasure by pressing P.
.A player can shoot by holding down shift key and pressing same buttons as move to shoot in those directions.
.After that the player must enter distance to shoot (1-5 caves).
.A light green hue or strong green hue in players cell indicates near by monster.
.A red alert triangle indicates a nearby pit.
.Once game its over the dungeon cannot be changed. Click restart or new game in dungeon settings to play again.


6.Design/Model Changes

.Making a GUI controller interface and implementing to handle the games I/O.
.Making additions to the model to allow pits, thieves and restarting the game.
.The new added classes for the GUI. The GUIController interface and implementation,
DungeonView interface and implementation, a DungeonViewActionlistener, a mouseAdapter,
Classes for different components of the view like MenuBar, PlayerDescription, DialogBox
And ModelStart to get text input from the dialog box to create a dungeon.

7.Assumptions

.Assuming that a constraint of minimum 6*6 can be set on the size of the grid to provide a 
consistent experience to the user. Allowing a smaller grid size requires a lot of 
conditional checking based on if the dungeon is wrapping, interconnected more than a degree of 0. 
Setting the grid size to be at or above 6*6 ensures that a start and end with distance of 5 can be found easily.
.Assuming that the location number of the cave or tunnel a player is in can be displayed at each step.
.Assuming that all items (treasure and arrows) can be picked up at once.
.Assuming that an Otyugh howls each time it is shot and its smell vanishes if it dies. 
.Assuming that a dungeon has only one pit.
.Assuming that the dungeon has same number of thieves as monsters.
.Assuming that monsters don't eat thieves. 

8.Limitations

A dungeon of size smaller than 6*6 cannot be made.
A dungeon has only one pit.
Extremely large dungeons over (50x50) make the program run slower due to the repainting of dungeon after every move.

9.Citations

Source for Union Find implementation : https://helloacm.com/the-union-find-disjoint-set-implementation-in-java/

Source for Dijktra implementation : https://www.techiedelight.com/single-source-shortest-paths-dijkstras-algorithm/

Source for image overlaying : https://stackoverflow.com/questions/13605248/java-converting-image-to-bufferedimage
