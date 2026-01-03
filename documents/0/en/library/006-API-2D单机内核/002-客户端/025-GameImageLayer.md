# GameImageLayer Image layer
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-11-30

**Inheritance**  →GameSprite<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **camera** : Camera;<br>Camera  |
| **[imageSprites](#imageSprites)** : any;<br>[Static] Record the display objects of all channels Default={}  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[updateFrame](#updateFrame)**(force? : boolean): void<br>Refresh the frame, if you change the camera settings and want to refresh immediately on the current frame, you can call this function yourself, otherwise it will be called automatically every frame in the frame brush (meaning it will be called only on the next frame)
| **[setImageSprite](#setImageSprite)**(passageID : number,  sp : GameSprite): void<br>【Static] Set the channel display object
| **[getImageSprite](#getImageSprite)**(passageID : number): GameSprite<br>[Static] Get the display object that occupies the channel
| **[deletePassage](#deletePassage)**(passageID : number): void<br>[Static] Delete channel
| **[regPassageFrameUpdate](#regPassageFrameUpdate)**(passageID : number,  onUpdate : Function,  thisPtr : any,  args? : any[],  sign? : string): void<br>[Static] Register frame brush effect, support register multiple
| **[clearPassageFrameUpdate](#clearPassageFrameUpdate)**(passageID : number,  sign? : string): void<br>[Static] Clean up the effect of the frame brush function of the channel
| **[getPassageFrameUpdates](#getPassageFrameUpdates)**(): any<br>[Static] Get channel frame brush function

## Details

### imageSprites
###### imageSprites : any;
[Static] Record the display objects of all channels Default={}<br>
Format { [passageID: string]: { displayObject: GameSprite } }


## updateFrame
###### **[updateFrame](#updateFrame)**(force? : boolean): void :
Refresh the frame, if you change the camera settings and want to refresh immediately on the current frame, you can call this function yourself, otherwise it will be called automatically every frame in the frame brush (meaning it will be called only on the next frame)
##### Parameters
	force [Optional] Default=false Force refresh to refresh the camera settings for all objects in the layer
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(By default the system will automatically decide whether to refresh the position of the child object relative to the camera based on whether the camera is updated)



## setImageSprite
###### **[setImageSprite](#setImageSprite)**(passageID : number,  sp : GameSprite): void :
[Static] Set the channel display object
##### Parameters
	passageID Channel number
	sp Show Objects



## getImageSprite
###### **[getImageSprite](#getImageSprite)**(passageID : number): GameSprite :
[Static] Get the display object that occupies the channel
##### Parameters
	passageID Channel number



## deletePassage
###### **[deletePassage](#deletePassage)**(passageID : number): void :
[Static] Delete channel<br>
-- Clear display objects
##### Parameters
	passageID Channel number



## regPassageFrameUpdate
###### **[regPassageFrameUpdate](#regPassageFrameUpdate)**(passageID : number,  onUpdate : Function,  thisPtr : any,  args? : any[],  sign? : string): void :
[Static] Register frame brush effect, support register multiple
##### Parameters
	passageID Channel number
	onUpdate Frame brush function
	thisPtr Scope
	args [optional] default=null custom parameter
	sign [Optional] Default=null Identifier to clean up the specified identifier when cleaning up



## clearPassageFrameUpdate
###### **[clearPassageFrameUpdate](#clearPassageFrameUpdate)**(passageID : number,  sign? : string): void :
[Static] Clean up the effect of the frame brush function of the channel
##### Parameters
	passageID Channel number
	sign [Optional] Default=null Identifiers, cleanup can be done with specified identifiers



## getPassageFrameUpdates
###### **[getPassageFrameUpdates](#getPassageFrameUpdates)**(): any :
[Static] Get channel frame brush function<br>
-- passageID Channel number<br>
-- onUpdate Frame brush function<br>
-- thisPtr Scope<br>
-- sign Marking<br>
-- args Customized parameters

##### Return
{ [passageID: string]: { onUpdate: Function, thisPtr: any, sign: string, args: any[] }[] }



