# Guessbook
## Jordi van Ditmar	student number: 10875875

Guessbook is in essence a digitization of the classic game ‘guess who?’, but will be played with mutual Facebook friends instead of made up people.  The app will basically be a representation of the classic game’s playing board and as such, no communication between devices or a server will be necessary. For the app Facebook’s API has to be used, next to that no external sources are required.

### Introduction
In the game ‘guess who?’ two players pick a card from a set of cards with fictional cartoon people on them (usually choice out of 24 cards). They then take turns, asking ‘yes or no’ questions to each other (e.g. “does your person wear glasses?”). With the answers to these questions a player can usually cross some characters of the list. Goal of the game is to be the first one to determine which card the opponent has selected.

In the app, the main idea of this game will be present. A few things will be significantly different, though. The most important change being that the set of people to choose from will not be fictional cartoony images, but a player’s actual Facebook friends. Because of this, more in-depth questions can be asked, since the players don’t only know what the people look like, but also their character, history, funny facts etc. 

### What will the app look like?
The first screen you’ll be prompted with will be a log on screen (see figure 1), as you’ll need to log onto your Facebook account to get to a list of your friends. A screen will pop up where you're asked to select the opponent you're playing against. Then, you’ll see a menu where from you can start the game, read the rules and some info, change the opponent, change the character pool and where there’s room for any future expansion. 
 
![](https://github.com/J0rrr/Guessbook/blob/master/doc/threefold%20examples.png)

Upon pressing the ‘start game’ button, a selection has to be made between playing on one or two devices (if this hasn’t been done already in the menu).  Playing on two devices will mean that the other player also has opened the app, logged on and selected the ‘two devices’ option. Both players will have to select the opponent they are playing against (so the pool of mutual friends can be loaded, of which 24 will be selected to play with). If the two players don’t have enough mutual friends, an option will appear to supplement the pool of mutual friends with celebrities and/or famous fictional characters. From this pool of characters the players have to select the character they want to be in-game (see figure 2). When they have selected one, a confirmation dialog-box will open, to make sure they have actually selected the character they want to be (see figure 3). Once the character is confirmed, the game begins. 

The game will be played in a conventional manner, where the two players take turns asking each other questions, and the first one to guess the right person wins (guessing a wrong person will let you lose automatically). For an example of what the gameplay will look like, see figure 4. Every turn, the player can select people to be crossed off the list and then press ‘next turn’ to actually remove them from the screen (this way the amount of turns can be counted, a sound will be played upon pressing the next turn button to prevent cheating). Note that, although connectivity between the devices will make the app more intuitive/interactive, it is not necessary for the core working of the game. As such, being able to connect the devices is something that will be looked into, but it’s not on the high-priority list.

![](https://github.com/J0rrr/Guessbook/blob/master/doc/gameplay%20example.png)

Figure 4, example of gameplay
 
Playing on one device will result in a nearly equal version of the game, with the only difference being that the device has to be exchanged every turn. To ensure that the players do not see each other’s ‘playing fields’, a screen will be added in-between pressing ‘next turn’ and actually showing the other player’s playing board. So if player 1 presses ‘next turn’, an almost blank screen will show with only one button. This button is pressed by player 2 to confirm that the device has changed hands and that player 1 is not able to see what player 2’s screen looks like. 

Another version of the game can be considered where two rounds of the game are played: one round where player 1 asks questions about player 2’s identity, and one round where it’s the other way round. In the end, the player who needed the smallest amount of questions to get to the answer, wins. In this game-mode, guessing the wrong person will result in a penalty of 3 turns. This version enables two players to play on the same device without having to switch the device every turn. If there is still time, this game-mode will be looked into.

### Necessities for the app
An obvious source of data for this app is Facebook. The mutual friends of the two players have to be loaded. Luckily, Facebook has a neat API and a large community using it, so no problems in retrieving this data arise yet. Aside from the Facebook friends, the app is completely standalone in the sense that nothing else is needed to play the game. The game relies completely on the real-life player to player interaction, and the app only needs to function as the games board. This will make the implementation of the app’s features fairly straightforward.

### Programming process
Finally, a description of the most logical programming process will be given here. The app can be decomposed into small parts, which can be implemented and tested one by one. These parts, in the most logical implementation order, are listed below, starting with the minimal requirements for the app:

* The logon screen activity 
* The code handling the retrieval of Facebook’s data
* The opponent selection activity
* The game’s main menu activity
* An activity where the ‘pool of characters’ can be viewed and possibly altered
* An activity where the player(s) can pick who they are in-game (their character)
* The gameplay activity for a game on one device
* An activity to show in-between turns for gameplay on one device
* The gameplay activity for a game on two devices
* An activity that is shown after a game is finished


When this is fully implemented and working correctly, the following parts could be implemented:

* An alternate version of the one-device-gameplay where the device isn't switched every turn
* A way of connecting two devices, so both players don't have to play on one device
* A leaderboard, showing statistics about finished matches

Below (figure 5) is a sketch of the activities necessary for the app, and their relations to each other.

![](https://github.com/J0rrr/Guessbook/blob/master/doc/design%20drawing.jpg)

Figure 5, sketch of activities
