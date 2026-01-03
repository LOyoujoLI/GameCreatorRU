# Command Event Instructions
>This class is the event command data class in the event page ([CommandPage](?file=006-API-2D单机内核/001-通用/013-CommandPage))<br>Support for custom event commands<br>Related categories:[Command](?file=006-API-2D单机内核/001-通用/012-Command)、[CommandPage](?file=006-API-2D单机内核/001-通用/013-CommandPage)、[CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-09

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_SYSTEM_COMMAND_START](#EVENT_SYSTEM_COMMAND_START)** : string;<br>[Static] events: system command events start, you can listen to the player by listening to the scene object  |
| **type** : number;<br>Instruction type System instruction 10000 or less, custom instruction 10000 or more, such as 10001 means No. 1 custom instruction  |
| **customID** : number;<br>ID of the custom instruction (if the instruction is a custom instruction, otherwise return null)  |
| **params** : any[];<br>Command parameters, which store the values of the parameters entered in the event editor  |
| **paramsCompiled** : any[];<br>Pre-compiled instruction parameters: generally used for custom storage after pre-compilation so that they can be called during the execution of instructions to improve event execution performance (e.g. caching some pre-computed values)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[callExecuteFunction](#callExecuteFunction)**(triggerLineID : number,  player : Player,  params : any[],  gameFunc? : string): void<br>Call to execute client-side methods: this method is needed when you need to execute client-side effects or have players input information

## Details

### EVENT_SYSTEM_COMMAND_START
###### EVENT_SYSTEM_COMMAND_START : string;
[Static] events: system command events start, you can listen to the player by listening to the scene object<br>
>// so = [SceneObjectEntity] Example of player's scene object<br>
>// sysType = Callback parameters: Command category 0 - When dialog box is displayed 1 - When dialog selection box is displayed 2 - When scene is changed<br>
>EventUtils.addEventListenerFunction(so, Command.EVENT_SYSTEM_COMMAND_START, (sysType:number)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>




## callExecuteFunction
###### **[callExecuteFunction](#callExecuteFunction)**(triggerLineID : number,  player : Player,  params : any[],  gameFunc? : string): void :
Call to execute client-side methods: This method is needed when you need to execute client-side effects or have players input information<br> 
It is generally used mainly to call client-side methods, with the client set to wait for player input in order to block client-side input,<br> 
and when multiple events have players input at the same time, they should be queued in a way that allows players to submit their input results one by one. <br>
<br>
The custom command functions executed by the client must be in the CommandExecuteGame module:<br>
>module CommandExecuteGame {<br>
>&nbsp;&nbsp;&nbsp;export function customCommand_1(param1:any,param2:any): void {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return GameCommand.COMMAND_STATE_NEED_INPUT;<br>
>&nbsp;&nbsp;&nbsp;}<br>
>}<br>
>

<br>
// About return value status: Usually<br>
GameCommand.COMMAND_STATE_CONTINUE; Indicates that the command continues [default]<br>
GameCommand.COMMAND_STATE_STOP; Indicates command termination<br>
GameCommand.COMMAND_STATE_NEED_INPUT; Indicates that the command needs to wait for player input before continuing<br>

##### Parameters
	triggerLineID Trigger line ID, use the ID of the trigger (for the concept of trigger line you can refer to CommandTrigger)
	player Player Target
	params Parameters The execution method arranges these parameters in order, for example, [param1,param2] corresponds to customCommand_1(param1:any,param2:any)
	gameFunc [Optional] Default=null If it exists, the method inside the GameFunction will be executed, otherwise the corresponding CommandExecuteGame function needs to be created.





