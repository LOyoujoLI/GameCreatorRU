# ServerScene Server Scenes
>&nbsp;&nbsp;The player will enter the corresponding scene after logging in, the scene is managed by the scene thread, each scene thread manages multiple preset scenes respectively (the scene that needs to be managed before it is actually created in that thread)<br>&nbsp;&nbsp;Creating a copy is done in the current scene thread<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-14

**Inheritance**  →[Scene](?file=007-API-2D网络内核/001-通用/023-Scene)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_PLAYER_IN_SCENE](#EVENT_PLAYER_IN_SCENE)** : string;<br>[Static] Event: Player enters the scene onPlayerInScene(player:ServerPlayer);  |
| **[EVENT_PLAYER_BEFORE_OUT_SCENE](#EVENT_PLAYER_BEFORE_OUT_SCENE)** : string;<br>[Static] Event: Player leaves the scene onPlayerBeforeOutScene(player:GameServerPlayer);  |
| **scenes** : ServerScene[];<br>[Static] Scenes [id] = [ServerScene](?file=007-API-2D网络内核/004-服务端/014-ServerScene) The corresponding thread holds the corresponding scene data, refer to ServerThread.getSceneThread default=[]  |
| **sceneCopys** : ServerScene[];<br>[Static] Scene copy Fill in id in order for copy id>_COPYENE_ID_START for copy ID Default=[]  |
| **playerMap** : {<br>List of players on this scene [uid] = [object GameServerPlayer] Default = {}  |
| **playerCount** : number;<br>Number of players in the current scene Default = 0  |
| **sceneObjectCount** : number;<br>Total number of objects in the scene Default value = 0  |
| **isDisposed** : boolean;<br>Released or not  |
| **isCopy** : boolean;<br>[Read Only] Is it a copy  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[createScene](#createScene)**(dataID : number,  copyMode? : boolean): number<br>[Static] Create a scene, if it is a copy then create a copy in the current thread
| **[getScene](#getScene)**(sceneID : number): [ServerScene](?file=007-API-2D网络内核/004-服务端/014-ServerScene)<br>[Static] Get the specified scenes in the current thread, scenes that do not belong to the current thread management cannot be obtained (unless they are copies created from the current scene)
| **[update](#update)**(now : number): void<br>Current scene refresh: the frame refresh, i.e. the function executed per frame. The server is set to refresh 60 times per second (may actually be less than 60 frames if lag is caused by logic calculations).
| **[dispose](#dispose)**(): void<br>Destruction: Currently only copies can be destroyed
| **[readyInScene](#readyInScene)**(player : GameServerPlayer): void<br>Prepare to enter the scene: let the player load the scene
| **[addPlayer](#addPlayer)**(player : GameServerPlayer): void<br>Add player: When the player enters the scene, the player will be added.
| **[removePlayer](#removePlayer)**(player : GameServerPlayer): void<br>Remove Player: When a player leaves the scene, the player is removed.
| **[getPlayer](#getPlayer)**(uid : number): GameServerPlayer<br>Get the player on the current scene: based on the player ID
| **[addSceneObject](#addSceneObject)**(so : ServerSceneObject,  addToList? : boolean): void<br>Adding game objects: There is no logic for synchronizing the client here, it should be implemented by the project layer
| **[removeSceneObject](#removeSceneObject)**(so : ServerSceneObject,  removeFromList? : boolean,  force? : boolean): boolean<br>Remove the game object: there is no logic to synchronize the client here, it should be implemented by the project layer

## Details

### EVENT_PLAYER_IN_SCENE
###### EVENT_PLAYER_IN_SCENE : string;
[Static] Event: Player enters the scene onPlayerInScene(player:ServerPlayer);<br>
>// Listen for events when the player enters the scene while in the scene thread<br>
>if(ServerThread.threadID!=ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerScene,ServerScene.EVENT_PLAYER_IN_SCENE,Callback.New((player:ServerPlayer)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>}<br>
>


### EVENT_PLAYER_BEFORE_OUT_SCENE
###### EVENT_PLAYER_BEFORE_OUT_SCENE : string;
[Static] Event: Player leaves the scene onPlayerBeforeOutScene(player:GameServerPlayer);<br>
>// Listen for events when the player leaves the scene while in the scene thread<br>
>if(ServerThread.threadID!=ServerThread.MAIN_THREAD_ID){<br>
>&nbsp;&nbsp;&nbsp;&nbsp;EventUtils.addEventListener(ServerScene,ServerScene.EVENT_PLAYER_BEFORE_OUT_SCENE,Callback.New((player:ServerPlayer)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;&nbsp;&nbsp;&nbsp;},this));<br>
>}<br>
>




## createScene
###### **[createScene](#createScene)**(dataID : number,  copyMode? : boolean): number :
[Static] Create a scene, if it is a copy then create a copy in the current thread<br>
The lifecycle of the replica can be implemented by the scenario subclasses of the project layer, for example the setting of destroying the replica when no player is on the scenario for more than 30 minutes, etc.
##### Parameters
	dataID Preset Reference ID
	copyMode [Optional] Default=false Whether copy mode

##### Return
[number] The returned scene ID, unique, and the same scene copy ID is not the same as the non-copy ID

## getScene
###### **[getScene](#getScene)**(sceneID : number): [ServerScene](?file=007-API-2D网络内核/004-服务端/014-ServerScene) :
[Static] Get the specified scenes in the current thread, scenes that do not belong to the current thread management cannot be obtained (unless they are copies created from the current scene)<br>
The current default rule for the GC server floor is to have fixed scenarios divided among different threads according to the sceneID % SCENE_FIXED_THREAD_COUNT rule
##### Parameters
	sceneID



## update
###### **[update](#update)**(now : number): void :
Current scene refresh: the frame refresh, i.e. the function executed per frame. The server is set to refresh 60 times per second (may actually be less than 60 frames if lag is caused by logic calculations).
##### Parameters
	now unix timestamp



## dispose
###### **[dispose](#dispose)**(): void :
Destruction: Currently only copies can be destroyed



## readyInScene
###### **[readyInScene](#readyInScene)**(player : GameServerPlayer): void :
Prepare to enter the scene: let the player load the scene
##### Parameters
	player Player



## addPlayer
###### **[addPlayer](#addPlayer)**(player : GameServerPlayer): void :
Add player: When the player enters the scene, the player will be added.
##### Parameters
	player Player



## removePlayer
###### **[removePlayer](#removePlayer)**(player : GameServerPlayer): void :
Remove Player: When a player leaves the scene, the player is removed.
##### Parameters
	player Player



## getPlayer
###### **[getPlayer](#getPlayer)**(uid : number): GameServerPlayer :
Get the player on the current scene: based on the player ID
##### Parameters
	uid Player's unique ID

##### Return
Returns null if it does not exist

## addSceneObject
###### **[addSceneObject](#addSceneObject)**(so : ServerSceneObject,  addToList? : boolean): void :
Adding game objects: There is no logic for synchronizing the client here, it should be implemented by the project layer<br>
Different projects or templates have different effects, all by the project layer to achieve specific functions. For example, MMORPG needs to use AOI algorithm
##### Parameters
	so Game objects to be added
	addToList [Optional] Default value = true Whether it is a preset NPC, if yes, it is not automatically calculated to insert into the empty position but according to the preset



## removeSceneObject
###### **[removeSceneObject](#removeSceneObject)**(so : ServerSceneObject,  removeFromList? : boolean,  force? : boolean): boolean :
Remove the game object: there is no logic to synchronize the client here, it should be implemented by the project layer<br>
Different projects or templates have different effects, all by the project layer to achieve specific functions. For example, MMORPG needs to use AOI algorithm
##### Parameters
	so Game objects to be removed
	removeFromList [Optional] Default=true Whether to remove from the list
	force [optional] default=false whether to force removal (if not forced will verify if ServerSceneObject is this in the list, otherwise just look at so.index)

##### Return
[boolean]



