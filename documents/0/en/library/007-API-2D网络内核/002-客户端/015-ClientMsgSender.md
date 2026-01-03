# ClientMsgSender Client-side Message Sender
>Classes used to send messages with the GC server<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-27

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[send](#send)**(msg : string,  threadID? : number): void<br>[Static] Sending String Messages
| **[rpc](#rpc)**(className : string,  funcName : string,  params? : any[],  onReturn? : Callback,  threadID? : number): void<br>[Static] Remote call to the server method (requires the server to set the call permission [ServerWorld] of addServerFunction)
| **[requestListenPlayerVariable](#requestListenPlayerVariable)**(isListen : boolean,  type : number,  varID : number): void<br>[Static] Request to listen to player variables
| **[requestGetWorldVariable](#requestGetWorldVariable)**(type : number,  varID : number): void<br>[Static] Request for world variables

## Details



## send
###### **[send](#send)**(msg : string,  threadID? : number): void :
[Static] Sending String Messages
##### Parameters
	msg
	threadID [Optional] Default = -1 Specifies the thread to send from, unspecified indicates the thread of the current player's scenario 2 = main thread 3~N = scenario thread -1 = indicates the default player's thread



## rpc
###### **[rpc](#rpc)**(className : string,  funcName : string,  params? : any[],  onReturn? : Callback,  threadID? : number): void :
[Static] Remote call to the server method (requires the server to set the call permission [ServerWorld] of addServerFunction)<br>
-- The method can only be used after the player has entered the scene
##### Parameters
	className Called classes
	funcName Called methods
	params Method parameters
	onReturn Server return value callback, timeout will be deleted
	threadID Specify the thread to send to, if not specified then the current player's scenario thread 2=main thread 3~N=scenario thread -1= indicates the default player's thread



## requestListenPlayerVariable
###### **[requestListenPlayerVariable](#requestListenPlayerVariable)**(isListen : boolean,  type : number,  varID : number): void :
[Static] Request to listen to player variables
##### Parameters
	isListen Listening or not
	type Category 0-Variable 1-Switch 2-String
	varID Variable ID



## requestGetWorldVariable
###### **[requestGetWorldVariable](#requestGetWorldVariable)**(type : number,  varID : number): void :
[Static] Request for world variables
##### Parameters
	type 0-variable 1-switch 2-string
	varID Variable ID





