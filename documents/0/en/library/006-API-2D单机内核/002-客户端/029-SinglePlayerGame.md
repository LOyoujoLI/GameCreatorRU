# SinglePlayerGame Single-player games category
>For single-player games additional functions such as initialization and archive retrieval<br>-- Global information will be read automatically at game launch: e.g., second-week variables, archive count information, custom global data, etc.<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-02-02

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_RECOVER_TRIGGER](#EVENT_RECOVER_TRIGGER)** : string;<br>[Static] Event: Event trigger line that resumes after reading the file  |
| **[EVENT_ON_BEFORE_RECOVERY_DATA](#EVENT_ON_BEFORE_RECOVERY_DATA)** : string;<br>[Static] Event: Dispatched before calling recoveryData  |
| **[EVENT_ON_AFTER_RECOVERY_DATA](#EVENT_ON_AFTER_RECOVERY_DATA)** : string;<br>[Static] event: dispatched after calling recoveryData  |
| **[saveConfig](#saveConfig)** : any;<br>[Static] Archive configuration The system stores some basic information according to this archive configuration  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[newGame](#newGame)**(): void<br>[Static] New game: The new game will enter a preset birth point scene, all player variables and attributes, etc. are initial values
| **[getSaveInfo](#getSaveInfo)**()<br>[Static] Get full archive information, return all archive list information
| **[getSaveInfoByID](#getSaveInfoByID)**(id : number)<br>[Static] Get the specified archive information in the archive list
| **[saveGlobalData](#saveGlobalData)**(onFin : Callback): void<br>[Static] Store custom global information, global data in any new games, archives are common data (for example, for storing the user's key settings or multi-weekend data)
| **[deleteGlobalData](#deleteGlobalData)**(onFin? : Callback): void<br>[Static] Delete the global custom data information, and also delete the second week variable information
| **[saveGame](#saveGame)**(index : number,  onFin : Callback,  indexInfo? : any): void<br>Static】Archive: Support for calling archive in event execution
| **[loadGame](#loadGame)**(index : number,  onFin : Callback): void<br>EVENT_IN_NEW_SCENE event is dispatched when this function is called in order to allow the project layer to enter the corresponding scene.
| **[delSaveFile](#delSaveFile)**(index : number,  onFin : Callback): void<br>[Static] Delete archive
| **[getSceneObjectSwitch](#getSceneObjectSwitch)**(sceneID : number,  soIndex : number): number[]<br>[Static] Get the object switch, generally used to install the object switch after changing the scene, the object switch does not reset with the switch scene, and will also be stored in the archive
| **[recoveryData](#recoveryData)**(): void<br>[Static] Recovery of archived data, generally in the form of reading the file into the scene after the recovery of data, including:
| **[regSaveCustomData](#regSaveCustomData)**(dataName : string,  dataFunction : Callback): void<br>[Static] Registration of custom data bound to archives
| **[regSaveCustomGlobalData](#regSaveCustomGlobalData)**(globalDataName : string,  globalDataFunction : Callback): void<br>[Static] Register custom data bound to the game (data that is not related to the archive and will be loaded automatically when the game starts GC-LifeData)
| **[getSaveCustomData](#getSaveCustomData)**(dataName : string): any<br>[Static] Get the custom data of the current archive, read the archive before you can get
| **[getSaveCustomGlobalData](#getSaveCustomGlobalData)**(globalDataName : string): any<br>[Static] Read custom global data

## Details

### EVENT_RECOVER_TRIGGER
###### EVENT_RECOVER_TRIGGER : string;
[Static] Event: Event trigger line that resumes after reading the file<br>
You can listen to SinglePlayerGame.recoveryData before it is called<br>
>EventUtils.addEventListenerFunction(SinglePlayerGame,SinglePlayerGame.EVENT_RECOVER_TRIGGER,(trigger:CommandTrigger)=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_ON_BEFORE_RECOVERY_DATA
###### EVENT_ON_BEFORE_RECOVERY_DATA : string;
[Static] Event: Dispatched before calling recoveryData<br>
>EventUtils.addEventListenerFunction(SinglePlayerGame,SinglePlayerGame.EVENT_ON_BEFORE_RECOVERY_DATA,()=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_ON_AFTER_RECOVERY_DATA
###### EVENT_ON_AFTER_RECOVERY_DATA : string;
[Static] event: dispatched after calling recoveryData<br>
>EventUtils.addEventListenerFunction(SinglePlayerGame,SinglePlayerGame.EVENT_ON_AFTER_RECOVERY_DATA,()=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### saveConfig
###### saveConfig : any;
[Static] Archive configuration The system stores some basic information according to this archive configuration<br>
event: boolean; // Events: Record the currently executing events when archiving, and restore them when reading the archive<br>
audioVolume: booean; // Global volume: BGM/BGS/SE/TS volume<br>
bgm: true; // The BGM currently being played<br>
bgs: true; // Currently playing BGS


## newGame
###### **[newGame](#newGame)**(): void :
[Static] New game: The new game will enter a preset birth point scene, all player variables and attributes, etc. are initial values<br>
The project layer can listen for events to enter the scene as a new game, refer to[ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene)The EVENT_IN_NEW_SCENE event<br>
A new game does not clear global data: e.g., second-week variables, custom global data, archive directory information, etc.<br> 
Before calling this function, the default scene: Game.currentScene=ClientScene.EMPTY



## getSaveInfo
###### **[getSaveInfo](#getSaveInfo)**() :
[Static] Get full archive information, return all archive list information

##### Return
Format:<br>-- id = unique number of the archive, e.g. [1,3,61] means that files 1, 3, 61 were archived<br>-- now = unix timestamp at the time of archiving<br>-- indexInfo = custom information (e.g. store map name so that players can quickly identify it in the archive list)

## getSaveInfoByID
###### **[getSaveInfoByID](#getSaveInfoByID)**(id : number) :
[Static] Get the specified archive information in the archive list
##### Parameters
	Specified archive information (simple information in the directory), null means no such archive

##### Return
Format:<br>-- indexInfo Custom information<br>-- id = unique number of the archive, e.g. [1,3,61] for archive 1, 3, 61<br>-- now = unix timestamp at the time of archiving

## saveGlobalData
###### **[saveGlobalData](#saveGlobalData)**(onFin : Callback): void :
[Static] Store custom global information, global data in any new games, archives are common data (for example, for storing the user's key settings or multi-weekend data)<br>
Calling this function will also store the information of the two-week variables at the same time<br> 
The storage will additionally store the custom archive data registered by SinglePlayerGame.regSaveCustomGlobalData
##### Parameters
	onFin When storage is complete onFin(success:boolean)



## deleteGlobalData
###### **[deleteGlobalData](#deleteGlobalData)**(onFin? : Callback): void :
[Static] Delete the global custom data information, and also delete the second week variable information
##### Parameters
	onFin [Optional] Default=null Callback after deletion



## saveGame
###### **[saveGame](#saveGame)**(index : number,  onFin : Callback,  indexInfo? : any): void :
Static】Archive: Support for calling archive in event execution<br>
SinglePlayerGame.regSaveCustomData will additionally store the custom archive data registered by SinglePlayerGame.regSaveCustomData<br> 
It will also store the global data (same call as SinglePlayerGame.saveGlobalData)<br> 
-- Device storage (storage in the form of files for PC, mobile devices, etc.) <br> 
-- Cookies cache (Web supports storage in the form of LocalStorage/IndexedDB)<br> 
-- Cloud archive (GC game platform automatically supports cloud archive service)
##### Parameters
	index Archive Location
	onFin Callback when archiving is complete onFin(success:boolean)
	indexInfo [optional] default=null information for the archive directory, information that can be JSONized (written to LIFE-DATA, used to see some custom information in the read archive list, can be obtained using SinglePlayerGame.getSaveInfo)



## loadGame
###### **[loadGame](#loadGame)**(index : number,  onFin : Callback): void :
EVENT_IN_NEW_SCENE event is dispatched when this function is called in order to allow the project layer to enter the corresponding scene.
##### Parameters
	index Read file location
	onFin Callback after reading the file onFin(success:boolean);



## delSaveFile
###### **[delSaveFile](#delSaveFile)**(index : number,  onFin : Callback): void :
[Static] Delete archive
##### Parameters
	onFin Callback whether the deletion was successful onFin(success:boolean)



## getSceneObjectSwitch
###### **[getSceneObjectSwitch](#getSceneObjectSwitch)**(sceneID : number,  soIndex : number): number[] :
[Static] Get the object switch, generally used to install the object switch after changing the scene, the object switch does not reset with the switch scene, and will also be stored in the archive
##### Parameters
	sceneID Scene ID
	soIndex Object ID

##### Return
[number]

## recoveryData
###### **[recoveryData](#recoveryData)**(): void :
[Static] Recovery of archived data, generally in the form of reading the file into the scene after the recovery of data, including:<br>
-- Properties and behaviors of all objects (behaviors that are halfway through will then continue to be executed)<br> 
-- All events that are being executed will be restored to continue midway through<br> 
-- All opened interfaces and layers<br> 
-- Restoration of BGM and BGS (background music, scene sound effects) that were previously being BGM and BGS (background music, scene sound effects)<br> 
-- Restore previous scene fog effects, tones, camera states (to be adjusted soon, as this feature will be put into project layer implementation, later it will be stored and read in the form of custom storage data)



## regSaveCustomData
###### **[regSaveCustomData](#regSaveCustomData)**(dataName : string,  dataFunction : Callback): void :
[Static] Registration of custom data bound to archives
##### Parameters
	dataName Data Name
	dataFunction Data function callback, through which to get the data to be stored



## regSaveCustomGlobalData
###### **[regSaveCustomGlobalData](#regSaveCustomGlobalData)**(globalDataName : string,  globalDataFunction : Callback): void :
[Static] Register custom data bound to the game (data that is not related to the archive and will be loaded automatically when the game starts GC-LifeData)
##### Parameters
	globalDataName Global data name
	globalDataFunction Data function callback, through which to get the data to be stored



## getSaveCustomData
###### **[getSaveCustomData](#getSaveCustomData)**(dataName : string): any :
[Static] Get the custom data of the current archive, read the archive before you can get
##### Parameters
	dataName Data Name



## getSaveCustomGlobalData
###### **[getSaveCustomGlobalData](#getSaveCustomGlobalData)**(globalDataName : string): any :
[Static] Read custom global data
##### Parameters
	Global data name





