# GameCommand Game client command processing
>Main functions:<br>-- Used to work with custom commands<br>-- Trigger events: scene events, scene object events, interface events, event library events (and fragment events trigger reference)[CommandPage](?file=007-API-2D网络内核/001-通用/013-CommandPage)）<br>-- Submit player input information<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-01-12

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **COMMAND_STATE_CONTINUE** : number;<br>[Static] Command Status: Continue  |
| **COMMAND_STATE_STOP** : number;<br>[Static] Command Status: Terminated  |
| **COMMAND_STATE_NEED_INPUT** : number;<br>[Static] Command Status: Player input required  |
| **isNeedPlayerInput** : boolean;<br>[Static] Whether player input is in progress  |
| **inputTriggerLine** : number;<br>[Static] The current trigger line ID to be entered  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[start](#start)**(triggerLineID? : number): void<br>[Static] Start
| **[startSceneCommand](#startSceneCommand)**(indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback): boolean<br>[Static] [Scene - Event] Active start triggering this event
| **[startSceneObjectCommand](#startSceneObjectCommand)**(sceneObjectIndex : number,  indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback,  triggerSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): boolean<br>[Static] [Scene Object-Event] Active start new trigger of this event
| **[startUICommand](#startUICommand)**(comp : UIBase,  indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback): boolean<br>[Static] [Interface - Events] Active start execution
| **[startCommonCommand](#startCommonCommand)**(id : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback,  triggerSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject),  executorSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): void<br>[Static] [Independent Event - Event Library Event] Active start execution
| **[inputMessageAndContinueExecute](#inputMessageAndContinueExecute)**(inputMessage? : any[],  force? : boolean,  delayFrame? : number,  triggerLineID? : number): void<br>[Static] Enter the information and continue the execution. The event page's waiting for player input will receive the input parameters.

## Details



## start
###### **[start](#start)**(triggerLineID? : number): void :
[Static] Start<br>
You can actively call start to restart after the general custom command returns COMMAND_STATE_STOP<br>
For example, for optimization in the network kernel, the wait in the event supports client-side wait, which is implemented by first COMMAND_STATE_STOP, then wait for N frames and then call this method to continue executing the event
##### Parameters
	triggerLineID [Optional] Default=null Trigger line: stop only the event execution of this trigger line when it exists, otherwise stop all



## startSceneCommand
###### **[startSceneCommand](#startSceneCommand)**(indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback): boolean :
[Static] [Scene - Event] Active start triggering this event
##### Parameters
	indexType Event category, 0~N corresponds to the event category in the customized scene
	inputMessage [optional] default=null Player input value (equivalent to the parameter passed when the event was called)
	onCommandExecuteOver [Optional] Default=null Callback when command execution is complete

##### Return
Whether the execution is triggered successfully

## startSceneObjectCommand
###### **[startSceneObjectCommand](#startSceneObjectCommand)**(sceneObjectIndex : number,  indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback,  triggerSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): boolean :
[Static] [Scene Object-Event] Active start new trigger of this event
##### Parameters
	sceneObjectIndex Scene object index (sceneObject.index)
	indexType Event category, 0~N corresponds to the event category in the custom scene object
	inputMessage [optional] default=null Player input value (equivalent to the parameter passed when the event was called)
	onCommandExecuteOver [Optional] Default=null Callback when command execution is complete
	triggerSceneObject [optional] default=null the object that triggered the event, null means the player's scene object as the trigger

##### Return
Whether the execution is triggered successfully

## startUICommand
###### **[startUICommand](#startUICommand)**(comp : UIBase,  indexType : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback): boolean :
[Static] [Interface - Events] Active start execution
##### Parameters
	comp component, such as a button in the interface
	indexType Sub-event category, 0~N The event category in the object corresponding to the UI
	inputMessage [optional] default=null Player input value (equivalent to the parameter passed when the event was called)
	onCommandExecuteOver [Optional] Default=null Callback when command execution is complete

##### Return
Whether the execution is triggered successfully

## startCommonCommand
###### **[startCommonCommand](#startCommonCommand)**(id : number,  inputMessage? : any[],  onCommandExecuteOver? : Callback,  triggerSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject),  executorSceneObject? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): void :
[Static] [Independent Event - Event Library Event] Active start execution<br>
Standalone events initiate a separate trigger line that operates independently and supports cross-scenario until its execution is complete.
##### Parameters
	id ID of the event library event
	inputMessage [optional] default=null Player input value (equivalent to the parameter passed when the event was called)
	onCommandExecuteOver [Optional] Default=null Callback when command execution is complete
	triggerSceneObject [optional] default=null Trigger eventer, if null then player's scene object
	executorSceneObject [Optional] Default=null Executor of the event, if null it means the player's scene object



## inputMessageAndContinueExecute
###### **[inputMessageAndContinueExecute](#inputMessageAndContinueExecute)**(inputMessage? : any[],  force? : boolean,  delayFrame? : number,  triggerLineID? : number): void :
[Static] Enter the information and continue the execution. The event page's waiting for player input will receive the input parameters.<br>
Can create such as input name, password, QTE system, etc.<br>
Event page production process:<br>
&nbsp;-- For example, by calling the script:inputMessageAndContinueExecute([123]);<br>
&nbsp;-- Event: Waiting for player input<br>
&nbsp;-- Events: can be received by assigning a value to a variable = player input or by displaying the player input in text, etc.
##### Parameters
	inputMessage [Optional] Default value = null Input information
	force [Optional] Default=false Whether to force the mode (non-forced mode only sends when the client determines that input is needed)
	delayFrame [Optional] Default=1 Delay how many frames to send
	triggerLineID [Optional] Default = -1 means submit the message to the specified trigger line, -1 means the default is GameCommand.inputTriggerLine, which is the current trigger line that the system is waiting for player input





