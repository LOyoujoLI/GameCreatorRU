# ClientSceneObject Scene object-client base class
>The actual scene object class that appears on the game screen and that all client-side scene object implementation classes inherit from<br>[Internal display hierarchy].<br>-- Animation layer: bottom layer animationLowLayer Animations played with playAnimation at a lower level than the target effect layer are added here<br>-- Custom base layers (layers lower than Avatar in the preset, including Avatar) customLayer<br>-- Animation Level: High Level animationHighLayer Animations played with playAnimation that are higher than the target effect layer are added here<br>-- Custom High Level (higher level than Avatar in the preset)customHighLayer<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-24

**Inheritance**  →[SceneObjectEntity](?file=007-API-2D网络内核/001-通用/026-SceneObjectEntity)→[SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **player** : ClientPlayer;<br>Affiliated players  |
| **root** : GameSprite;<br>The root container of the display object, the scene object on the scene actually adds this container to the display container (displayObject) of the scene  |
| **shadow** : GameSprite;<br>Shadow, by default, is added on the shadow layer of the scene so that it is lower than all objects  |
| **animationLowLayer** : GameSprite;<br>Bottom animation layer Animations played with playAnimation that are lower than the target effect layer are added here  |
| **avatar** : Avatar;<br>Avatar  |
| **avatarContainer** : GameSprite;<br>Avatar container, parent node of the loaded Avatar  |
| **customLayer** : GameSprite;<br>Custom layers Layers lower than Avatar in the preset, including Avatar (avatar)  |
| **animationHighLayer** : GameSprite;<br>High-level animation layers Animations played with playAnimation that are higher than the target effect layer are added here  |
| **customHighLayer** : GameSprite;<br>Model object preset high level (higher level in preset than Avatar)  |
| **scene** : ClientScene;<br>This value will be set when adding to the scene and will not be set to null when removing  |
| **[actionIndex](#actionIndex)** : number;<br>Play action according to action index  |
## **Protected Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **_x** : number;<br>Horizontal Coordinates  |
| **_y** : number;<br>Vertical Coordinates  |
## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(soData? : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject),  scene? : [ClientScene](?file=007-API-2D网络内核/002-客户端/017-ClientScene))<br>Constructors
| **[dispose](#dispose)**(): void<br>Release
| **[drawShadow](#drawShadow)**(scalePer? : number): void<br>Draws a shadow, for example, when the shadow needs to be scaled
| **[stopRender](#stopRender)**(stopCurrentFrame? : boolean): void<br>Stops rendering, and Game.pause automatically calls this function for objects in the scene
| **[recoveryRender](#recoveryRender)**(continueCurrentFrame? : boolean): void<br>Resume rendering and Game.pause will automatically call this function for the object in the scene
| **[refreshCoordinate](#refreshCoordinate)**(): void<br>This function should be called after entering a new coordinate
| **[update](#update)**(nowTime : number): void<br>Refresh: the scene will call all scenes above the scene object of this function, the execution logic should be implemented by the subclass, this function under the class without any code implementation
| **[playAnimation](#playAnimation)**(aniID : number,  loop : boolean,  isHit : boolean,  fps? : number,  superposition? : boolean): [GCAnimation](?file=007-API-2D网络内核/002-客户端/011-GCAnimation)<br>Play the animation, the target object is Avatar
| **[stopAnimation](#stopAnimation)**(aniID : any): void<br>Stop animation
| **[stopAllAnimation](#stopAllAnimation)**(): void<br>Stop all animations
| **[hasListener](#hasListener)**(type : string): boolean<br>Check if the EventDispatcher object has any listeners registered for a specific event type.
| **[event](#event)**(type : string,  data? : any): boolean<br>Handout events.
| **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)<br>Use the EventDispatcher object to register an event listener object of the specified type so that the listener can receive event notifications.
| **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)<br>Use the EventDispatcher object to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event.
| **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)<br>Removes the listener from the EventDispatcher object.
| **[offAll](#offAll)**(type? : string): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)<br>Removes all listeners of the specified event type from the EventDispatcher object.
## Protected Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[updateShadow](#updateShadow)**(): void<br>Refresh the shadow, update the shadow coordinates, refreshCoordinate will call this function in order to update the shadow coordinates
## Details

### actionIndex
###### actionIndex : number;
Play action according to action index<br>
@return [number]


## constructor
###### **[constructor](#constructor)**(soData? : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject),  scene? : [ClientScene](?file=007-API-2D网络内核/002-客户端/017-ClientScene)) :
Constructors
##### Parameters
	soData [Optional] Default=null Scene object data
	scene [Optional] Default=null Scenario



## dispose
###### **[dispose](#dispose)**(): void :
Release



## drawShadow
###### **[drawShadow](#drawShadow)**(scalePer? : number): void :
Draws a shadow, for example, when the shadow needs to be scaled
##### Parameters
	scalePer [Optional] Default value = 1.0 Scaling



## stopRender
###### **[stopRender](#stopRender)**(stopCurrentFrame? : boolean): void :
Stops rendering, and Game.pause automatically calls this function for objects in the scene<br>
Stop Avatar playback and all animations
##### Parameters
	stopCurrentFrame [Optional] Default=false Whether to stop at the current frame true=current frame false=initially set frame



## recoveryRender
###### **[recoveryRender](#recoveryRender)**(continueCurrentFrame? : boolean): void :
Resume rendering and Game.pause will automatically call this function for the object in the scene<br>
Resume Avatar playback and all animations
##### Parameters
	continueCurrentFrame [Optional] Default=false Whether Avatar resumes playback from the current frame true=current frame false=initially set frame



## refreshCoordinate
###### **[refreshCoordinate](#refreshCoordinate)**(): void :
This function should be called after entering a new coordinate<br>
-- This function is called after a scene object has been added to the scene<br>
-- This function calls updateShadow, which can be overridden by subclasses to achieve more functionality



## update
###### **[update](#update)**(nowTime : number): void :
Refresh: the scene will call all scenes above the scene object of this function, the execution logic should be implemented by the subclass, this function under the class without any code implementation
##### Parameters
	nowTime Game timestamp (Game.pause pauses the game timestamp)



## playAnimation
###### **[playAnimation](#playAnimation)**(aniID : number,  loop : boolean,  isHit : boolean,  fps? : number,  superposition? : boolean): [GCAnimation](?file=007-API-2D网络内核/002-客户端/011-GCAnimation) :
Play the animation, the target object is Avatar<br>

##### Parameters
	aniID Animation number, which specifies the number of the animation editor preset
	loop Whether to play in a loop
	isHit Whether to show the effect of being hit, the animation editor supports the animation layer to show only when hit, if set to true that means all layers of the animation are shown
	fps [Optional] Default=null Frame rate, if none use Config.ANIMATION_FPS
	superposition [Optional] Default=false Overlay, default is not overlay, i.e. the same ID will replay the animation, stopping the animation cannot be stopped by using ID but must be passed into the Animation object

##### Return
[GCAnimation]

## stopAnimation
###### **[stopAnimation](#stopAnimation)**(aniID : any): void :
Stop animation
##### Parameters
	aniID Animation number/object number | [GCAnimation]



## stopAllAnimation
###### **[stopAllAnimation](#stopAllAnimation)**(): void :
Stop all animations



## hasListener
###### **[hasListener](#hasListener)**(type : string): boolean :
Check if the EventDispatcher object has any listeners registered for a specific event type.<br>
@param	type The type of event.

##### Return
The value is true if the listener of the specified type is registered; otherwise, the value is false.

## event
###### **[event](#event)**(type : string,  data? : any): boolean :
Handout events.
##### Parameters
	type	Event type.
	data	(Optional) Callback data. <b>Note:</b> If you need to pass multiple parameters p1,p2,p3,... you can use an array structure such as [p1,p2,p3,...] ; if you need to call back a single parameter p that is an array, you need to use a structure such as: [p], other than a single parameter p, you can pass in the parameter p directly.

##### Return
Whether there is a listener for this event type, the value is true if there is a listener, otherwise the value is false.

## on
###### **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject) :
Use the EventDispatcher object to register an event listener object of the specified type so that the listener can receive event notifications.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function. a
	listener	Event listening function.
	args		(Optional) Callback parameters for the event listen function.

##### Return
This EventDispatcher object. a

## once
###### **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject) :
Use the EventDispatcher object to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	args		(Optional) Callback parameters for the event listen function.

##### Return
此 EventDispatcher 对象。

## off
###### **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject) :
Removes the listener from the EventDispatcher object.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	onceOnly	(Optional) If the value is true , only the listeners added by the once method will be removed.

##### Return
This EventDispatcher object.

## offAll
###### **[offAll](#offAll)**(type? : string): [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject) :
Removes all listeners of the specified event type from the EventDispatcher object.
##### Parameters
	type	(Optional) The event type, or if the value is null, remove all types of listeners for this object.

##### Return
This EventDispatcher object.


## updateShadow
###### **[updateShadow](#updateShadow)**(): void :
Refresh the shadow, update the shadow coordinates, refreshCoordinate will call this function in order to update the shadow coordinates




