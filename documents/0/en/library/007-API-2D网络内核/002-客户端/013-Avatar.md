# Avatar Avatar display object
>Display the current image by action, part, direction, and frame<br>-- Support the direction: 1 direction, 2 direction, 3 direction, 4 direction, 5 direction, 8 direction, where 1, 3, 5 direction material will automatically flip horizontally in order to save material use<br>-- Support for auxiliary bodies for visualization of project layers to create data for auxiliary purposes such as animated hit points, ballistic launch points in different directions, etc.<br>-- Support for changing parts (dressing)<br>-- Common events supported:EventObject.LOADED<br>-- Directional system reference keypad centered on 5 facing other numbers: 1 - lower left 2 - lower 3 - lower right 4 - left 6 - right 7 - upper left 8 - upper 9 - upper right<br>&nbsp;&nbsp;&nbsp;7 8 9<br>&nbsp;&nbsp;&nbsp;4 5 6<br>&nbsp;&nbsp;&nbsp;1 2 3<br>Usage:<br>var a = new Avatar();<br>a.id = 5;<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>&nbsp;Avatar.ACTION_PLAY_COMPLETED When the action is finished playing<br>&nbsp;Avatar.CHANGE_ACTION When changing the action Parameter 1: Action ID before change Parameter 2: Action ID after change<br>&nbsp;Avatar.RENDER Dispatched when a new frame is actually reached, not dispatched if the body does not have an actual frame<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-12-06

**Inheritance**  →GameSprite<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[ACTION_PLAY_COMPLETED](#ACTION_PLAY_COMPLETED)** : string;<br>[Static] event: The event is thrown whenever the action is finished playing, only when the last frame has been played according to the frame rate is the event thrown  |
| **[CHANGE_ACTION](#CHANGE_ACTION)** : string;<br>[Static] Event: Dispatched whenever the action is changed  |
| **[RENDER](#RENDER)** : string;<br>[Static] event: dispatched when onRender is executed, dispatched when a new frame is reached  |
| **[id](#id)** : number;<br>Avatar unique ID, corresponding to the preset production data ID in the editor, will throw EventObject.LOADED when the resource is loaded after setting  |
| **[syncLoadWhenAssetExist](#syncLoadWhenAssetExist)** : boolean;<br>synchronous loading, when the resource exists, the current frame is displayed immediately, default is true  |
| **[prerender](#prerender)** : boolean;<br>Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.  |
| **oriMode** : number;<br>[Read Only] Direction Mode 1 2 3 4 5 8 where 1, 3, 5 will automatically mirror the flip, from the editor in the preset  |
| **isPlaying** : boolean;<br>[Read Only] Get whether it is in play  |
| **isLoading** : boolean;<br>Read-only] to get whether it is loading, set the id if the resource is not loaded then the state is true  |
| **fps** : number;<br>Frame rate: the number of frames per second, for example, fps=12 means 12 frames per second  |
| **fixedOrientation** : boolean;<br>Fixed orientation, ignore the request to change orientation when this is turned on, i.e. setting orientation is invalid  |
| **[refObjs](#refObjs)** : {<br>Auxiliary body id => AvatarRefObj Default = {}  |
| **picUrls** : string[];<br>The index in AvatarFrameImage corresponds to the position of this array. Default = []  |
| **currentFrameImage** : AvatarFrameImage;<br>Current frame map (if available)  |
| **currentFrame** : number;<br>Set and get the current frame: for example, 1 means the first frame  |
| **totalFrame** : number;<br>[Read-only] Total number of frames (based on current action-direction)  |
| **topAvatar** : Avatar;<br>Root node: The component can use this item to get its own root node, and this property of the root node is the root node itself  |
| **[orientation](#orientation)** : number;<br>Set the orientation, refer to the keypad direction, with 5 as the center facing the direction of other numbers: 1 - lower left 2 - lower 3 - lower right 4 - left 6 - right 7 - upper left 8 - upper 9 - upper right  |
| **[actionIndex](#actionIndex)** : number;<br>Set the action, according to the index, setting an invalid action will ignore the change  |
| **[actionID](#actionID)** : number;<br>Set the action, according to the action ID, set an invalid action will ignore this change  |
| **actionList** : AvatarAction[];<br>[Read Only] Get the action list, must be loaded before you can get  |
| **[PartLength](#PartLength)** : number;<br>[Read Only] Returns the number of parts (including the body, or 1 if only the body)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[hasActionID](#hasActionID)**(actionID : number): boolean<br>Presence or absence of action
| **[addPartByAvatar](#addPartByAvatar)**(partID : number,  part : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  partIndex? : number): boolean<br>Adds a part, depending on the part object, or ignores it if it already exists
| **[addPartByID](#addPartByID)**(partID : number,  avatarID : number,  partIndex? : number): boolean<br>Add part: according to the specified part corresponding to the database ID, ignore if the part already exists
| **[removePartByPartID](#removePartByPartID)**(partID : number,  disposeOldPart? : boolean): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)<br>Remove part: according to the specified part ID
| **[removePartByAvatar](#removePartByAvatar)**(part : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  disposeOldPart? : boolean): boolean<br>Removal part: According to the part object
| **[changePartByAvatar](#changePartByAvatar)**(newPart : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  partID : number): boolean<br>Replacement part: according to the new part and part ID
| **[changePartByAvatarID](#changePartByAvatarID)**(newAvatarID : number,  partID : number): boolean<br>Part replacement: according to the database ID and part ID corresponding to the new part
| **[getPartByPartID](#getPartByPartID)**(partID : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)<br>Get the part: according to the part ID
| **[getPartAt](#getPartAt)**(partIndex : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)<br>Get the part according to the index of the location where the part is located
| **[getPartByID](#getPartByID)**(avatarID : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)<br>Get the part according to the database ID corresponding to the part
| **[getPartIndex](#getPartIndex)**(avatar : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)): number<br>Get the index of a part by its location
| **[gotoAndPlay](#gotoAndPlay)**(frame? : number,  isHit? : boolean,  loop? : boolean): void<br>Jumping a frame for playback, crossing the border will automatically take the mode (e.g. frame length 10, playing 13 is playing 3)
| **[play](#play)**(): void<br>Playback starts at the current frame rate
| **[stop](#stop)**(frame? : number): void<br>Stop Play
| **[hitTestPoint](#hitTestPoint)**(stageX : number,  stageY : number): boolean<br>Pixel-level click-touch detection

## Details

### ACTION_PLAY_COMPLETED
###### ACTION_PLAY_COMPLETED : string;
[Static] event: The event is thrown every time the action is finished playing, only when the last frame has been played at the frame rate.<br>
>var a = new Avatar();<br>
>a.id = 5;<br>
>a.on(Avatar.ACTION_PLAY_COMPLETED,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### CHANGE_ACTION
###### CHANGE_ACTION : string;
[Static] Event: Dispatched whenever the action is changed<br>
onChangeAction(lastActID:number,nowActID:number); lastActID=Action ID before change nowActID=Action ID after change<br>
>var a = new Avatar();<br>
>a.id = 5;<br>
>a.on(Avatar.CHANGE_ACTION,this,(lastActID:number,nowActID:number)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>a.actionID = 2;<br>
>


### RENDER
###### RENDER : string;
[Static] event: dispatched when onRender is executed, dispatched when a new frame is reached<br>
>var a = new Avatar();<br>
>a.id = 5;<br>
>a.on(Avatar.RENDER,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### id
###### id : number;
AVATAR unique ID, corresponding to the preset production data ID in the editor, will throw EventObject.LOADED when the resource is loaded after setting<br>
>var a = new Avatar();<br>
>a.on(EventObject.LOADED,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>a.id = 5;<br>
>


### syncLoadWhenAssetExist
###### syncLoadWhenAssetExist : boolean;
synchronous loading, when the resource exists, the current frame is displayed immediately, default is true<br>
LOADED event, it is recommended to listen to this event before setting the id
### prerender
###### prerender : boolean;
Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Pre-rendering will consume some performance, you can choose to use this in the case of Avatar resources are larger and more, turn on this will have additional performance and memory overhead
### refObjs
###### refObjs : {
Auxiliary Body id => AvatarRefObj Default Value={}<br>
You can use the various auxiliary body information preset by the editor to make some logic of the project layer
### orientation
###### orientation : number;
Set the orientation, refer to the keypad direction, with 5 as the center facing the direction of other numbers: 1 - lower left 2 - lower 3 - lower right 4 - left 6 - right 7 - upper left 8 - upper 9 - upper right<br>
Setting an invalid orientation will ignore this change<br>
7 8 9<br>
4 5 6<br>
1 2 3
### actionIndex
###### actionIndex : number;
Set the action, according to the index, setting an invalid action will ignore the change<br>
@param index Action Index
### actionID
###### actionID : number;
Set the action, according to the action ID, set an invalid action will ignore this change<br>
@param id Action ID
### PartLength
###### PartLength : number;
[Read-only] return the number of parts (including the body, if only the body then return 1)<br>
The Avatar needs to be loaded before it is allowed to be used


## hasActionID
###### **[hasActionID](#hasActionID)**(actionID : number): boolean :
Presence or absence of action
##### Parameters
	actionID The ID of the action that exists

##### Return
[boolean]

## addPartByAvatar
###### **[addPartByAvatar](#addPartByAvatar)**(partID : number,  part : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  partIndex? : number): boolean :
Adding a part, depending on the part object, or ignoring it if it already exists<br>
The Avatar needs to be loaded before it is allowed to be used<br>
No need to manually uninstall the added parts
##### Parameters
	partID Department ID
	part Parts
	partIndex [Optional] Default = -1 Position of insertion, default -1 means auto insertion to the topmost level

##### Return
[boolean] Whether to add successfully

## addPartByID
###### **[addPartByID](#addPartByID)**(partID : number,  avatarID : number,  partIndex? : number): boolean :
Add part: according to the specified part corresponding to the database ID, if the part already exists then ignore<br>
The Avatar needs to be loaded before it is allowed to be used<br>
No need to manually uninstall the added parts
##### Parameters
	partID Department ID
	avatarID The database ID corresponding to the part
	partIndex [Optional] Default = -1 Position of insertion, default -1 means auto insertion to the topmost level

##### Return
[boolean] Whether to add successfully

## removePartByPartID
###### **[removePartByPartID](#removePartByPartID)**(partID : number,  disposeOldPart? : boolean): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar) :
Remove part: according to the specified part ID<br>
The Avatar needs to be loaded before it is allowed to be used<br>
Selectable parameter for uninstallation, "If automatic uninstallation is not selected, manual uninstallation is required".
##### Parameters
	partID Department ID
	disposeOldPart [Optional] Default = true whether to uninstall the old part, if set to false then you have to uninstall it manually by yourself

##### Return
[Avatar] Parts

## removePartByAvatar
###### **[removePartByAvatar](#removePartByAvatar)**(part : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  disposeOldPart? : boolean): boolean :
Removal part: According to the part object<br>
The Avatar needs to be loaded before it is allowed to be used<br>
Selectable parameter for uninstallation, "If automatic uninstallation is not selected, manual uninstallation is required".
##### Parameters
	part Parts
	disposeOldPart [Optional] Default = true whether to uninstall the old part, if set to false then you have to uninstall it manually by yourself

##### Return
[boolean] Whether the removal was successful or not

## changePartByAvatar
###### **[changePartByAvatar](#changePartByAvatar)**(newPart : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar),  partID : number): boolean :
Replacement part: according to the new part and part ID<br>
The Avatar needs to be loaded before it is allowed to be used<br>
The new widget will automatically inherit the settings of the original widget (such as position, zoom, hue, transparency and other settings)<br>
The original part is automatically uninstalled
##### Parameters
	newPart New parts
	partID Department ID

##### Return
[boolean]

## changePartByAvatarID
###### **[changePartByAvatarID](#changePartByAvatarID)**(newAvatarID : number,  partID : number): boolean :
Part replacement: according to the database ID and part ID corresponding to the new part<br>
The Avatar needs to be loaded before it is allowed to be used<br>
The new widget will automatically inherit the settings of the original widget (such as position, zoom, hue, transparency and other settings)<br>
The original part is automatically uninstalled
##### Parameters
	newAvatarID The database ID corresponding to the new part
	partID Department ID
##### Return
[boolean]

## getPartByPartID
###### **[getPartByPartID](#getPartByPartID)**(partID : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar) :
Get the part: according to the part ID<br>
The Avatar needs to be loaded before it is allowed to be used
##### Parameters
	partID Department ID

##### Return
[Avatar] Parts

## getPartAt
###### **[getPartAt](#getPartAt)**(partIndex : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar) :
Get the part according to the index of the location where the part is located<br>
The Avatar needs to be loaded before it is allowed to be used
##### Parameters
	partIndex The index where the part is located (index range 0~PartLength-1)

##### Return
[Avatar] Parts

## getPartByID
###### **[getPartByID](#getPartByID)**(avatarID : number): [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar) :
Get the part according to the database ID corresponding to the part<br>
The Avatar needs to be loaded before it is allowed to be used
##### Parameters
	avatarID The database ID corresponding to the part

##### Return
[Avatar] component, or null if it does not exist

## getPartIndex
###### **[getPartIndex](#getPartIndex)**(avatar : [Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)): number :
Get the index of a part by its location<br>
The Avatar needs to be loaded before it is allowed to be used
##### Parameters
	avatar Parts

##### Return
[number] Index range 0~PartLength-1, does not exist then return -1

## gotoAndPlay
###### **[gotoAndPlay](#gotoAndPlay)**(frame? : number,  isHit? : boolean,  loop? : boolean): void :
Jumping a frame for playback, crossing the border will automatically take the mode (e.g. frame length 10, playing 13 is playing 3)<br>
@frame [optional] the number of frames to jump, default frame=1, 1 means the first frame<br>
@isHit [Optional] Default hit mode, the elements inside the animation have a mode that is only displayed on hit, you can set this to false to block the effect on hit.<br>
@loop [Optional] If or not loop play Defaultfalse



## play
###### **[play](#play)**(): void :
Playback starts at the current frame rate



## stop
###### **[stop](#stop)**(frame? : number): void :
Stop Play
##### Parameters
	frame [Optional] Default value = 0 Specify the number of frames to dwell on



## hitTestPoint
###### **[hitTestPoint](#hitTestPoint)**(stageX : number,  stageY : number): boolean :
Pixel-level click-touch detection
##### Parameters
	stageX Coordinates relative to the stage x
	stageY Coordinate y relative to the stage

##### Return
[boolean] Whether to click in



