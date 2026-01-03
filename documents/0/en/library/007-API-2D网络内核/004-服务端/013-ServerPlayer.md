# ServerPlayer Server Players
>The player logs in to the main thread, reads the data and then goes to the corresponding scenario thread<br>Away from when a player opens a scene will clean up the player data under that scene thread<br>The main thread stores all player data, while the branch thread stores the player data under the current thread, for example, a server has four players ABCD, where A is in thread 4 and BCD is in thread 5.<br>Then there are a total of 4 players in the main thread, 1 in thread 4, and 3 in thread 5. There is also the possibility that players may be switching scenario threads or up and down threads that may be in the void, or only exist in the main thread.<br>The data in the main thread is not necessarily the latest data, but it is the latest data when the main thread archives the player<br>Entering a threaded scene creates a new player class and copies the previous data to the newly created player class<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-14

**Inheritance**  →[Player](?file=007-API-2D网络内核/001-通用/022-Player)<br>
**Subcategories**   N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_PLAYER_LOGIN](#EVENT_PLAYER_LOGIN)** : string;<br>[static] event: player online, after loading player data dispatch event, only the main thread can get callback(player:GameServerPlayer)  |
| **[EVENT_PLAYER_DISPLACEMENT](#EVENT_PLAYER_DISPLACEMENT)** : string;<br>[static] event: player squeeze number, squeeze number will not trigger the online event, only the main thread can get callback(player:GameServerPlayer)  |
| **[EVENT_PLAYER_LOGOUT](#EVENT_PLAYER_LOGOUT)** : string;<br>[static] event: player offline, dispatch event before cleaning up the player, only the main thread can get callback(player:GameServerPlayer)  |
| **[EVENT_PLAYER_MESSAGE](#EVENT_PLAYER_MESSAGE)** : string;<br>[Static] Event: Receive player string message  |
| **[playerList](#playerList)** : {<br>[static] Player list key -> [player] default={}  |
| **[playerCount](#playerCount)** : number;<br>[Static] Total number of players Default value=0  |
| **sceneID** : number;<br>ID of the player's scene  |
| **scene** : ServerScene;<br>The scene where the player is located, if it is empty then the player is no longer on the scene  |
| **threadID** : number;<br>The player's thread player.sceneID % ServerConfig.SCENE_FIXED_THREAD_COUNT + 3;  |
| **sceneObject** : ServerSceneObject;<br>[Read-only] Corresponding scene objects  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(key : string,  uid : number)<br>Constructors
| **[execCommonCommand](#execCommonCommand)**(commandID : number,  inputMessage : any[]): [CommandTrigger](?file=007-API-2D网络内核/001-通用/014-CommandTrigger)<br>Execute independent event library events, creating a separate event line to execute, without affecting other event execution
| **[operationPlayerData](#operationPlayerData)**(uid : number,  func : Function,  args? : any[],  onFin? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback),  useVariables? : boolean): void<br>[Static] Generic manipulation of player data (players not in the current thread or offline players can also be manipulated)
| **[getPlayer](#getPlayer)**(key : string): GameServerPlayer<br>[Static] Get players:The main thread is all online players, the branch thread only exists for all players on that branch thread
| **[getPlayerByUID](#getPlayerByUID)**(uid : number): GameServerPlayer<br>[Static] Get players:The main thread is all online players, the branch thread only exists for all players on that branch thread

## Details

### EVENT_PLAYER_LOGIN
###### EVENT_PLAYER_LOGIN : string;
[static] event: player online, after loading player data dispatch event, only the main thread can get callback(player:GameServerPlayer)<br>
&nbsp;Login will read the database and dispatch this event after reading the database (at this time the player is still in the main thread not transferred to the corresponding logical scenario thread)<br>
&nbsp;>&nbsp;// In the case of the main thread<br>
>&nbsp;if(ServerThread.threadID==ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Listening to player logins<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerPlayer,ServerPlayer.EVENT_PLAYER_LOGIN,Callback.New((player:GameServerPlayer)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>&nbsp;}<br>
>


### EVENT_PLAYER_DISPLACEMENT
###### EVENT_PLAYER_DISPLACEMENT : string;
[static] event: player squeeze number, squeeze number will not trigger the online event, only the main thread can get callback(player:GameServerPlayer)<br>
&nbsp;The squeeze number will use the online player's data directly (that data is in the corresponding scenario thread)<br>
&nbsp;>&nbsp;// In the case of the main thread<br>
>&nbsp;if(ServerThread.threadID==ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Listening to player logins<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerPlayer,ServerPlayer.EVENT_PLAYER_DISPLACEMENT,Callback.New((player:GameServerPlayer)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>&nbsp;}<br>
>


### EVENT_PLAYER_LOGOUT
###### EVENT_PLAYER_LOGOUT : string;
[Static] event: player offline, before cleaning up the player dispatch event, only the main thread can get callback(player:GameServerPlayer)<br>
&nbsp;>&nbsp;// In the case of the main thread<br>
>&nbsp;if(ServerThread.threadID==ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Listening to player logins<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerPlayer,ServerPlayer.EVENT_PLAYER_LOGOUT,Callback.New((player:GameServerPlayer)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>&nbsp;}<br>
>


### EVENT_PLAYER_MESSAGE
###### EVENT_PLAYER_MESSAGE : string;
[Static] Event: Receive player string message<br>
The corresponding scenario thread can receive the message, and the client sends it to the scenario thread it is in by default, or to a specified thread (except the main thread).callback(player:GameServerPlayer,msg:string)<br>
&nbsp;>&nbsp;// In the case of scene threads<br>
>&nbsp;if(ServerThread.threadID!=ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Listening to player logins<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerPlayer,ServerPlayer.EVENT_PLAYER_LOGOUT,Callback.New((player:GameServerPlayer,msg:string)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;trace("Receive a message from the player",msg);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>&nbsp;}<br>
>


### playerList
###### playerList : {
[static] Player list key -> [player] default={}<br>
Main thread exists for all players<br>
Branch threads exist only for all players on that branch thread
### playerCount
###### playerCount : number;
[Static] Total number of players Default value=0<br>
-- The main thread indicates the total number of all players<br>
-- Branch threads indicate the total number of players on the thread


## constructor
###### **[constructor](#constructor)**(key : string,  uid : number) :
Constructors
##### Parameters
	key Player unique key
	uid Player Unique UID



## execCommonCommand
###### **[execCommonCommand](#execCommonCommand)**(commandID : number,  inputMessage : any[]): [CommandTrigger](?file=007-API-2D网络内核/001-通用/014-CommandTrigger) :
Execute independent event library events, creating a separate event line to execute, without affecting other event execution<br>
The server can call this method: Execute a separate event with a new trigger line where both the trigger and the executor are the player<br>
If you want to specify a trigger and an executor to execute a new event, refer to the code:<br>
>// triggerSo = Trigger scene object<br>
>// executeSo = Executor Scene Object<br>
>// fromClient = Whether the request comes from the client or not, there is a permission issue not every event is allowed to be called by the client<br>
>var commonEvCmd: CommandPage = ServerWorld.getClientCallWorldEvent(commandID, fromClient);<br>
>if (commonEvCmd) {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var trigger = new CommandTrigger(CommandTrigger.COMMAND_MAIN_TYPE_CALL_COMMON_EVENT, commandID, this.scene, triggerSo, true, executeSo);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;commonEvCmd.startTriggerEvent(trigger, inputMessage);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return trigger;<br>
>}<br>
>


##### Parameters
	commandID ID of the event library event
	inputMessage The input parameters are available in the event via trigger.inputMessage



## operationPlayerData
###### **[operationPlayerData](#operationPlayerData)**(uid : number,  func : Function,  args? : any[],  onFin? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback),  useVariables? : boolean): void :
[Static] Generic manipulation of player data (players not in the current thread or offline players can also be manipulated)<br>
Since it is not certain if the player is online or in another thread, this function can be used to operate<br>
If it is in other threads: the corresponding thread executes the relevant code<br>
If the player is offline: read and parse all the data of the player and store it after the operation<br>
Caution:<br>
&nbsp;1.This operation will have a large overhead and should be used with caution.<br>
&nbsp;2.This function cannot be used by Thread ServerThread.MAIN_THREAD_ID<br>
>// For example, if you operate on a player with ID=123, set the player's variable #2 to a random number and return the value of variable #3, the rd here must be passed as a parameter, because when executing the func function<br>
>// It may be executed in other threads where only the method is executed and the temporary variable rd does not exist, so it is safe and reliable by passing parameters<br>
>// It is also equivalent to passing data to other threads, the more data is passed the higher the overhead will be, try to use critical data transfer<br>
>trace("6666666666666666")<br>
>var rd = MathUtils.rand(10000);<br>
>trace("Temporary variable RD=", rd);<br>
>ServerPlayer.operationPlayerData(123, (player: ServerPlayer, rd: number) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// Operation Variables<br>
>&nbsp;&nbsp;&nbsp;&nbsp;trace("Operate player variables", rd);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;player.variable.setVariable(2, rd);<br>
>&nbsp;&nbsp;&nbsp;&nbsp;return player.variable.getVariable(3);<br>
>}, [rd], Callback.New((returnValue: number) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// The return value comes from the return value of the function above, so it's the 3 variable for that player, which means it can read data from other threads or offline players<br>
>&nbsp;&nbsp;&nbsp;&nbsp;trace("The player's variable #3 is", returnValue);<br>
>}, this), true);<br>
>


##### Parameters
	uid Player ID
	func Method of operation func(player:ServerPlayer,...args)
	args [Optional] Default=[] Parameters passed by the executefunc method: must be JSONizable
	onFin [Optional] Default=null Callback on completion
	useVariables [Optional] Default=true Whether to use variables, read and write variables if used to allow offline players to synchronize the database



## getPlayer
###### **[getPlayer](#getPlayer)**(key : string): GameServerPlayer :
[Static] Get players:The main thread is all online players, the branch thread only exists for all players on that branch thread
##### Parameters
	key

##### Return
[GameServerPlayer]

## getPlayerByUID
###### **[getPlayerByUID](#getPlayerByUID)**(uid : number): GameServerPlayer :
[Static] Get Players - Based on UID: All players exist on the main thread, only all players on the branch thread exist on the branch thread
##### Parameters
	key

##### Return
[GameServerPlayer]



