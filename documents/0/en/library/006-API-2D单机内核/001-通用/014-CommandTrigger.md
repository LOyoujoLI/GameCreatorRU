# CommandTrigger Event Triggers
>Triggers are used to trigger events that are always bound to a scene object and are triggered by an object and executed by an object (i.e., triggers and executors)<br>The main types of triggers are divided into: triggers for scenes, triggers for scene objects, triggers for interface controls, event library triggers (standalone), and standalone event fragment triggers<br>Support multiple triggers executing events at the same time<br>Support custom triggers, such as scene entry events, interface control click events, etc.<br>Support for pausing the execution of events and pausing to wait for time to advance<br>Support for multi-line mode: you can still execute the event again without waiting for it to finish<br>Support for receiving custom parameter input from players (such as making features like waiting for players to enter their names, waiting for players to enter their passwords, QTE, etc.)<br>Cross-scene execution: Some triggers can be executed across scenes and will not be terminated by changing scenes, satisfying the following conditions:<br>&nbsp;&nbsp;-- Both the triggers and executors are player scene objects (e.g., click events for interface controls)<br>After reading the file, all the events being executed will be restored (e.g., if event A is executed to line 3 before reading the file, then event A will be executed from line 4 after reading the file)<br>Related categories:[Command](?file=006-API-2D单机内核/001-通用/012-Command)、[CommandPage](?file=006-API-2D单机内核/001-通用/013-CommandPage)、[CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-11

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_START](#EVENT_START)** : string;<br>[Static] Execution Start Event: An event (Event) dispatched when the trigger starts execution  |
| **[EVENT_OVER](#EVENT_OVER)** : string;<br>[Static] End of Execution Event: An event (Event) dispatched when the execution of the trigger ends  |
| **[EVENT_BEHAVIOR_OVER](#EVENT_BEHAVIOR_OVER)** : string;<br>[Static] Event when the execution of the object behavior event previously dispatched by this trigger is completed: (same as [Wait for behavior to end] in the instruction)  |
| **COMMAND_MAIN_TYPE_SCENE** : number;<br>[Static] Enumeration-Event master category: Scene related event category Default=0 |
| **COMMAND_MAIN_TYPE_SCENE_OBJECT** : number;<br>[Static] Enumeration-Event Main Category: The event category associated with the scene object Default=1  |
| **COMMAND_MAIN_TYPE_UI** : number;<br>[Static] Enumeration-Event Main Category: Interface-related event categories Default=2 |
| **COMMAND_MAIN_TYPE_CALL_COMMON_EVENT** : number;<br>[Static] Enumeration-Event Master Class: The event class of the independent event library event Default value = 3  |
| **COMMAND_MAIN_TYPE_FRAGMENT_EVENT** : number;<br>[Static] Enumeration-Event Main Category: The event category of the fragment event Default value = 4  |
| **id** : number;<br>唯一ID，The TriggerLineID corresponds to the ID of the trigger  |
| **[mainType](#mainType)** : number;<br>Trigger Master Type Corresponds to CommandTrigger::COMMAND_MAIN_TYPE_XXXXX  |
| **[indexType](#indexType)** : number;<br>Trigger subtypes Subtypes under the main type  |
| **[from](#from)** : any;<br>Record the source of the corresponding event  |
| **[multiline](#multiline)** : boolean;<br>Whether multiline mode: indicates that the trigger is a new trigger generated one at a time, running independently  |
| **scene** : ClientScene;<br>The scene where it is located, here generally refers to the current game scene  |
| **[trigger](#trigger)** : SceneObjectEntity;<br>The scene object that triggered the event (the event trigger)  |
| **[executor](#executor)** : SceneObjectEntity;<br>Target of the execution event (event executor)  |
| **[pause](#pause)** : boolean;<br>Suspend command to continue advancing: Suspend execution marker, indicating that the execution of the event is temporarily stopped  |
| **[delayPause](#delayPause)** : boolean;<br>Whether to pause the [wait] command to continue execution (will also pause while waiting, and will wait for the remaining time/frames after resuming)  |
| **[cmdReturn](#cmdReturn)** : boolean;<br>Interrupt execution marker, indicating that the event instruction scope is interrupted and returns to the previous level of scope to continue execution (if it is already the top level, the event instruction execution is complete)  |
| **[inputMessage](#inputMessage)** : any[];<br>Player submits input value Default = []  |
| **[triggerPlayer](#triggerPlayer)** : Player;<br>[Read Only] Get the player who triggered the event, single player version only the current unique player  |
| **[hasBehavior](#hasBehavior)** : boolean;<br>[Read-only] Whether the trigger still has unexecuted actions sent out  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[offset](#offset)**(value : number): void<br>Offset command line
| **[waitFrame](#waitFrame)**(frame : number): void<br>Wait for the specified number of frames before continuing the command
| **[waitTime](#waitTime)**(time : number): void<br>Wait for the specified time and continue execution
| **[addBehavior](#addBehavior)**(targetSo : SceneObjectEntity,  behaviorData : any[],  loop : boolean,  targetSceneObject : SceneObject,  cover : boolean,  startIndex? : number,  Immediate? : boolean,  forceStopLastBehavior? : boolean,  delayFrame? : number,  executor? : SceneObjectEntity): void<br>Adding object behavior groups
| **[addCommonEventCommandPageLayer](#addCommonEventCommandPageLayer)**(commonEventID : number): void<br>When the event library event is called, the specified event library event is appended to the current trigger and will continue to be executed after the execution of the event library event.
| **[addFragmentEventCommandPageLayer](#addFragmentEventCommandPageLayer)**(feData : string): void<br>Append a fragment event level to the current trigger and return to the original event after the fragment event has been executed

## Details

### EVENT_START
###### EVENT_START : string;
[Static] Execution Start Event: An event (Event) dispatched when the trigger starts execution<br>
>// trigger = [CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger) Triggers<br>
>EventUtils.addEventListener(trigger, CommandTrigger.EVENT_START, Callback.New(()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this));<br>
>


### EVENT_OVER
###### EVENT_OVER : string;
[Static] End of Execution Event: An event (Event) dispatched when the execution of the trigger ends<br>
>// trigger = [CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger) Triggers<br>
>EventUtils.addEventListener(trigger, CommandTrigger.EVENT_OVER, Callback.New(()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this));<br>
>


### EVENT_BEHAVIOR_OVER
###### EVENT_BEHAVIOR_OVER : string;
[Static] Event when the execution of the object behavior event previously dispatched by this trigger is completed: (same as [Wait for behavior to end] in the instruction)<br>
>// trigger = [CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger) Triggers<br>
>EventUtils.addEventListener(trigger, CommandTrigger.EVENT_BEHAVIOR_OVER, Callback.New(()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this));<br>
>


### mainType
###### mainType : number;
Trigger Master Type Corresponding toCommandTrigger::COMMAND_MAIN_TYPE_XXXXX<br>
E.g., this is a scene object-related event
### indexType
###### indexType : number;
Trigger subtypes Subtypes under the main type<br>
For example, this is the "click event" of a scene object
### from
###### from : any;
Record the source of the corresponding event<br>
0-Scenario: None<br>
1-Scene Object: Object index<br>
2-Interface: sid unique random ID<br>
3-Event library: ID of the event library event<br>
4-Event page fragment: sid unique random ID
### multiline
###### multiline : boolean;
Whether multiline mode: indicates that the trigger is a new trigger generated one at a time, running independently<br>
For example, the click event of a control in the interface is a recurring event that is executed every time it is clicked - increasing the value of variable 1 by 20 points per second for 10 seconds.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Then the player clicks N times, and each event takes 10 seconds to finish executing.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If multiline mode is enabled: no need to wait for the previous 10-second event, start a new 10-second event (which will be executed simultaneously)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If multiline mode is turned off: you need to wait for the last 10 seconds event to be executed before it can take effect, otherwise this click is ignored.
### trigger
###### trigger : SceneObjectEntity;
The scene object that triggers the event (event trigger)<br> 
As in RPG games, when the player clicks on an NPC, the player's scene object is the trigger
### executor
###### executor : SceneObjectEntity;
The target of the executed event (event executor)<br> 
As in an RPG, when the player clicks on an NPC, the NPC is the executor
### pause
###### pause : boolean;
Pause instruction to continue advancing: a pause execution marker, indicating that the execution of the event is temporarily stopped<br> 
Also the instruction stops the index advancement of the instruction and stays at the current line, which is still the current line of instruction execution if execution continues,<br> 
so in general you can call the offset method to offset the instruction line, or you can distinguish different states under the same instruction by the information submitted by the player for input
### delayPause
###### delayPause : boolean;
Whether to pause the [wait] command to continue execution (it will also pause while waiting, and will wait for the remaining time/frames after resuming)<br> 
Generally used for productions that need to actively pause certain events, such as the RPG template where certain events in the scene are paused when Game.pause is encountered,<br> 
in order to open the battle scene into "another space "The pause is resumed after the battle is over.
### cmdReturn
###### cmdReturn : boolean;
Interrupt execution flag, indicating that the scope of the event instruction is interrupted and returns to the previous level of scope to continue execution (if it is already the top level, the event instruction is executed) <br> 
If the system instruction - [interrupt instruction execution] is set to true, indicating that the event at the current level will not be executed subsequently
### inputMessage
###### inputMessage : any[];
Player submits input value Default = []<br> 
Generally used in conjunction with the system command - [Wait for player input] (of course custom waits are also valid)<br> 
The client submits the player's input via the inputMessageAndContinueExecute method of [GameCommand] <br> 
For example, the production waits for the player mouse click on the screen, then by submitting the mouse position information to the event receiver in order to get the information and execute the logic
### triggerPlayer
###### triggerPlayer : Player;
[Read Only] Get the player who triggered the event, single player version only the current unique player<br>
@return [Player]
### hasBehavior
###### hasBehavior : boolean;
Read-only] Whether or not the trigger is still dispatched with unexecuted behavior<br> 
A trigger can dispatch multiple object behavior events at the same time, for example, let A execute 123 and let B execute 456, <br> 
and the property returns false when all dispatched behaviors are executed (or when no object behavior events are currently dispatched).


## offset
###### **[offset](#offset)**(value : number): void :
Offset command line
##### Parameters
	value At offset



## waitFrame
###### **[waitFrame](#waitFrame)**(frame : number): void :
Wait for the specified number of frames before continuing the command
##### Parameters
	frame Number of frames waited for



## waitTime
###### **[waitTime](#waitTime)**(time : number): void :
Wait for the specified time and continue execution
##### Parameters
	time Waiting time, in milliseconds



## addBehavior
###### **[addBehavior](#addBehavior)**(targetSo : SceneObjectEntity,  behaviorData : any[],  loop : boolean,  targetSceneObject : SceneObject,  cover : boolean,  startIndex? : number,  Immediate? : boolean,  forceStopLastBehavior? : boolean,  delayFrame? : number,  executor? : SceneObjectEntity): void :
Adding object behavior groups<br>
Each time a group of object behaviors is added to an object, a new layer of behavior is added, and only when this layer is completed does it return to the previous layer for further execution<br>
For example, the default behavior of A object is 123, after the execution of 1 added a new behavior group 456, at this time after the execution of 456 back to the first level to continue the implementation of 23, so the total order should be: 1-4-5-6-2-3
##### Parameters
	targetSo Target audience (behavior performer)
	behaviorData Behavior data [[Behavior1-ID,Parameter1,Parameter2],[Behavior2-ID,Parameter1,Parameter2],....] , Since the behavior is customized, please refer to the game's template for the role of the specific behavior advanced producers can edit the behavior in: GameCreator Editor Menu - Custom Editor - Custom Behavior with the script,
	loop Whether to loop or not, once the loop is executed it will loop indefinitely at that level unless a new layer of behavior is added
	targetSceneObject Event Triggers
	cover Whether to override or not, and once overridden to empty the previous behavior group (along with its default behavior)
	startIndex [Optional] Default=0 The index of the act group's start play, default 0, means play from the very beginning
	Immediate [Optional] Default=true whether to refresh immediately, otherwise it will wait for the next frame before refreshing
	forceStopLastBehavior [Optional] Default=false Whether to force a behavior being executed to stop, implemented by the project layer so that the current behavior group can be executed immediately
	delayFrame [Optional] Default = 0 Number of frames to wait for within the behavior
	executor [optional] default=null Execution eventer (also behavior dispatcher)



## addCommonEventCommandPageLayer
###### **[addCommonEventCommandPageLayer](#addCommonEventCommandPageLayer)**(commonEventID : number): void :
When the event library event is called, the event library event specified in the current trigger is appended and executed, and the execution of the event library event returns to the original event and continues<br> 
Generally used to append the event library event to the instruction execution
##### Parameters
	commonEventID Event ID of the event library



## addFragmentEventCommandPageLayer
###### **[addFragmentEventCommandPageLayer](#addFragmentEventCommandPageLayer)**(feData : string): void :
Append fragment event hierarchy, append fragment event to the current trigger, after the fragment event is executed, it will go back to the original event to continue execution<br> 
Generally used to append event fragment in the instruction execution
##### Parameters
	feData Fragmented event data






