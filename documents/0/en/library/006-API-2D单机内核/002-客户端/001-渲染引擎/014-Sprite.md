# Sprite Sprite Show Object Wizard
>Base class for display objects, supporting display images and event response<br>Support for generic mouse events:<br>EventObject.RIGHT_MOUSE_UP Right mouse button pop-up<br>EventObject.RIGHT_MOUSE_DOWN Right mouse button pressed<br>EventObject.RIGHT_CLICK Right mouse click<br>EventObject.CLICK Left mouse button click<br>EventObject.DOUBLE_CLICK Left mouse button double click<br>EventObject.MOUSE_DOWN Left mouse button pressed<br>EventObject.MOUSE_UP Left mouse button pop-up<br>EventObject.MOUSE_WHEEL Mouse wheel<br>EventObject.DRAG_START Mouse drag and drop to start<br>EventObject.DRAG_MOVE Mouse drag and drop to move in<br>EventObject.DRAG_END Mouse drag and drop to move end<br>// Event Listening Example<br>var sp = new Sprite();<br>sp.on(EventObject.CLICK,this,this.onClick);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →TreeNode<br>
**Subcategories**  [GameDialog](?file=007-API-2D网络内核/002-客户端/024-GameDialog)、[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **x** : number;<br>Horizontal coordinates relative to the parent container  |
| **y** : number;<br>Vertical coordinates relative to the parent container  |
| **width** : number;<br>Width, for mouse detection  |
| **height** : number;<br>Height, for mouse detection  |
| **hasMouseEvent** : boolean;<br>[Read Only] Whether there is a mouse event  |
| **scaleX** : number;<br>X-axis scaling value  |
| **scaleY** : number;<br>Y-axis scaling value  |
| **rotation** : number;<br>Rotation angle  |
| **skewX** : number;<br>Horizontal tilt angle  |
| **skewY** : number;<br>Vertical tilt angle  |
| **transform** : Matrix;<br>Matrix information of the object. By setting the matrix you can achieve node rotation, scaling and displacement effects.  |
| **pivotX** : number;<br>Position X of the axis point, scaling and rotation by axis point |
| **pivotY** : number;<br>Position Y of the axis point to scale and rotate with the axis point  |
| **alpha** : number;<br>Transparency  |
| **visible** : boolean;<br>Whether to display  |
| **blendMode** : string;<br>Compositing mode null/lighter/blend1-1 (lighter=additive Numbers can be changed, refer to map layer custom blend mode)  |
| **graphics** : Graphics;<br>Drawing objects  |
| **scrollRect** : Rectangle;<br>Display the scrolling rectangular range of the object with cropping effect  |
| **parent** : TreeNode;<br>Parent Node  |
| **[stage](#stage)** : Stage;<br>[Read-only] If the object is on the stage then return the stage, otherwise return null  |
| **[hitArea](#hitArea)** : any;<br>You can set a Rectangle area as the click area and use it as the mouse event detection after setting  |
| **[mask](#mask)** : Sprite;<br>Mask, you can set an object (support bitmap and vector image), according to the object shape for mask display, support pixel-level mask  |
| **[mouseEnabled](#mouseEnabled)** : boolean;<br>Whether to accept mouse events  |
| **globalScaleX** : number;<br>Read-only] Get the global x-axis scaling value relative to the stage (will superimpose the scaling value of the father node).  |
| **globalScaleY** : number;<br>Read-only] Get the global Y-axis scaling value relative to the stage (will superimpose the scaling value of the father node).  |
| **mouseX** : number;<br>Read-only] Returns the X-axis coordinate information of the mouse on the coordinate system of this object.  |
| **mouseY** : number;<br>Read-only] Returns the Y-axis coordinate information of the mouse on the coordinate system of this object.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[dispose](#dispose)**(): void<br>Destruction
| **[getBounds](#getBounds)**(): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Get the rectangular display area of this object in the parent container coordinate system, which is computationally intensive and used sparingly
| **[getSelfBounds](#getSelfBounds)**(): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Get the rectangular display area of this object in its own coordinate system, which is computationally intensive and used sparingly
| **[localToGlobal](#localToGlobal)**(point : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>Convert local coordinates to global coordinates
| **[globalToLocal](#globalToLocal)**(point : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>Convert global coordinates to local coordinates
| **[startDrag](#startDrag)**(area? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): void<br>Start dragging this object
| **[stopDrag](#stopDrag)**(): void<br>Stop dragging this object
| **[hitTestPoint](#hitTestPoint)**(x : number,  y : number): boolean<br>Detects whether a point is within this object
| **[pos](#pos)**(x : number,  y : number,  speedMode? : boolean): [Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)<br>Set the coordinate position. Equivalent to setting the x and y attributes separately.

## Details

### stage
###### stage : Stage;
[Read-only] If the object is on the stage then return the stage, otherwise return null<br>
@return [Stage]
### hitArea
###### hitArea : any;
You can set a Rectangle area as the click area, and then use that area as the mouse event detection after setting <br>
Support Type:HitArea | Rectangle
### mask
###### mask : Sprite;
Mask, you can set an object (support bitmap and vector image), according to the object shape for mask display, support pixel-level mask<br>
The coordinate system of the mask object is relative to the mask object itself, i.e., the point 0,0 of the object is used.
### mouseEnabled
###### mouseEnabled : boolean;
Whether to accept mouse events<br>
default is false, if listening to mouse events, it will automatically set the value of both this object and the parent node property mouseEnable to true (if the parent node is manually set to false, it will not change)


## dispose
###### **[dispose](#dispose)**(): void :
Destruction



## getBounds
###### **[getBounds](#getBounds)**(): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Get the rectangular display area of this object in the parent container coordinate system, which is computationally intensive and used sparingly

##### Return
Rectangular area

## getSelfBounds
###### **[getSelfBounds](#getSelfBounds)**(): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Get the rectangular display area of this object in its own coordinate system, which is computationally intensive and used sparingly

##### Return
Rectangular area

## localToGlobal
###### **[localToGlobal](#localToGlobal)**(point : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
Convert local coordinates to global coordinates
##### Parameters
	point Local Coordinate Points

##### Return
[Point] Global coordinates after conversion

## globalToLocal
###### **[globalToLocal](#globalToLocal)**(point : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
Convert global coordinates to local coordinates
##### Parameters
	point Global coordinate points

##### Return
[Point] The point of the converted coordinates

## startDrag
###### **[startDrag](#startDrag)**(area? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): void :
Start dragging this object
##### Parameters
	area [Optional] Default=null Within the drag-defined area



## stopDrag
###### **[stopDrag](#stopDrag)**(): void :
Stop dragging this object



## hitTestPoint
###### **[hitTestPoint](#hitTestPoint)**(x : number,  y : number): boolean :
Check if a point is inside this object<br> 
@param x Global x coordinate<br> 
@param y Global y coordinate.

##### Return
 Indicates whether the object is within the

## pos
###### **[pos](#pos)**(x : number,  y : number,  speedMode? : boolean): [Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite) :
Set the coordinate position. Equivalent to setting the x and y attributes separately.<br>
@param	x			X-axis coordinates.<br>
@param	y			Y-axis coordinates.
##### Parameters
		speedMode	(Optional) whether the speed mode, the normal is to call this.x = value to assign, speed mode directly call the internal function processing, if not rewrite x,y properties, it is recommended to set the speed mode for higher performance.
	@return	Returns the object itself.





