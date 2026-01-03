# Tween Jogging class
>Use this type to enable fading of the target object's properties. It is generally used in conjunction with[Ease](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/032-Ease)Use<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **update** : Callback;<br>Update the callback, when the jogging value changes, call back the changed value  |
| **progress** : number;<br>Set the current execution ratio  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[to](#to)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)<br>[Static] Jog the props property of the object to the target value.
| **[from](#from)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)<br>[Static] From the props property, jog to the current state.
| **[to](#to)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)<br>Jogs the props property of the object to the target value.
| **[from](#from)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)<br>From the props property, jogs to the current state.
| **[complete](#complete)**(): void<br>Immediately end the jog and get to the end.
| **[pause](#pause)**(): void<br>Pause the jogging and you can restart it by resume or restart.
| **[setStartTime](#setStartTime)**(startTime : number): void<br>Set the start time.
| **[clearAll](#clearAll)**(target : any): void<br>[Static] Clear all the jogs on the specified target object.
| **[clear](#clear)**(tween : [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)): void<br>[Static] Clean up a certain slow motion.
| **[clear](#clear)**(): void<br>Stops and clears the current jog.
| **[restart](#restart)**(): void<br>Restart the suspended slow motion.
| **[resume](#resume)**(): void<br>Resume suspended jogging.

## Details



## to
###### **[to](#to)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween) :
[Static] Jog the props property of the object to the target value.<br>
@param	target The target object (the object whose property value is about to be changed).<br>
@param	props A list of attributes that change, such as<br>
@param	duration Time spent, in milliseconds.<br>
@param	ease Jog type, default is uniform motion. Default=null<br>
@param	complete End the callback function. Default value = null<br>
@param	delay Delay execution time. Default value = 0<br>
@param	coverBefore Indicates if the previous jogging is overwritten. Default=false<br>
@return	Returns the Tween object.



## from
###### **[from](#from)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween) :
[Static] From the props property, jog to the current state.<br>
@param	target The target object (the object whose property value is about to be changed).<br>
@param	props A list of attributes that change, such as<br>
@param	duration Time spent, in milliseconds.<br>
@param	ease Jog type, default is uniform motion. Default=null<br>
@param	complete End the callback function. Default value = null<br>
@param	delay Delay execution time. Default value = 0<br>
@param	coverBefore Indicates if the previous jogging is overwritten. Default=false<br>
@return	Returns the Tween object.



## to
###### **[to](#to)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween) :
Jogs the props property of the object to the target value.<br>
@param	target The target object (the object whose property value is about to be changed).<br>
@param	props A list of attributes that change, such as<br>
@param	duration Time spent, in milliseconds.<br>
@param	ease Jog type, default is uniform motion. Default value=null<br>
@param	complete End the callback function. Default value=null<br>
@param	delay Delay execution time. Default value=0<br>
@param	coverBefore Indicates if the previous jogging is overwritten. Default value=false<br>
@return	Returns the Tween object.



## from
###### **[from](#from)**(target : any,  props : any,  duration : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback),  delay? : number,  coverBefore? : boolean): [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween) :
From the props property, jogs to the current state.<br>
@param	target The target object (the object whose property value is about to be changed).<br>
@param	props A list of attributes that change, such as<br>
@param	duration Time spent, in milliseconds.<br>
@param	ease Jog type, default is uniform motion. Default value=null<br>
@param	complete End the callback function. Default value=null<br>
@param	delay Delay execution time. Default value=0<br>
@param	coverBefore Indicates if the previous jogging is overwritten. Default value=0<br>
@return	Returns the Tween object.



## complete
###### **[complete](#complete)**(): void :
Immediately end the jog and get to the end.



## pause
###### **[pause](#pause)**(): void :
Pause the jogging and you can restart it by resume or restart.



## setStartTime
###### **[setStartTime](#setStartTime)**(startTime : number): void :
Set the start time.<br>
@param	startTime Start time. 


## clearAll
###### **[clearAll](#clearAll)**(target : any): void :
[Static] Clear all the jogs on the specified target object.<br>
@param	target Target audience.



## clear
###### **[clear](#clear)**(tween : [Tween](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/033-Tween)): void :
[Static] Clean up a certain slow motion.<br>
@param	tween Slow moving objects.



## clear
###### **[clear](#clear)**(): void :
Stops and clears the current jog.



## restart
###### **[restart](#restart)**(): void :
Restart the suspended slow motion.



## resume
###### **[resume](#resume)**(): void :
Resume suspended jogging.





