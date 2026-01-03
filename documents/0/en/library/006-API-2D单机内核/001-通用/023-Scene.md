# Scene Scenario-Base Classes
>Scene objects ([SceneObject]) and layers ([ClientSceneLayer], only the client has the concept of layers) are supported on the scene<br>The base class for all scenarios is the class, which has the basic characteristics of the class<br>Support binding classes: different scenes can be bound to different classes in order to achieve different features, for example, scene A is a flat RPG scene, scene B is a horizontal jumping scene with a physics system<br>Support custom trigger types: such as events to enter the scene, events to leave the scene, etc.<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-05-21

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **id** : number;<br>Unique number  |
| **width** : number;<br>Map width (in pixels)  |
| **height** : number;<br>Map height (in pixels)  |
| **name** : string;<br>Map Name  |
| **[preloadMapAsset](#preloadMapAsset)** : boolean;<br>Whether to load map resources when pre-loading the scene: the mapping resources involved in the layer, if not pre-loaded will be dynamically loaded when displayed  |
| **[preloadSceneObjectAsset](#preloadSceneObjectAsset)** : boolean;<br>Whether to load all scene object resources when pre-loading the scene: avatar, possible interfaces and animations mounted on the object  |
| **[preloadSceneCommandAsset](#preloadSceneCommandAsset)** : boolean;<br>Whether to load all trigger events of the scene when preloading the scene  |
| **[dataLayers](#dataLayers)** : number[][][];<br>Data layer data [index of custom layer][grid x-axis][grid y-axis]  |
| **LayerDatas** : SceneLayerData[];<br>Layer data, which holds the preset layer data in the editor, will generate layer display objects based on this item when creating a scene  |
| **[bgm](#bgm)** : string;<br>BGM-Background music Background music played when entering the scene (implemented by the project layer)  |
| **bgmVolume** : number;<br>BGM-Background music volume 0~1  |
| **bgmPitch** : number;<br>BGM-Background music tone 0~2 Default 1 means normal sound effect  |
| **[bgs](#bgs)** : string;<br>BGS-Ambient sound effects Ambient sound effects played when entering a scene (implemented by the project layer)  |
| **bgsVolume** : number;<br>BGS volume 0~1  |
| **bgsPitch** : number;<br>BGS-Tone 0~2 Default 1 means normal sound  |
| **[sceneObjects](#sceneObjects)** : SceneObject[];<br>List of scene object records [scene object.index] -> [scene object]  |
| **[customCommandPages](#customCommandPages)** : CommandPage[];<br>Scene Custom Trigger Category [Event Trigger Category Index] -> [Event Page Object]  |
| **gridWidth** : number;<br>Grid width According to the game scene according to the preset [grid pixel size] and the actual scene width to calculate the size, unit grid pixel size reference Config.SCENE_GRID_SIZE  |
| **gridHeight** : number;<br>Grid height According to the game scene according to the preset [grid pixel size] and the actual scene height to calculate the size, unit grid pixel size reference Config.SCENE_GRID_SIZE  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[parse](#parse)**(jsonObj : any,  gameData : [GameData](?file=006-API-2D单机内核/001-通用/017-GameData)): void<br>This function is called when the system initializes the scene and can be overridden by the project layer to implement the required game logic
| **[getDataGridState](#getDataGridState)**(index : number,  gridX : number,  gridY : number): number<br>Get data grid status
| **[setDataGridState](#setDataGridState)**(index : number,  gridX : number,  gridY : number,  state : number): void<br>Setting the data grid status
| **[getRealWidth](#getRealWidth)**(scene : [Scene](?file=006-API-2D单机内核/001-通用/023-Scene)): { width number; height number; }<br>[Static] Get the actual width and height calculated with the scene grid (normalized width and height by grid)

## Details

### preloadMapAsset
###### preloadMapAsset : boolean;
Whether to load map resources when preloading the scene: the mapping resources involved in the layer, if not preloaded will be dynamically loaded at display time<br> 
The map layer resources are automatically loaded according to this configuration when calling AssetManager.preLoadSceneAsset at the project level
### preloadSceneObjectAsset
###### preloadSceneObjectAsset : boolean;
Whether to load all scene object resources when preloading the scene: avatar, possible interfaces and animations mounted on the object<br> 
This configuration is used to automatically load the pre-defined scene object resources in the scene when calling AssetManager.preLoadSceneAsset at the project level
### preloadSceneCommandAsset
###### preloadSceneCommandAsset : boolean;
Whether to load all trigger events of the scene when preloading the scene<br>
The pre-defined scene object resources in the scene are automatically loaded according to this configuration when the AssetManager.preLoadSceneAsset is called at the project level<br>
<br>
When loading a scene the resources will be preloaded according to the following system events in the events page<br>
-- Dialog and option events: dialog styles and headshot resources with<br>
-- Set object behavior events: avatar resources<br>
-- Custom events: you need to add logic to the project layer, for example, you can override AssetManager.preLoadCommandPage to add content that needs to be preloaded.
### dataLayers
###### dataLayers : number[][][];
Data layer data [index of custom layer][grid x-axis][grid y-axis]<br>
Support custom addition or removal of data layers, related logic implementation in the project layer<br>
For example, you can create barrier layers, mask layers or poison gas ranges in RPGs
### bgm
###### bgm : string;
BGM-Background music Background music played when entering the scene (implemented by the project layer)<br>
Relative address, e.g. asset/audio/bgm/abc.mp3
### bgs
###### bgs : string;
BGS-Ambient sound effects Ambient sound effects played when entering a scene (implemented by the project layer)<br>
Relative address, e.g. asset/audio/bgs/abc.mp3
### sceneObjects
###### sceneObjects : SceneObject[];
List of scene object records [scene object.index] -> [scene object]<br>
All scene objects on the scene are stored in this list, and each object has a unique index<br>
The preset object number (ID) in the scene editor corresponds to the index here, while dynamically generated objects or cloned objects in the game will be inserted according to the empty space.<br>
Clones that are removed from the scene are usually left empty in this list
### customCommandPages
###### customCommandPages : CommandPage[];
Scene Custom Trigger Category [Event Trigger Category Index] -> [Event Page Object]<br>
For example, the enter scene event, which is present in most templates, is a common custom trigger category


## parse
###### **[parse](#parse)**(jsonObj : any,  gameData : [GameData](?file=006-API-2D单机内核/001-通用/017-GameData)): void :
This function is called when the system initializes the scene and can be overridden by the project layer to implement the required game logic
##### Parameters
	jsonObj Scene data files
	gameData Game Data



## getDataGridState
###### **[getDataGridState](#getDataGridState)**(index : number,  gridX : number,  gridY : number): number :
Get data grid status
##### Parameters
	index Data Layer Index
	gridX Grid coordinates x
	gridY Grid coordinates y

##### Return
[number] Status of the grid

## setDataGridState
###### **[setDataGridState](#setDataGridState)**(index : number,  gridX : number,  gridY : number,  state : number): void :
Set data grid state<br> 
The state of the grid can be changed dynamically during the game run, the changed state will not be archived, it is only a temporary state,<br> 
If you need to store the grid state you need to implement the project layer itself. (The archive supports storing some custom data.)<br> 
The project layer implements the role of the data layer itself.
##### Parameters
	index Data Layer Index
	gridX Grid coordinates x
	gridY Grid coordinates y
	state Set the state of this grid



## getRealWidth
###### **[getRealWidth](#getRealWidth)**(scene : [Scene](?file=006-API-2D单机内核/001-通用/023-Scene)): { width number; height number; } :
[Static] Get the actual width and height calculated with the scene grid (normalized width and height by grid)
##### Parameters
	scene Scene Object

##### Return
width=Width (pixel size) height=height (pixel size)


