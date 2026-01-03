# ServerWorld Server World
>Includes world custom data, global variables, etc.<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-18

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_STARTUP_COMPLETE](#EVENT_STARTUP_COMPLETE)** : string;<br>[Static] event: The server world is started and every thread will dispatch this event, while the system will open to allow login ServerWorld.isOpenGate=true  |
| **isOpenGate** : boolean;<br>[Static] Whether to open the gate: Allow login Default Value=true  |
| **isStop** : boolean;<br>[Static] [Read Only] Does the World Stop-Hop id-CommandPage Default Value=[]  |
| **uiCustomCommandPages** : {<br>[Static] ui event set id-CommandPage 0~N Default Value={}  |
| **[whenNoScene](#whenNoScene)** : Callback;<br>[Static] Callback function when the player enters a scene that does not exist whenNoScene(player:ServerPlayer);  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[dataWrite](#dataWrite)**(func : Function,  args : any[]): void<br>[Static] World Custom Data Writing（i.e. written ServerWorld.data）
| **[close](#close)**(onFin? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void<br>【Static】Close the world
| **[restart](#restart)**(): void<br>[Static] Rebooting the World
| **[kickPlayer](#kickPlayer)**(uid : number): void<br>Static] Kick out player: Disconnect the player from the server
| **[addPlayerToBlackList](#addPlayerToBlackList)**(uid : number): void<br>[Static] Player added to blacklist, can't login
| **[removePlayerToBlackList](#removePlayerToBlackList)**(uid : number): void<br>[Static] Player removed from blacklist
| **[addServerFunction](#addServerFunction)**(classDomain : string,  functionName? : string): void<br>[Static] Add server methods that allow RPC calls from the client
| **[setWorldVariableAccessible](#setWorldVariableAccessible)**(type : number,  varID : number,  accessible : boolean): void<br>[Static] Set variables to get access to the client
| **[getWorldVariableAccessible](#getWorldVariableAccessible)**(type : number,  varID : number): boolean<br>[Static] Get variables to get access to the client
| **[setWorldVariable](#setWorldVariable)**(varID : number,  value : number,  isNotice? : boolean): void<br>[Static] Write world value variables
| **[getWorldVariable](#getWorldVariable)**(varID : number): number<br>[Static] Reading World Variables
| **[setWorldSwitch](#setWorldSwitch)**(varID : number,  value : number,  isNotice? : boolean): void<br>[Static] Write to World Switch
| **[getWorldSwitch](#getWorldSwitch)**(varID : number): number<br>[Static] Read the world switch
| **[setWorldString](#setWorldString)**(varID : number,  value : string,  isNotice? : boolean): void<br>[Static] Writing world string variables
| **[getWorldString](#getWorldString)**(varID : number): string<br>[Static] Reading World String Variables
| **[addListenerVariable](#addListenerVariable)**(type : number,  verID : number,  onChange : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void<br>[Static] Listening when the world variable changes
| **[removeListenerVariable](#removeListenerVariable)**(type : number,  verID : number,  onChange : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void<br>[Static] Cancel Listening: When the world variable changes

## Details

### EVENT_STARTUP_COMPLETE
###### EVENT_STARTUP_COMPLETE : string;
[Static] Event: ServerWorld is started. Every thread will dispatch this event, and the system will turn on allow login ServerWorld.isOpenGate=true<br>
If the executed logic needs to wait for asynchronous return results, you can set ServerWorld.isOpenGate=false to close the gate first, by listening to this event when executing the logic<br>
Wait for the logic to be fully executed before opening the door to allow players to log in. (For example, the project needs to add some additional logic to handle when the game server starts)<br>
>&nbsp;EventUtils.addEventListener(ServerWorld,ServerWorld.EVENT_STARTUP_COMPLETE,Callback.New(()=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;},this));<br>
>


### data
###### data : typeof WorldData;
[Static] World Data<br>
can be read directly, and write words need to be written through ServerWorld.dataWrite otherwise written to the unsynchronized thread is only used as temporary data for the thread (restart the server is reset)
### whenNoScene
###### whenNoScene : Callback;
[Static] Callback function whenNoScene(player:ServerPlayer) when the scene the player entered does not exist;<br>
Get the scene number of the player based on its player.sceneID


## dataWrite
###### **[dataWrite](#dataWrite)**(func : Function,  args : any[]): void :
[Static] World custom data writing (i.e. writing ServerWorld.data)<br>
Since the GC built-in custom world data has a copy for each thread, it needs to be synchronized with each thread, while if you change ServerWorld.data directly it can only be written temporarily and will not be archived.<br>
【Caution】<br>
-- The code inside the method runs independently in other threads, so it cannot rely on external variables, and the data that needs to be used from outside should be passed through args<br>
-- The method should not contain a random element within it, it must be deterministic, otherwise the synchronization is wrong<br>
-- The parameters must be pure data that can be copied through JSON packaging<br>
<br>
Example:<br>
>var a = new DataStructure_数据结构2();<br>
>a.AAA = MathUtils.rand(1000000000) + 1000000000;<br>
>a.BBB = 22222222<br>
>a.CCC = 33333333<br>
>var aaa = Math.random();<br>
>ServerWorld.dataWrite(function (a: DataStructure_数据结构2,aaa) {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;ServerWorld.data.arr2.push(a);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;ServerWorld.data.arr2[ServerWorld.data.arr2.length - 1].AAA = aaa;<br>
>}, [a,aaa]);<br>
>


##### Parameters
	func Executed by: This method will be executed in all threads
	args Parameters of the method



## close
###### **[close](#close)**(onFin? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void :
【Static】Close the world<br>
-- Player data storage<br>
-- Scene data storage<br>
-- World Data Storage<br>
-- Shut down the server
##### Parameters
	onFin Callback after completion of closure



## restart
###### **[restart](#restart)**(): void :
[Static] Rebooting the World<br>
-- Close the world<br>
-- Calling external scripts for restarting



## kickPlayer
###### **[kickPlayer](#kickPlayer)**(uid : number): void :
[Static] Kick out the player: Disconnect the player from the server
##### Parameters
	uid Player Unique ID



## addPlayerToBlackList
###### **[addPlayerToBlackList](#addPlayerToBlackList)**(uid : number): void :
[Static] Player added to blacklist, can't login
##### Parameters
	uid Player Unique ID



## removePlayerToBlackList
###### **[removePlayerToBlackList](#removePlayerToBlackList)**(uid : number): void :
[Static] Player removed from blacklist
##### Parameters
	uid Player Unique ID



## addServerFunction
###### **[addServerFunction](#addServerFunction)**(classDomain : string,  functionName? : string): void :
[Static] Add server methods that allow RPC calls from the client<br>
The client can call the server directly through ClientMsgSender.rpc and get the return value, but the server needs to use this function to set the allowed access rights in advance
##### Parameters
	classDomain Allowed domains (classes)
	functionName [Optional] Default = null Allowed methods, null means that all methods under the domain are available



## setWorldVariableAccessible
###### **[setWorldVariableAccessible](#setWorldVariableAccessible)**(type : number,  varID : number,  accessible : boolean): void :
[Static] Set variables to get access to the client
##### Parameters
	type 0-Global variable 1-Global switch 2-Global string
	varID Global numeric variable ID
	accessible Availability to the client



## getWorldVariableAccessible
###### **[getWorldVariableAccessible](#getWorldVariableAccessible)**(type : number,  varID : number): boolean :
[Static] Get variables to get access to the client
##### Parameters
	type 0-Global variable 1-Global switch 2-Global string
	varID Global numeric variable ID

##### Return
[boolean] Availability to the client

## setWorldVariable
###### **[setWorldVariable](#setWorldVariable)**(varID : number,  value : number,  isNotice? : boolean): void :
[Static] Write world value variables
##### Parameters
	varID Global numeric variable ID
	value Value
	isNotice [Optional] Default=true Whether to notify all threads for full thread synchronization



## getWorldVariable
###### **[getWorldVariable](#getWorldVariable)**(varID : number): number :
[Static] Reading World Variables
##### Parameters
	varID Global numeric variable ID



## setWorldSwitch
###### **[setWorldSwitch](#setWorldSwitch)**(varID : number,  value : number,  isNotice? : boolean): void :
[Static] Write to World Switch
##### Parameters
	varID Global switch variable ID
	value Value
	isNotice [Optional] Default=true Whether to notify all threads for full thread synchronization



## getWorldSwitch
###### **[getWorldSwitch](#getWorldSwitch)**(varID : number): number :
[Static] Read the world switch
##### Parameters
	varID Global switch variable ID



## setWorldString
###### **[setWorldString](#setWorldString)**(varID : number,  value : string,  isNotice? : boolean): void :
[Static] Writing world string variables
##### Parameters
	varID Global string variable ID
	value Value
	isNotice [Optional] Default=true Whether to notify all threads for full thread synchronization



## getWorldString
###### **[getWorldString](#getWorldString)**(varID : number): string :
[Static] Reading World String Variables
##### Parameters
	varID Global string variable ID



## addListenerVariable
###### **[addListenerVariable](#addListenerVariable)**(type : number,  verID : number,  onChange : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void :
[Static] Listening when the world variable changes
##### Parameters
	type 0-Numeric variables 1-Switch variables 2-String variables
	verID Variable ID
	onChange onChange(type:number,varID:number,value:number|string);



## removeListenerVariable
###### **[removeListenerVariable](#removeListenerVariable)**(type : number,  verID : number,  onChange : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void :
[Static] Cancel Listening: When the world variable changes
##### Parameters
	type 0-Numeric variables 1-Switch variables 2-String variables
	verID Variable ID
	onChange onChange(type:number,varID:number,value:number|string);





