# SceneObject Scene object: Base class
>Scene objects usually appear only on scenes, and all scene objects inherit from such<br>The object prototype is derived from the specified object model class, which can be preset in the editor so that different classes have different characteristics (e.g., characters, decorations, etc.)<br>About object model presets:<br>-- Support for custom properties<br>-- Support for loading custom display objects (walking maps, animations, interfaces)<br>-- Support for binding scripts (for implementing features that do not pass, can be made in combination with custom properties and display objects)<br>Regarding archival auto-recording:<br>-- Basic and custom properties of the player's scene objects are automatically recorded during archiving<br>-- The base and custom properties of other scene objects in the current scene are automatically recorded at archive time<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-05-21

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **modelID** : number;<br>Corresponding scene object model  |
| **moduleIDs** : number[];<br>[Read-only] The current set of module IDs  |
| **index** : number;<br>The location of the sceneObject list of the scene, which can also be regarded as a unique ID, the scene object ID in the editor is this property Default value = 0  |
| **name** : string;<br>Name Default=""  |
| **x** : number;<br>Coordinate x (in pixels) Default value = 0  |
| **y** : number;<br>Coordinate y (in pixels) Default value = 0  |
| **layerLevel** : number;<br>Display layer 0-bottom layer 1-middle layer 2-highest layer The level of the scene where the object is located can be found in [ClientScene] Default = 1  |
| **autoPlayEnable** : boolean;<br>Avatar Autoplay Action Default=true  |
| **avatarID** : number;<br>Avatar ID Default = 1  |
| **[avatarOri](#avatarOri)** : number;<br>The role's facing preset value Default = 2  |
| **avatarAct** : number;<br>Character's action:ID preset value Default=1  |
| **avatarFPS** : number;<br>Motion Playback Frequency Preset Default = 12  |
| **avatarFrame** : number;<br>Initial preset frame Default = 0  |
| **avatarAlpha** : number;<br>Transparency Preset Default = 1  |
| **avatarHue** : number;<br>Hue Preset Default = 0  |
| **scale** : number;<br>Avatar body type preset value Default=1  |
| **[displayList](#displayList)** : { [varName: string]: { type: number, id: number } };<br>Show object list data type 1-Specify avatar class 2-Specify fixed interface 3-Specify interface class 4-Specify fixed animation 5-Specify animation class  |
| **moduleDisplayList** : { [varName: string]: { type: number, id: number } }[];<br>Current display list data for all modules Default = []  |
| **playerUID** : number;<br>The player who has control (belongs to the player), the value of 0 for non-player objects is mainly used for judgment Default = 0  |
| **player** : Player;<br>Affiliated players, non-player objects the value is null mainly used to determine with and reference  |
| **[hasCommand](#hasCommand)** : boolean[];<br>Whether to own the event [indexType] = whether to own the event Default = []  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[createModule](#createModule)**(moduleID : number,  soe : SceneObjectEntity,  presetData? : any): SceneObjectModule<br>[Static] Create scene object module (according to the default value of the module)

## Details

### modelID
###### modelID : number;
Corresponding scene object model ID<br> 
Default=1
### avatarOri
###### avatarOri : number;
The role's facing preset value Default = 2<br>
Reference keypad with 5 as the center of the direction system facing other numbers, for example, 2 means facing down (i.e. 5 facing 2 is downward)<br>
7  8  9<br>
4  5  6<br>
1  2  3
### displayList
###### displayList : { [varName: string]: { type: number, id: number } };
Show object list data type 1-Specify avatar class 2-Specify fixed interface 3-Specify interface class 4-Specify fixed animation 5-Specify animation class<br>
The list of displayed objects predefined by the scene object model preset in the editor. Default value = {}
### hasCommand
###### hasCommand : boolean[];
Whether to own the event [indexType] = whether to own the event Default = []<br>
The scene object supports custom trigger event categories, where the possession of events is in the order of the custom trigger event categories.<br>
For example, in RPG games, scene objects may exist: click events, touch events, parallel events, etc. The project layer can execute events based on this property determination


## createModule
###### **[createModule](#createModule)**(moduleID : number,  soe : SceneObjectEntity,  presetData? : any): SceneObjectModule :
[Static] Create scene object module (according to the default value of the module)
##### Parameters
	moduleID Module ID of the scene object
	soe Scene object entities to be installed to
	presetData [optional] default=null preset value data, e.g. { abc: 5, def:6 }

##### 返回
[SceneObjectModule] Modules



