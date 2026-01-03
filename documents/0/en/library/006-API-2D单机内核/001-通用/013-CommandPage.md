# CommandPage Event Page
>Contains all command lines under this event page ([Command](?file=006-API-2D单机内核/001-通用/012-Command))<br>Related categories:[Command](?file=006-API-2D单机内核/001-通用/012-Command)、[CommandPage](?file=006-API-2D单机内核/001-通用/013-CommandPage)、[CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-09

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **id** : number;<br>Unique ID  |
| **commands** : Command[];<br>Collection of command objects Default = []  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[startTriggerEvent](#startTriggerEvent)**(trigger : CommandTrigger,  playerInput? : any[]): void<br>Start trigger event (first time) is automatically ignored if already in execution
| **[executeEvent](#executeEvent)**(trigger : CommandTrigger,  playerInput? : any[]): void<br>[Static] Execution of events, generally used to resume event execution after a pause in the middle of the production of custom instructions
| **[startTriggerFragmentEvent](#startTriggerFragmentEvent)**(feData : string,  trigger : SceneObjectEntity,  execute : SceneObjectEntity,  onCommandExecuteOver? : Callback): CommandTrigger<br>[Static] Start executing fragment events

## Details



## startTriggerEvent
###### **[startTriggerEvent](#startTriggerEvent)**(trigger : CommandTrigger,  playerInput? : any[]): void :
Start trigger event (first time) is automatically ignored if already in execution
##### Parameters
	trigger Event Triggers
	playerInput [Optional] Default = [] Custom input information submitted by the player



## executeEvent
###### **[executeEvent](#executeEvent)**(trigger : CommandTrigger,  playerInput? : any[]): void :
[Static] Execution of events, generally used to resume event execution after a pause in the middle of the production of custom instructions
##### Parameters
	trigger Event Triggers
	playerInput [Optional] Default = [] Custom input information submitted by the player



## startTriggerFragmentEvent
###### **[startTriggerFragmentEvent](#startTriggerFragmentEvent)**(feData : string,  trigger : SceneObjectEntity,  execute : SceneObjectEntity,  onCommandExecuteOver? : Callback): CommandTrigger :
[Static] Start executing fragment events<br>
The fragment event event starts a separate trigger line that operates independently and supports cross-scene (must be triggered by the player's scene object) until its execution is complete.
##### Parameters
	feData Fragmented event data
	trigger Trigger-Scene Object
	execute Executor-Scene Object
	onCommandExecuteOver [Optional] Default=null Callback when command execution is complete

##### Return
[CommandTrigger] Triggers



