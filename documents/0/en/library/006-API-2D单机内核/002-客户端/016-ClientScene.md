# ClientScene Client game scenes
>A scene generally consists of a map image and an object ([ClientSceneObject]) on the scene<br>-- Layer support: block layers and picture layers, customizable, unlimited layers supported<br>-- Scene object support: add scene objects to the scene<br>-- Lens Control Camera<br>[New scene] ps: the use of the camera and the current scene can also be very convenient to create a small map<br>&nbsp;// Method 1: Create a scene #5 (not including the objects pre-positioned in the scene), an instance is allowed to set the id only once<br>&nbsp;var s = new ClientScene();<br>&nbsp;s.id = 5;<br>&nbsp;s.startRender();<br>&nbsp;stage.addChild(s.displayObject); // Game display layer reference GameLayer.d.ts<br>&nbsp;// Method Two:Create a scene by ClientScene.createScene, no need to specify the binding class of the scene, the system automatically creates the binding class of the scene according to the preset<br>&nbsp;ClientScene.createScene(sceneModelID, null, Callback.New(()=>{}, this), true);<br>[Other events]<br>&nbsp;EventObject.LOADED When all layer resources of the map are loaded, such as scene.on(EventObject.LOADED,this,()=>{});<br>[Level] Total level can be referred to [GameLayer]<br>The following is a reference to the default game display level of the engine:<br>-- Scene layer sceneLayer<br>&nbsp;&nbsp;&nbsp;&nbsp;- Custom base layers for editor presets (layers lower than object layers)<br>&nbsp;&nbsp;&nbsp;&nbsp;- Shadow layer shadowLayer<br>&nbsp;&nbsp;&nbsp;&nbsp;- Animation Layer - Bottom Layer animationLowLayer<br>&nbsp;&nbsp;&nbsp;&nbsp;- Object layer - bottom layer sceneObjectLowLayer Also turned on [child objects automatically change levels based on Y value]<br>&nbsp;&nbsp;&nbsp;&nbsp;- Object layer - middle layer sceneObjectLayer Also turned on [child objects automatically change levels based on Y value]<br>&nbsp;&nbsp;&nbsp;&nbsp;- Custom high level for editor presets (layers higher than the object layer)<br>&nbsp;&nbsp;&nbsp;&nbsp;- Object Level - High Level sceneObjectHighLayer Also turned on [child objects automatically change levels based on Y value]<br>&nbsp;&nbsp;&nbsp;&nbsp;- Animation Layer - High Level animationHighLayer<br>&nbsp;&nbsp;&nbsp;&nbsp;- Fog layer fogLayer<br>&nbsp;&nbsp;&nbsp;&nbsp;- Weather layer weaterLayer<br>-- Image Layer imageLayer<br>-- UI layer uiLayer<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-22

**Inheritance**  →[Scene](?file=006-API-2D单机内核/001-通用/023-Scene)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[BASE_DATA_LOADED](#BASE_DATA_LOADED)** : string;<br>[static] event: base data loaded (can be used to quickly cut into the scene, and then load dynamic related resources) callback parameters: onBaseDataLoaded(scene:ClientScene) default value = "ClientScene_BASE_DATA_LOADED"  |
| **[EVENT_IN_NEW_SCENE](#EVENT_IN_NEW_SCENE)** : string;<br>[Static] Event: Enter new scene onInNewScene(sceneID:number,state:number) state:0-switch scene 1-new game 2-read archive  |
| **EMPTY** : ClientScene;<br>[Static] Empty scenes, when the game starts then the empty scene state, can be used to determine  |
| **isDisposed** : boolean;<br>Uninstalled or not  |
| **sceneObjects** : ClientSceneObject[];<br>Scene object list: all scene objects on the scene [scene object.index] -> [scene object]  |
| **settingLayers** : ClientSceneLayer[];<br>Pre-defined set of layer display objects (from presets in the map editor)  |
| **displayObject** : GameSprite;<br>Display object of the scene (root container)  |
| **shadowLayer** : ClientSceneLayer;<br>Shadow layer  |
| **animationLowLayer** : ClientSceneLayer;<br>Animation layer: bottom layer  |
| **sceneObjectLowLayer** : ClientSceneLayer;<br>Object layer: Bottom layer  |
| **sceneObjectLayer** : ClientSceneLayer;<br>Object layer: Intermediate layer  |
| **sceneObjectHighLayer** : ClientSceneLayer;<br>Scene object: the highest level  |
| **animationHighLayer** : ClientSceneLayer;<br>Animation Level: High Level  |
| **fogLayer** : ClientSceneLayer;<br>Fog layer  |
| **weaterLayer** : ClientSceneLayer;<br>Weather layer  |
| **camera** : Camera;<br>Shots of the scene  |
| **localX** : number;<br>[Read-only] Get the scene position where the mouse X is located (unit: pixels)  |
| **localY** : number;<br>[Read-only] Get the scene position where the mouse Y is located (unit: pixels)  |
| **globalPos** : Point;<br>[Read Only] Get the absolute mouse position (relative to the stage) (unit: pixels)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[createScene](#createScene)**(sceneID : number,  onBaseDataLoaded? : Callback,  onLoaded? : Callback,  syncCallbackWhenAssetExist? : boolean): void<br>[Static] Create scenes, will create the corresponding instance scenes according to the preset implementation class
| **[dispose](#dispose)**(): void<br>Release the current scene
| **[addLayer](#addLayer)**(layer : ClientSceneLayer): void<br>Adding layers
| **[addLayerAt](#addLayerAt)**(layer : ClientSceneLayer,  index : number): void<br>Add a layer to the specified layer
| **[removeLayer](#removeLayer)**(layer : ClientSceneLayer): void<br>Remove Layer
| **[removeLayerAt](#removeLayerAt)**(index : number): void<br>Specify a layer to remove
| **[setLayerIndex](#setLayerIndex)**(layer : ClientSceneLayer,  index : number): void<br>Set the layer to the specified layer, which must already be on the scene
| **[getLayerLength](#getLayerLength)**(): number<br>Get the current total number of layers
| **[getLayer](#getLayer)**(index : number): ClientSceneLayer<br>Get the layers, indexed according to the actual hierarchy
| **[getLayerByPreset](#getLayerByPreset)**(id : number): ClientSceneLayer<br>Get layers, based on pre-defined levels
| **[getLayerByName](#getLayerByName)**(name : string): ClientSceneLayer<br>Get layer by name
| **[getPresetSceneObjectDatas](#getPresetSceneObjectDatas)**(): SceneObject[]<br>Get scene object data for scene presets (without birth points)
| **[addSceneObject](#addSceneObject)**(soData : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  isEntity? : boolean,  useModelClass? : boolean): ClientSceneObject<br>Scene objects are added to the scene
| **[removeSceneObject](#removeSceneObject)**(so : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  removeFromList? : boolean): ClientSceneObject<br>Removing scene objects from the scene
| **[addNewSceneObject](#addNewSceneObject)**(modelID : number,  presetSceneObjectData? : any): ClientSceneObject<br>Add a new object, generate a new object with default values, and also append modified properties（presetSceneObjectData）
| **[addSceneObjectFromClone](#addSceneObjectFromClone)**(fromSceneID : number,  fromSceneObjectindex : number,  isCopy? : boolean,  presetSceneObjectData? : any): ClientSceneObject<br>Cloning and adding scene objects
| **[getGlobalPos](#getGlobalPos)**(localX : number,  localY : number): [Point](?file=006-API-2D单机内核/001-通用/019-Point)<br>Get the absolute mouse position (relative to the stage) according to the specified scene position
| **[updateCamera](#updateCamera)**(): void<br>Refresh the footage immediately (by default the scene refreshes the footage frame by frame, e.g. when the bound scene object is moving)
| **[startRender](#startRender)**(): void<br>Rendering starts, the scene is at rest if not called, moving layers etc. are not played
| **[stopRender](#stopRender)**(LayerMoveToZero? : boolean): void<br>Stop Rendering
| **[hasListener](#hasListener)**(type : string): boolean<br>Check if the scenario has registered any listeners for a specific event type
| **[event](#event)**(type : string,  data? : any): boolean<br>Scene dispatch events
| **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene)<br>Use the scenario to register an event listener object of the specified type to enable the listener to receive event notifications
| **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene)<br>Use the scenario to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event
| **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene)<br>Remove the listener from the scene
| **[offAll](#offAll)**(type? : string): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene)<br>Removes all listeners of the specified event type from the scene
## Protected Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[onRender](#onRender)**(): void<br>Rendering: Refresh is not handled when Game.pause（update）
## Details

### BASE_DATA_LOADED
###### BASE_DATA_LOADED : string;
[static] event: base data loaded (can be used to quickly cut into the scene, and then load dynamic related resources) callback parameters: onBaseDataLoaded(scene:ClientScene) default value = "ClientScene_BASE_DATA_LOADED"<br>
Listening for the base resource to finish loading Example:<br>
>&nbsp;var s = new ClientScene();<br>
>&nbsp;s.id = 5;<br>
>&nbsp;s.on(ClientScene.BASE_DATA_LOADED)<br>
>&nbsp;s.startRender(ClientScene.BASE_DATA_LOADED,this,(s:ClientScene)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;});<br>
>&nbsp;stage.addChild(s.displayObject);<br>
>


### EVENT_IN_NEW_SCENE
###### EVENT_IN_NEW_SCENE : string;
[Static] Event: Enter new scene onInNewScene(sceneID:number,state:number) state:0-switch scene 1-new game 2-read archive<br>
Listens to events from switching scene events, new games, and reading archives so that the project layer can implement scene changes Default = "ClientSceneEVENT_IN_NEW_SCENE"<br>
>&nbsp;// sceneModelID = scene model ID, corresponding to the editor's scene ID (if it is a network version it may be a copy scene, but the model source is still the preset scene)<br>
>&nbsp;EventUtils.addEventListenerFunction(ClientScene, ClientScene.EVENT_IN_NEW_SCENE, (sceneModelID: number, state: number)=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;}, this)<br>
>




## createScene
###### **[createScene](#createScene)**(sceneID : number,  onBaseDataLoaded? : Callback,  onLoaded? : Callback,  syncCallbackWhenAssetExist? : boolean): void :
[Static] Create scenes, will create the corresponding instance scenes according to the preset implementation class
##### Parameters
	sceneID Scene ID
	onBaseDataLoaded [Optional] Default=null Callback when the base data is loaded onBaseDataLoaded(scene)
	onLoaded [Optional] Default=null onLoaded(scene)
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)

##### Return
[ClientScene]

## dispose
###### **[dispose](#dispose)**(): void :
Release the current scene



## addLayer
###### **[addLayer](#addLayer)**(layer : ClientSceneLayer): void :
Adding layers
##### Parameters
	layer Layer objects



## addLayerAt
###### **[addLayerAt](#addLayerAt)**(layer : ClientSceneLayer,  index : number): void :
Add a layer to the specified layer
##### Parameters
	layer Layer objects
	index Specify layer index



## removeLayer
###### **[removeLayer](#removeLayer)**(layer : ClientSceneLayer): void :
Remove Layer
##### Parameters
	layer Layer objects



## removeLayerAt
###### **[removeLayerAt](#removeLayerAt)**(index : number): void :
Specify a layer to remove
##### Parameters
	index Specify layer index



## setLayerIndex
###### **[setLayerIndex](#setLayerIndex)**(layer : ClientSceneLayer,  index : number): void :
Set the layer to the specified layer, which must already be on the scene
##### Parameters
	layer Layer
	index Specified layer index



## getLayerLength
###### **[getLayerLength](#getLayerLength)**(): number :
Get the current total number of layers

##### Return
[number]

## getLayer
###### **[getLayer](#getLayer)**(index : number): ClientSceneLayer :
Get the layers, indexed according to the actual hierarchy
##### Parameters
	index Hierarchical Index

##### Return
Layer

## getLayerByPreset
###### **[getLayerByPreset](#getLayerByPreset)**(id : number): ClientSceneLayer :
Get layers, based on pre-defined levels
##### Parameters
	id Corresponds to the serial number in the map layer preview



## getLayerByName
###### **[getLayerByName](#getLayerByName)**(name : string): ClientSceneLayer :
Get layer by name
##### Parameters
	name Name of the layer

##### Return
[ClientSceneLayer]

## getPresetSceneObjectDatas
###### **[getPresetSceneObjectDatas](#getPresetSceneObjectDatas)**(): SceneObject[] :
Get scene object data for scene presets (without birth points)

##### Return
Scene object dataset

## addSceneObject
###### **[addSceneObject](#addSceneObject)**(soData : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  isEntity? : boolean,  useModelClass? : boolean): ClientSceneObject :
Scene objects are added to the scene<br>
Since objects involve parameter defaults, state pages, and pre-defined object modules, it is common to use addNewSceneObject/addSceneObjectFromClone to create objects<br>
This is usually used on the current scene to add existing entity objects to it.<br>
Example:<br>
>// soc = [object ClientSceneObject]<br>
>Game.currentScene.addChild(soc,true,true);<br>
>


##### Parameters
	soData Scene object data (can be pure data SceneObject or entity object)
	isEntity [Optional] Default=false whether it is an entity object and not data, if it is data then an entity object will be recreated based on the data
	useModelClass [Optional] Default = false Whether to use the implementation class of the scene object model, which is usually true at the project level

##### Return
[ClientSceneObject] Example of added scene objects

## removeSceneObject
###### **[removeSceneObject](#removeSceneObject)**(so : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  removeFromList? : boolean): ClientSceneObject :
Removing scene objects from the scene
##### Parameters
	so Scene object data, make sure the index of the scene object is the one you need to remove
	removeFromList [Optional] Default=false Whether to remove from the list

##### Return
[ClientSceneObject] Example of removed scene object

## addNewSceneObject
###### **[addNewSceneObject](#addNewSceneObject)**(modelID : number,  presetSceneObjectData? : any): ClientSceneObject :
Add a new object, generate a new object with default values, and also append modified properties (presetSceneObjectData)
##### Parameters
	modelID Model ID
	presetSceneObjectData [Optional] Default=null Preset data to use as a reference when generating, e.g. {x:500,y:500}

##### Return
[ClientSceneObject]

## addSceneObjectFromClone
###### **[addSceneObjectFromClone](#addSceneObjectFromClone)**(fromSceneID : number,  fromSceneObjectindex : number,  isCopy? : boolean,  presetSceneObjectData? : any): ClientSceneObject :
Clone and add scene objects<br> 
Specify an object from a specified pre-defined scene as the clone source, then copy this object to the current scene. <br> 
Prefer to use the fromSceneObjectindex location to hold the scene object, and if an object already exists at that location, automatically calculate the empty location to insert into (this.sceneObjects)<br> 
If sourcing a scene that is not the current scene, the scene must have been preloaded or created before cloning:<br>
&nbsp;-- Preload scene resources AssetManager.preLoadSceneAsset or CreateScene ClientScene.createScene
##### Parameters
	fromSceneID Scene ID of the source
	fromSceneObjectindex Scene object ID in the source scene
	isCopy [optional] default=true whether to clone (used to record that this object is from a clone)
	presetSceneObjectData [Optional] Default=null Pre-defined data (SceneObject properties), such as modified x,y, etc., are assigned initially.

##### Return
[ClientSceneObject] Scene object instance, return null if no model is found


## getGlobalPos
###### **[getGlobalPos](#getGlobalPos)**(localX : number,  localY : number): [Point](file=006-API-2D单机内核/001-通用/019-Point) :
Get the absolute mouse position (relative to the stage) according to the specified scene position
##### Parameters
	localX Coordinates x of the scene (in pixels)
	localY Coordinates y of the scene (in pixels)

##### Return
[Point]

## updateCamera
###### **[updateCamera](#updateCamera)**(): void :
Refresh the footage immediately (by default the scene refreshes the footage frame by frame, e.g. when the bound scene object is moving)



## startRender
###### **[startRender](#startRender)**(): void :
Rendering starts, the scene is at rest if not called, moving layers etc. are not played



## stopRender
###### **[stopRender](#stopRender)**(LayerMoveToZero? : boolean): void :
Stop Rendering
##### Parameters
	LayerMoveToZero [Optional] Default=false whether the layer is moved to zero, if yes then zero, otherwise advance one frame



## hasListener
###### **[hasListener](#hasListener)**(type : string): boolean :
Check if the scenario has registered any listeners for a specific event type<br>
@param	type The type of event.

##### Return
The value is true if the specified type of listener is registered; otherwise, the value is false.

## event
###### **[event](#event)**(type : string,  data? : any): boolean :
Scene dispatch events
##### Parameters
	type	Event type.
	data	[Optional] Default value = null Callback data. If you need to pass multiple parameters p1,p2,p3,... you can use an array structure such as [p1,p2,p3,...] ; if you need to call back a single parameter p that is an array, you need to use a structure such as: [p], for other single parameters p, you can pass the parameter p directly.

##### Return
Whether there is a listener for this event type, the value is true if there is a listener, otherwise the value is false.

## on
###### **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene) :
Use the scenario to register an event listener object of the specified type to enable the listener to receive event notifications
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function. a
	listener	Event listening function.
	args		[Optional] Default=null Callback parameter for the event listen function.

##### Return
This scene object.

## once
###### **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene) :
Use the scenario to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	args		[Optional] Default=null Callback parameter for the event listen function.

##### Return
This scene object.

## off
###### **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene) :
Remove the listener from the scene
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	onceOnly	[Optional] Default=false If the value is true , only the listeners added by the once method will be removed.

##### Return
This scene object.

## offAll
###### **[offAll](#offAll)**(type? : string): [ClientScene](?file=006-API-2D单机内核/002-客户端/016-ClientScene) :
Removes all listeners of the specified event type from the scene
##### Parameters
	type	[Optional] Default=null Event type, if the value is null, remove all types of listeners for this object.

##### Return
This scene object.


## onRender
###### **[onRender](#onRender)**(): void :
Rendering: when Game.pause then no refresh (update) is handled<br>
Support for subclasses to override this method in order to write proprietary game logic<br>
Current method function:<br>
-- Refresh Lens<br>
-- Refresh Layer<br>
-- Refreshing the scene object (update)




