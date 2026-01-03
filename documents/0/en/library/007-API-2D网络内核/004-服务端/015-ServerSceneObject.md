# ServerSceneObject Server Scene Objects
>This class does not have any logical functions, the subclasses of this class in the project layer should implement the coarse logical functions<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-24

**Inheritance**  →[SceneObjectEntity](?file=007-API-2D网络内核/001-通用/026-SceneObjectEntity)→[SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **scene** : ServerScene;<br>Affiliated scenes  |
| **player** : ServerPlayer;<br>Affiliated Players  |
| **customCommandPages** : CommandPage[];<br>Scene object custom event page Subscript=indexType 0~n Default=[]  |
| **isCopy** : boolean;<br>[Read Only] Whether copy  |
| **isDisposed** : boolean;<br>Released or not  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[syncClientData](#syncClientData)**(syncSelf : boolean): any<br>Data synchronized to the client: contains scene objects and player data (if the player)
| **[constructor](#constructor)**(): (soData? SceneObject, presetCustomAttrs?<br>Constructor: To create a server object, you need to create it with ServerSceneObject::create.
| **[dispose](#dispose)**(): void<br>Destruction
| **[create](#create)**(): (soData SceneObject, presetCustomAttrs?<br>[Static] Create scene object
| **[clone](#clone)**(fromSceneID : number,  fromSceneObjectindex : number,  toScene : [ServerScene](?file=007-API-2D网络内核/004-服务端/014-ServerScene),  isCopy? : boolean,  x? : number,  y? : number): [ServerSceneObject](?file=007-API-2D网络内核/004-服务端/015-ServerSceneObject)<br>[Static] Cloning scene objects
| **[update](#update)**(now : number): void<br>Update function

## Details



## syncClientData
###### **[syncClientData](#syncClientData)**(syncSelf : boolean): any :
Data synchronized to the client: contains scene objects and player data (if the player)<br>
The custom properties in the data only contain properties that are set to "[Synchronize this property] when the object appears" (properties can be designed in [Scene Object Model Settings] and [Player Data Settings])
##### Parameters
	syncSelf Whether or not to sync to yourself, depending on the settings you can filter which attributes can be synced to other player clients

##### Return
Allow synchronization of client's data (public data, if it is not public it will not be transferred)

## constructor
###### **[constructor](#constructor)**(): (soData? SceneObject, presetCustomAttrs? :
Constructor: To create a server object, you need to create it with ServerSceneObject::create.
##### Parameters
	soData [Optional] Default=null Reference SceneObject, created from this data
	presetCustomAttrs [Optional] Default=null Reference data Preset attribute, if null the default value of the model data is used
	player [Optional] Default=null The player to which the object belongs, or null if it is an NPC



## dispose
###### **[dispose](#dispose)**(): void :
Destruction<br>
Active creation or cloning or player objects before they are destroyed



## create
###### **[create](#create)**(): (soData SceneObject, presetCustomAttrs? :
[Static] Create scene object<br>
The actual creation of the corresponding class based on the modelID of the SceneObject (the scene object model has its own implementation class ServerSceneObject_X)
##### Parameters
	soData Refer to the SceneObject to create the
	presetCustomAttrs [Optional] Default=null Reference data Preset attribute, if null the default value of the model data is used
	player [Optional] Default=null The player to which the object belongs, or null if it is an NPC
	isClone [Optional] Default = true Whether from clone (this value is generally true for non-predefined objects)

##### Return
[ServerSceneObject] The actual scene object class

## clone
###### **[clone](#clone)**(fromSceneID : number,  fromSceneObjectindex : number,  toScene : [ServerScene](?file=007-API-2D网络内核/004-服务端/014-ServerScene),  isCopy? : boolean,  x? : number,  y? : number): [ServerSceneObject](?file=007-API-2D网络内核/004-服务端/015-ServerSceneObject) :
[Static] Cloning scene objects<br>
You can copy scene objects from scene A to scene B
##### Parameters
	fromSceneID The ID of the scene where the copy is located
	fromSceneObjectindex Index where the copy is located
	toScene [Optional] Default=null Cloned to scene (e.g. current scene)
	isClone [Optional] Default = true Whether from clone (this value is generally true for non-predefined objects)
	x [optional] default=null Use x as the default coordinate x if available, otherwise use the coordinate x of the cloned source
	y [Optional] Default=null Use y as the default coordinate y if available, otherwise use the coordinate y of the cloned source

##### Return
[ServerSceneObject] The actual object class

## update
###### **[update](#update)**(now : number): void :
Update function<br>
Implemented by subclasses, generally used for scene frame brushes to call the scene object's frame brush in order to execute the logic frame by frame
##### Parameters
	now Current time unix timestamp





