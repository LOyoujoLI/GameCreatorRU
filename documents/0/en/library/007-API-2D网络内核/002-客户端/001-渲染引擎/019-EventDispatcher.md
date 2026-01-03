# EventDispatcher Event Scheduler
>Base class for all classes that can dispatch events.<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[hasListener](#hasListener)**(type : string): boolean<br>Check if the EventDispatcher object has any listeners registered for a specific event type.
| **[event](#event)**(type : string,  data? : any): boolean<br>Handout events.
| **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>Use the EventDispatcher object to register an event listener object of the specified type so that the listener can receive event notifications.
| **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>Use the EventDispatcher object to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event.
| **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>Removes the listener from the EventDispatcher object.
| **[offAll](#offAll)**(type? : string): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>Removes all listeners of the specified event type from the EventDispatcher object.
| **[isMouseEvent](#isMouseEvent)**(type : string): boolean<br>Detects if the specified event type is a mouse event.

## Details



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
	data	(Optional) Callback data. Default value = null Note: If you need to pass multiple parameters p1,p2,p3,... you can use an array structure such as [p1,p2,p3,...] ; if you need to call back a single parameter p is an array, you need to use a structure such as: [p], other than a single parameter p, you can directly pass in the parameter p.

##### Return
Whether there is a listener for this event type, the value is true if there is a listener, otherwise the value is false.

## on
###### **[on](#on)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher) :
Use the EventDispatcher object to register an event listener object of the specified type so that the listener can receive event notifications.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	args		(Optional) Callback parameter for the event listening function. Default value = null

##### Return
This EventDispatcher object.

## once
###### **[once](#once)**(type : string,  caller : any,  listener : Function,  args? : Array<any>): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher) :
Use the EventDispatcher object to register an event listener object of the specified type to enable the listener to receive event notifications, which are automatically removed after one response to the listener event.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	args		(Optional) Callback parameter for the event listening function. Default value = null

##### Return
This EventDispatcher object.

## off
###### **[off](#off)**(type : string,  caller : any,  listener : Function,  onceOnly? : boolean): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher) :
Removes the listener from the EventDispatcher object.
##### Parameters
	type		The type of event.
	caller	The execution domain of the event listening function.
	listener	Event listening function.
	onceOnly	(Optional) If the value is true , only the listeners added by the once method will be removed. Default value = false

##### Return
This EventDispatcher object.

## offAll
###### **[offAll](#offAll)**(type? : string): [EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher) :
Removes all listeners of the specified event type from the EventDispatcher object.
##### Parameters
	type	(Optional) The event type, if null, removes all types of listeners for this object. Default value = null

##### Return
This EventDispatcher object.

## isMouseEvent
###### **[isMouseEvent](#isMouseEvent)**(type : string): boolean :
Detects if the specified event type is a mouse event.<br>
@param	type The type of event.<br>
@return	If it is a mouse event, the value is true; otherwise, the value is false.





