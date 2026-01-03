# EventObject Event Object
>When an event occurs the callback with such instance<br>is also used for common event class storage, such as EventObject.MOUSE_DOWN<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **MOUSE_DOWN** : string;<br>[Static] Define the value of the type property of the mousedown event object Event when the left mouse button is pressed  |
| **MOUSE_UP** : string;<br>[Static] Define the type property value of mouseup event object Event when left mouse button is popped up  |
| **CLICK** : string;<br>[Static] Define the value of the type property of the click event object Mouse-click event  |
| **RIGHT_MOUSE_DOWN** : string;<br>[Static] Define the value of the type property of the rightmousedown event object Event when the right mouse button is pressed  |
| **RIGHT_MOUSE_UP** : string;<br>[Static] Define the value of the type property of the rightmouseup event object Event when the right mouse button pops up  |
| **RIGHT_CLICK** : string;<br>[Static] Define the value of the type property of the rightclick event object Event on right mouse button click  |
| **MOUSE_MOVE** : string;<br>[Static] Define the value of the type property of the mousemove event object Mouse-over event  |
| **MOUSE_OVER** : string;<br>[Static] Define the type property value of the mouseover event object Mouse-over hover event  |
| **MOUSE_OUT** : string;<br>[Static] Define the type property value of the mouseout event object Mouseout hover event  |
| **MOUSE_WHEEL** : string;<br>[Static] Define the value of the type property of the mousewheel event object Mouse wheel event  |
| **DOUBLE_CLICK** : string;<br>[Static] Define the value of the type property of the doubleclick event object Double-click event of the left mouse button  |
| **CHANGE** : string;<br>[Static] Define the value of the type property of the change event object State change event  |
| **RESIZE** : string;<br>[Static] Define the value of the type property of the resize event object. |
| **ADDED** : string;<br>[Static] Define the value of the type attribute of the added event object to be triggered when it is added to the parent node  |
| **REMOVED** : string;<br>[Static] Define the value of the type attribute of the removed event object to be triggered when it is removed from the parent node  |
| **DISPLAY** : string;<br>[Static] Define the value of the type attribute of the display event object Add to the display list  |
| **UNDISPLAY** : string;<br>[Static] Define the value of the type property of the undisplay event object Add when removing from the display list  |
| **ERROR** : string;<br>[Static] Define the value of the type property of the error event object.  |
| **COMPLETE** : string;<br>[Static] Define the value of the type property of the complete event object.  |
| **LOADED** : string;<br>[Static] Define the value of the loaded event object's type attribute Loaded event  |
| **PROGRESS** : string;<br>[Static] Define the type attribute value of the progress event object Load in-progress event  |
| **INPUT** : string;<br>[Static] Define the type attribute value of the input event object Input event  |
| **RENDER** : string;<br>[Static] Define the type property value of the render event object Render-time event  |
| **KEY_DOWN** : string;<br>[Static] Define the value of the type property of the keydown event object.  |
| **KEY_PRESS** : string;<br>[Static] Define the value of the type property of the keypress event object Press the key once  |
| **KEY_UP** : string;<br>[Static] Define the value of the type property of the keyup event object.  |
| **DRAG_START** : string;<br>[Static] Define the value of the type property of the dragstart event object Drag start  |
| **DRAG_MOVE** : string;<br>[Static] Define the type property value of the dragmove event object.  |
| **DRAG_END** : string;<br>[Static] Define the value of the type property of the dragend event object.  |
| **ENTER** : string;<br>[Static] Define the value of the type property of the enter event object When the Enter key is entered in the input box  |
| **BLUR** : string;<br>[Static] Define the value of the type property of the blur event object.  |
| **FOCUS** : string;<br>[Static] Define the type property value of the focus event object Get focus event  |
| **FOCUS_CHANGE** : string;<br>[Static] Define the value of the type property of the focuschange event object. |
| **FULL_SCREEN_CHANGE** : string;<br>[Static] Triggered when the browser changes full screen  |
| **DEVICE_LOST** : string;<br>[Static] Triggered when the graphics card device is lost  |
| **type** : string;<br>Event type.  |
| **nativeEvent** : any;<br>Native browser events  |
| **target** : Sprite;<br>Event target trigger object  |
| **currentTarget** : Sprite;<br>Event currently bubbling object  |
| **touchId** : number;<br>Unique identification number assigned to the touch point (as int)  |
| **keyCode** : number;<br>Keyboard values  |
| **delta** : number;<br>Roller sliding increments  |
| **touches** : Array<any>;<br>[Read-only] Touch point list.  |
| **altKey** : boolean;<br>Read-only] indicates whether the Alt key is active (true) or inactive (false).  |
| **ctrlKey** : boolean;<br>Read-only] indicates whether the Ctrl key is active (true) or inactive (false).  |
| **shiftKey** : boolean;<br>Read-only] indicates whether the Shift key is active (true) or inactive (false).  |
| **charCode** : boolean;<br>Read-only] Contains the character code value of the key pressed or released. The character code value is the English keyboard value.  |
| **[keyLocation](#keyLocation)** : number;<br>[Read Only] indicates the position of the key on the keyboard. This is useful for distinguishing keys that appear multiple times on the keyboard.  |
| **stageX** : number;<br>[Read-only] X-axis coordinates of mouse on Stage (absolute coordinates)  |
| **stageY** : number;<br>[Read-only] Y-axis coordinates of the mouse on Stage (absolute coordinates)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[stopPropagation](#stopPropagation)**(): void<br>Blocks processing of all event listeners in subsequent nodes of the current node in the event stream. This method does not affect any event listeners in the current node (currentTarget).

## Details

### keyLocation
###### keyLocation : number;
[Read-only] indicates the position of the key on the keyboard. This is useful for distinguishing keys that appear multiple times on the keyboard.<br>
For example, you can distinguish the Left Shift key from the Right Shift key, or the numeric keys from the keypad, based on the value of this property.


## stopPropagation
###### **[stopPropagation](#stopPropagation)**(): void :
Blocks processing of all event listeners in subsequent nodes of the current node in the event stream. This method does not affect any event listeners in the current node (currentTarget).





