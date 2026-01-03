# GameBase Game master management base class
>The actual game will create concrete classes to inherit from this class, with convenient properties pointing to the upper level custom classes<br>It is usually necessary to use the Game variable to create an instance of the class or its subclasses:var Game = new GameBase();<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-28

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_PAUSE_CHANGE](#EVENT_PAUSE_CHANGE)** : string;<br>Suspend state change event dispatch  |
| **layer** : GameLayer;<br>Total game level  |
| **currentScene** : ClientScene;<br>The current scene, by default, is the EMPTY of [ClientScene](?file=006-API-2D Standalone Kernel/002-Client/016-ClientScene), the project layer needs to set this value when implementing scene replacement  |
| **player** : ClientPlayer;<br>My Player Objects  |
| **oneFrame** : number;<br>[Read Only] Time of one unit frame in the game  |
| **[now](#now)** : number;<br>[Read Only] Game Timestamp: The time from when the game starts to now  |
| **[frameCount](#frameCount)** : number;<br>[Read Only] Game Frame Count: the total number of frames from the start of the game to the present  |
| **[pause](#pause)** : boolean;<br>Game time pause (affects whether the system is stationary and the upper logic can be based on this item to write the stationary effect)  |



## Details

### EVENT_PAUSE_CHANGE
###### EVENT_PAUSE_CHANGE : string;
Suspended state change event dispatch<br>
>EventUtils.addEventListenerFunction(Game, Game.EVENT_PAUSE_CHANGE, this.onPauseChange, this);<br>
>


### now
###### now : number;
[Read Only] Game Timestamp: The time from when the game starts to now<br>
-- Reading the archive will restore the archived game timestamp<br>
-- Pausing the game will cause that time to be suspended
### frameCount
###### frameCount : number;
[Read Only] Game Frame Count: The total number of frames from the start of the game to the present<br>
-- Pausing the game will cause the frame count to be paused
### pause
###### pause : boolean;
Game time pause (affects whether the system is stationary and the upper logic can be based on this item to write the stationary effect)<br>
System presets are forbidden for scenarios and contain the following:<br>
-- Scene layer rendering<br>
-- Scene object refresh (the update function of the scene object is no longer called during the pause)




