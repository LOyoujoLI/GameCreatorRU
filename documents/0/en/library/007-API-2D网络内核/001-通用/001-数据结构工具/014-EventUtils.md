# EventUtils General Event Manager
>The difference with the client-side EventDispatcher is that it can support arbitrary object dispatching and receiving events<br>However, it should be noted that when destroying the object, you need to call EventUtils.clear();，Otherwise the event manager is used<br>Objects registered for events are permanently recorded here, leading to memory leaks (i.e. useless resources keep piling up leading to high memory usage).<br>General rule: the general format EVENT__????? EventUtils are used for all events, such as CommandTrigger.<br>Usage 1:<br>&nbsp;EventUtils.addEventListener(obj,XXX.EVENT_XXX,Callback.New((Parameter1,Parameter2)=>{<br>&nbsp;&nbsp;&nbsp;// Logic<br>&nbsp;},this));<br>Usage 2:<br>&nbsp;EventUtils.addEventListenerFunction(obj,XXX.EVENT_XXX,(Parameter1,Parameter2)=>{<br>&nbsp;&nbsp;&nbsp;// Logic<br>&nbsp;},this);<br>&nbsp;// When a condition is met somewhere then: (where parameters can be passed custom)<br>&nbsp;EventUtils.happen(obj,XXX.EVENT_XXX,[Parameter1,Parameter2]);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-08-22

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[addEventListener](#addEventListener)**(obj : any,  type : string,  callBack : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback),  isOnce? : boolean): void<br>[Static] Registration Event
| **[addEventListenerFunction](#addEventListenerFunction)**(obj : any,  type : string,  onHappen : Function,  thisPtr : any,  args? : any[],  isOnce? : boolean): void<br>[Static] Registering Events - Functions and Scopes Edition
| **[removeEventListener](#removeEventListener)**(obj : any,  type : string,  callBack : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void<br>[Static] Remove event
| **[removeEventListenerFunction](#removeEventListenerFunction)**(obj : any,  type : string,  onHappen : Function,  thisPtr : any): void<br>[Static] Removing Events - Functions and Scopes Edition
| **[happen](#happen)**(obj : any,  type : string,  args? : any[]): void<br>[static] dispatch event, if there are parameters when registering, the parameters take precedence over the registered parameters, and then append the parameter args dispatched here
| **[clear](#clear)**(obj : any,  type? : string): void<br>[Static] Clear Event

## Detailss



## addEventListener
###### **[addEventListener](#addEventListener)**(obj : any,  type : string,  callBack : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback),  isOnce? : boolean): void :
[Static] Registration Event
##### Parameters
	obj Event Object
	type Type
	callBack Callback
	isOnce [Optional] Default=false Whether to execute once Default false



## addEventListenerFunction
###### **[addEventListenerFunction](#addEventListenerFunction)**(obj : any,  type : string,  onHappen : Function,  thisPtr : any,  args? : any[],  isOnce? : boolean): void :
[Static] Registering Events - Functions and Scopes Edition
##### Parameters
	obj Event Object
	type Type
	onHappen Callback Methods
	thisPtr Callback time scope
	args [Optional] Default=null Callback time parameter
	isOnce [Optional] Default=false Whether to execute once



## removeEventListener
###### **[removeEventListener](#removeEventListener)**(obj : any,  type : string,  callBack : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void :
[Static] Remove event
##### Parameters
	obj Event Object
	type Type
	callBack Callback



## removeEventListenerFunction
###### **[removeEventListenerFunction](#removeEventListenerFunction)**(obj : any,  type : string,  onHappen : Function,  thisPtr : any): void :
[Static] Removing Events - Functions and Scopes Edition
##### Parameters
	obj Event Object
	type Type
	onHappen Callback Methods
	thisPtr Callback time scope



## happen
###### **[happen](#happen)**(obj : any,  type : string,  args? : any[]): void :
[static] dispatch event, if there are parameters when registering, the parameters take precedence over the registered parameters, and then append the parameter args dispatched here
##### Parameters
	obj Event Object
	type Type
	args [optional] default=null Custom parameters that can appear in function callbacks when passed



## clear
###### **[clear](#clear)**(obj : any,  type? : string): void :
[Static] Clear Event
##### Parameters
	obj Event Object
	type [optional] default=null type, if null means all





