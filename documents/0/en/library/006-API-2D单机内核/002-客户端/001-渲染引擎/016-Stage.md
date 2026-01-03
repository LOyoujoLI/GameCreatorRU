# Stage Stage category
>There is only one stage, which can be accessed via stage<br>Support events:<br>EventObject.KEY_DOWN Press the button<br>EventObject.KEY_UP Push button pop-up<br>EventObject.RESIZE When the window size changes<br>EventObject.FULL_SCREEN_CHANGE When the full screen changes<br>EventObject.FOCUS_CHANGE When the focus changes<br>EventObject.FOCUS When the focus is generated<br>EventObject.BLUR When out of focus<br>EventObject.RENDER When rendering per frame<br>// Event Listening Example<br>stage.on(EventObject.CLICK,this,this.onClick);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→TreeNode<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **width** : number;<br>Current width  |
| **height** : number;<br>Current height  |
| **[scaleMode](#scaleMode)** : string;<br>Zoom mode. The default value is "noscale"  |
| **[alignH](#alignH)** : string;<br>Horizontal alignment. The default value is"left"  |
| **[alignV](#alignV)** : string;<br>Vertical alignment. The default value is"top"  |
| **bgColor** : string;<br>The background color of the stage, default is black  |
| **mouseX** : number;<br>Read-only] X-axis coordinates of the mouse on the Stage  |
| **mouseY** : number;<br>Read-only] The Y-axis coordinate of the mouse on the Stage.  |
| **clientScaleX** : number;<br>Read-only] The X-axis scaling factor of the current viewport caused by the zoom mode.  |
| **clientScaleY** : number;<br>Read-only] The scaling factor of the Y-axis caused by the zoom mode of the current viewport.  |
| **[screenMode](#screenMode)** : string;<br>Scene layout type.  |
| **visible** : boolean;<br>Whether to display  |
| **[fullScreenEnabled](#fullScreenEnabled)** : boolean;<br>Whether to open the full screen, the user click to enter the full screen  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setScreenSize](#setScreenSize)**(screenWidth : number,  screenHeight : number): void<br>Set the screen size and the scene will be adapted to the screen size. This method can be called dynamically to change the size of the game display
| **[exitFullscreen](#exitFullscreen)**(): void<br>Exit full screen mode

## Details

### scaleMode
###### scaleMode : string;
Scaling mode. The default value is "noscale"<br> 
The range of values:<br> 
"noscale" : no scaling<br> 
"exactfit" : full-screen unequal scaling<br> 
"showall" : minimum scaling<br> 
"noborder" : maximum scaling<br> 
"full" : no scaling, the width of the stage is higher than the screen width and height<br> 
"fixedwidth" : constant width, height scaled according to the screen ratio<br> 
"fixedheight" : constant height, width scaled according to the screen ratio<br> 
"fixedauto" : automatically choose to use fixedwidth or fixedheight according to the aspect ratio
### alignH
###### alignH : string;
Horizontal alignment. Default value is "left"<br> 
Range of values: <br> 
"left": left-aligned<br> 
"center": center-aligned<br> 
"right": right-aligned
### alignV
###### alignV : string;
Vertical alignment. The default value is "top"<br> 
The range of values: <br> 
"top": top-aligned<br> 
"middle": center-aligned<br> 
"bottom": bottom-aligned
### screenMode
###### screenMode : string;
Scene layout type. <br> 
Value range: <br> 
"none" : No screen change<br> 
"horizontal" : Auto horizontal<br> 
"vertical" : Auto vertical
### fullScreenEnabled
###### fullScreenEnabled : boolean;
Whether to enable fullscreen or not, users click to enter fullscreen<br> 
Compatibility Note: Some browsers do not allow clicking to enter fullscreen, such as Iphone, etc.


## setScreenSize
###### **[setScreenSize](#setScreenSize)**(screenWidth : number,  screenHeight : number): void :
Set the screen size, the scene will be adapted to the screen size. This method can be called dynamically to change the size of the game display<br> 
@param screenWidth The width of the screen. <br> 
@param screenHeight The height of the screen.



## exitFullscreen
###### **[exitFullscreen](#exitFullscreen)**(): void :
Exit full screen mode





