# ClientPlayer Client Player Class
>Each player has only a unique instance of the player class, which may be an instance of that class or its subclasses (the standalone version has and has only one player, so there is only one instance)<br>Standalone kernel listens directly for changes in local variables<br>The network version of the kernel listens for variables by requesting the server to listen for them via RPC, and the server will synchronize them to the player's client each time it finds a change<br>&nbsp;&nbsp;-- No permission to listen to other players' variables<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-06-03

**Inheritance**  →[Player](?file=006-API-2D单机内核/001-通用/022-Player)<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(isMyPlayer? : boolean)<br>Constructors
| **[addListenerPlayerVariable](#addListenerPlayerVariable)**(type : number,  varID : number,  onChange : Callback,  isOnce? : boolean,  immediatelyCallback? : boolean): void<br>Listening to player variables
| **[removeListenerPlayerVariable](#removeListenerPlayerVariable)**(type : number,  varID : number,  onChange : Callback): void<br>Unlisten to player variables

## Details



## constructor
###### **[constructor](#constructor)**(isMyPlayer? : boolean) :
Constructors
##### Parameters
	isMyPlayer [optional] default=false whether it is my player (other players will exist in the network kernel)



## addListenerPlayerVariable
###### **[addListenerPlayerVariable](#addListenerPlayerVariable)**(type : number,  varID : number,  onChange : Callback,  isOnce? : boolean,  immediatelyCallback? : boolean): void :
Listening to player variables<br>
Standalone kernel: listen directly for changes in local variables<br>
Network version of the kernel: the first time this variable is listened to will be synchronized with the server-numbered variables, other non-first time listened to directly from the client cache<br>
>// Example: Listening to my player's number 10 numeric variable, since it is determined to be a numeric variable, the callback here uses value:number to determine that it is a numeric type<br>
>Game.player.addListenerPlayerVariable(0,10,Callback.New((typeID:number,varID:number,value:number)=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>},this))<br>
>


##### Parameters
	type 0-variable 1-switch 2-string
	varID Variable ID
	onChange Callback when variable changes onChange(typeID:number,varID:number,value:number|string)
	isOnce [optional] default=false whether to listen only once, but still need to call removeListenerPlayerVariable to remove 
	immediatelyCallback [optional] default=true whether the callback is immediate, otherwise the callback event will be received the next time the value of the variable changes 



## removeListenerPlayerVariable
###### **[removeListenerPlayerVariable](#removeListenerPlayerVariable)**(type : number,  varID : number,  onChange : Callback): void :
Unlisten to player variables<br>
Standalone kernel: directly unlisten to local variable changes<br>
Kernel for Network: Notify the server when all variables listening to the number are cancelled - cancels the synchronization of variables listening to the number and will not send synchronization messages to the client when the variable changes
##### Parameters
	type 0-variable 1-switch 2-string
	varID Variable ID
	onChange The callback when the variable is changed must be passed in to listen to this callback when the player variable is changed before it can be cancelled





