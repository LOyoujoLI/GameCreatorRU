# SceneObjectEntity Scene object entity class
>All actual scene object entities inherit from such<br>Possession of characteristics:<br>-- Object switches (the system automatically records object switches for all scenes when archiving, and can also affect emergence conditions)<br>-- Adding object behaviors (for details, refer to:[SceneObjectBehaviors](?file=006-API-2D单机内核/001-通用/025-SceneObjectBehaviors)）<br>-- Carry custom events: such as RPG templates may have click events, touch events a variety of trigger events<br>-- Status page: The status of the page that appears is determined by meeting the appearance conditions<br>-- Scene object module: multiple modules can be installed and have the characteristics of the module after installation<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-02-22

**Inheritance**  →[SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_BEFORE_CHANGE_STATUS_PAGE](#EVENT_BEFORE_CHANGE_STATUS_PAGE)** : string;<br>[Static] event: This event is not dispatched when first created before switching state pages. Dispatching object SceneObjectEntity is generally used to listen to all scene objects globally for switching status page events.  |
| **[EVENT_BEFORE_CHANGE_STATUS_PAGE_FOR_INSTANCE](#EVENT_BEFORE_CHANGE_STATUS_PAGE_FOR_INSTANCE)** : string;<br>[Static] Event: This event is not dispatched when it is first created before switching the status page. Dispatching object [Object SceneObjectEntity] is generally used to listen to the switch status page event for an object.  |
| **[EVENT_CHANGE_STATUS_PAGE](#EVENT_CHANGE_STATUS_PAGE)** : string;<br>[Static] event: When the state page is switched, the event is not dispatched when it is created for the first time. Dispatching object SceneObjectEntity is generally used to listen to all scene objects globally for switching status page events.  |
| **[EVENT_CHANGE_STATUS_PAGE_FOR_INSTANCE](#EVENT_CHANGE_STATUS_PAGE_FOR_INSTANCE)** : string;<br>[Static] Event: When the state page is switched, the event is not dispatched when it is created for the first time. Dispatching object [Object SceneObjectEntity] is generally used to listen to the switch status page event for an object.  |
| **[EVENT_ON_ADD_MODULE](#EVENT_ON_ADD_MODULE)** : string;<br>[Static] Event: When attaching a module Dispatch object=SceneObjectEntity  |
| **[EVENT_ON_REMOVE_MODULE](#EVENT_ON_REMOVE_MODULE)** : string;<br>[Static] Event: When removing the module Dispatch object =SceneObjectEntity onRemoveModule(soe:SceneObjectEntity,soModule:SceneObjectModule)  |
| **isDisposed** : boolean;<br>Released or not  |
| **isCopy** : boolean;<br>[Read Only] Whether copy  |
| **inScene** : boolean;<br>On or off scene Default=false  |
| **currentStatusPageIndex** : number;<br>Index of the current corresponding status page 0~N  |
| **triggerLines** : any;<br>Event trigger line: all triggers { [triggerLineID: number]: CommandTrigger }  |
| **customCommandPages** : CommandPage[];<br>Scene object event page Subscript=indexType 0~n  |
| **[moduleLength](#moduleLength)** : number;<br>[Read-only] Get the number of all modules  |
## **Protected Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **behaviors** : SceneObjectBehaviors[];<br>Behavior sets, consisting of a combination of multiple behaviors  |
## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getSwitch](#getSwitch)**(varID : number): number<br>Get the switch of the object
| **[setSwitch](#setSwitch)**(varID : number,  value : number): void<br>Set the switch of the object: when archiving the system will automatically record the object switch data of all objects in the whole scene, and at the same time can affect the emergence conditions.
| **[installSwitchs](#installSwitchs)**(switchs : number[]): void<br>Installation switch, generally used to read data and then write at once
| **[getCustomAttrs](#getCustomAttrs)**(): string[]<br>Get a custom set of property names
| **[addBehavior](#addBehavior)**(behaviorData : any[],  loop : boolean,  targetSceneObject : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  onOver : Callback,  cover : boolean,  startIndex? : number,  Immediate? : boolean,  forceStopLastBehavior? : boolean,  delayFrame? : number,  executor? : [SceneObjectEntity](?file=006-API-2D单机内核/001-通用/026-SceneObjectEntity)): [SceneObjectBehaviors](?file=006-API-2D单机内核/001-通用/025-SceneObjectBehaviors)<br>Add a set of behaviors
| **[clearBehaviors](#clearBehaviors)**(): void<br>Clean up the behavior group, after cleaning up the object does not have any behavior set
| **[getCommandTrigger](#getCommandTrigger)**(mainType : number,  indexType : number,  scene : [Scene](?file=006-API-2D单机内核/001-通用/023-Scene),  executor : [SceneObjectEntity](?file=006-API-2D单机内核/001-通用/026-SceneObjectEntity)): [CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger)<br>Get event triggers: single-line events get a unique trigger, while multi-line events generate new triggers
| **[addModule](#addModule)**(soModule : SceneObjectModule,  sendEvent? : boolean): boolean<br>Add Module
| **[addModuleAt](#addModuleAt)**(soModule : SceneObjectModule,  index : number,  sendEvent? : boolean): boolean<br>Add module - to the specified location
| **[addModuleByID](#addModuleByID)**(moduleID : number,  sendEvent? : boolean): SceneObjectModule<br>Adding modules - by module number
| **[addModuleByIDAt](#addModuleByIDAt)**(moduleID : number,  index : number,  sendEvent? : boolean): SceneObjectModule<br>Add a module - to the specified location - according to the module number
| **[removeAllModules](#removeAllModules)**(isDispose? : boolean,  sendEvent? : boolean): void<br>Remove all modules
| **[removeModuleByID](#removeModuleByID)**(moduleID : number,  isDispose? : boolean,  sendEvent? : boolean): SceneObjectModule<br>Remove the specified number of modules
| **[removeModule](#removeModule)**(soModule : SceneObjectModule,  isDispose? : boolean,  sendEvent? : boolean): boolean<br>Remove modules - according to the modules they own
| **[removeModuleAt](#removeModuleAt)**(index : number,  isDispose? : boolean,  sendEvent? : boolean): boolean<br>Remove module - according to the specified location
| **[setModuleIndex](#setModuleIndex)**(soModule : SceneObjectModule,  toIndex : number): boolean<br>Set the owned modules to the specified location
| **[setModuleIndexByID](#setModuleIndexByID)**(moduleID : number,  toIndex : number): boolean<br>Set the owned modules to the specified location - according to the module number
| **[setModuleIndexByIndex](#setModuleIndexByIndex)**(fromIndex : number,  toIndex : number): boolean<br>Adjustment of module position
| **[getModule](#getModule)**(moduleID : number): SceneObjectModule<br>Get owned modules - by module number
| **[getModuleByName](#getModuleByName)**(moduleName : string): SceneObjectModule<br>Get owned modules - by module name
| **[getModuleAt](#getModuleAt)**(index : number): SceneObjectModule<br>Get owned modules - based on module location
| **[getModuleIndex](#getModuleIndex)**(soModule : SceneObjectModule): number<br>Get the location of the owned modules
| **[getModuleIndexByID](#getModuleIndexByID)**(moduleID : number): number<br>Get the location of owned modules - based on the module number

## Details

### EVENT_BEFORE_CHANGE_STATUS_PAGE
###### EVENT_BEFORE_CHANGE_STATUS_PAGE : string;
[Static] event: When switching status page before the first time to create the event is not dispatched. Dispatching object SceneObjectEntity is generally used to listen to all scene objects globally for switching status page events.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Currently only available on the server side<br>
>// When listening to status page changes<br>
>EventUtils.addEventListenerFunction(SceneObjectEntity, SceneObjectEntity.EVENT_BEFORE_CHANGE_STATUS_PAGE, (soe: SceneObjectEntity) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### EVENT_BEFORE_CHANGE_STATUS_PAGE_FOR_INSTANCE
###### EVENT_BEFORE_CHANGE_STATUS_PAGE_FOR_INSTANCE : string;
[Static] Event: This event is not dispatched when it is first created before switching the status page. Dispatching object [Object SceneObjectEntity] is generally used to listen to the switch status page event for an object.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Currently only available on the server side<br>
>// When listening to status page changes<br>
>EventUtils.addEventListenerFunction(soe, SceneObjectEntity.EVENT_BEFORE_CHANGE_STATUS_PAGE_FOR_INSTANCE, (soe: SceneObjectEntity) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### EVENT_CHANGE_STATUS_PAGE
###### EVENT_CHANGE_STATUS_PAGE : string;
[Static] event: When the state page is switched, the event is not dispatched when it is created for the first time. Dispatching object SceneObjectEntity is generally used to listen to all scene objects globally for switching status page events.<br>
>// When listening to status page changes<br>
>EventUtils.addEventListenerFunction(SceneObjectEntity, SceneObjectEntity.EVENT_CHANGE_STATUS_PAGE, (soe: SceneObjectEntity) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### EVENT_CHANGE_STATUS_PAGE_FOR_INSTANCE
###### EVENT_CHANGE_STATUS_PAGE_FOR_INSTANCE : string;
[Static] Event: When the state page is switched, the event is not dispatched when it is created for the first time. Dispatching object [Object SceneObjectEntity] is generally used to listen to the switch status page event for an object.<br>
>// When listening to status page changes<br>
>EventUtils.addEventListenerFunction(soe, SceneObjectEntity.EVENT_CHANGE_STATUS_PAGE_FOR_INSTANCE, (soe: SceneObjectEntity) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### EVENT_ON_ADD_MODULE
###### EVENT_ON_ADD_MODULE : string;
[Static] Event: When attaching a module Dispatch object=SceneObjectEntity<br>
>// Listening for events when players add modules<br>
>EventUtils.addEventListenerFunction(SceneObjectEntity, SceneObjectEntity.EVENT_ON_ADD_MODULE, (soe:SceneObjectEntity,soModule:SceneObjectModule) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### EVENT_ON_REMOVE_MODULE
###### EVENT_ON_REMOVE_MODULE : string;
[Static] Event: When removing a module Dispatch object=SceneObjectEntity onRemoveModule(soe:SceneObjectEntity,soModule:SceneObjectModule)<br>
>// Listening for events when a player removes a module<br>
>EventUtils.addEventListenerFunction(SceneObjectEntity, SceneObjectEntity.EVENT_ON_REMOVE_MODULE, (soe:SceneObjectEntity,soModule:SceneObjectModule) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>}, this);<br>
>


### moduleLength
###### moduleLength : number;
[read-only] Get the number of all modules<br> 
@return [number] Number of modules


## getSwitch
###### **[getSwitch](#getSwitch)**(varID : number): number :
Get the switch of the object
##### Parameters
	varID Object switch number 0-N

##### Return
[number]

## setSwitch
###### **[setSwitch](#setSwitch)**(varID : number,  value : number): void :
Set the switch of the object: when archiving the system will automatically record the object switch data of all objects in the whole scene, and at the same time can affect the emergence conditions.
##### Parameters
	varID Object switch number 0-N
	value Switch value 0/1



## installSwitchs
###### **[installSwitchs](#installSwitchs)**(switchs : number[]): void :
Installation switch, generally used to read data and then write at once



## getCustomAttrs
###### **[getCustomAttrs](#getCustomAttrs)**(): string[] :
Get a custom set of property names

##### Return
[string]

## addBehavior
###### **[addBehavior](#addBehavior)**(behaviorData : any[],  loop : boolean,  targetSceneObject : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  onOver : Callback,  cover : boolean,  startIndex? : number,  Immediate? : boolean,  forceStopLastBehavior? : boolean,  delayFrame? : number,  executor? : [SceneObjectEntity](?file=006-API-2D单机内核/001-通用/026-SceneObjectEntity)): [SceneObjectBehaviors](?file=006-API-2D单机内核/001-通用/025-SceneObjectBehaviors) :
Add a set of behaviors
##### Parameters
	behaviorData Behavior data [[Behavior1-ID,Parameter1,Parameter2],[Behavior2-ID,Parameter1,Parameter2],....]
	loop Whether circular
	targetSceneObject Target audience for reference
	onOver Callback when the behavior ends
	cover Covering old behavior
	startIndex [Optional] Default=0 The index of the act group's start play, default 0, means play from the very beginning
	Immediate [Optional] Default=true whether to refresh immediately, otherwise it will wait for the next frame before refreshing
	forceStopLastBehavior [Optional] Default=false Whether to force a behavior being executed to stop, implemented by the project layer so that the current behavior group can be executed immediately
	delayFrame [Optional] Default = 0 Number of frames to wait for within the behavior
	executor [optional] default=null Execution eventer (also behavior dispatcher)

##### Return
Object behavior processor

## clearBehaviors
###### **[clearBehaviors](#clearBehaviors)**(): void :
Clean up the behavior group, after cleaning up the object does not have any behavior set



## getCommandTrigger
###### **[getCommandTrigger](#getCommandTrigger)**(mainType : number,  indexType : number,  scene : [Scene](?file=006-API-2D单机内核/001-通用/023-Scene),  executor : [SceneObjectEntity](?file=006-API-2D单机内核/001-通用/026-SceneObjectEntity)): [CommandTrigger](?file=006-API-2D单机内核/001-通用/014-CommandTrigger) :
Get event triggers: single-line events get a unique trigger, while multi-line events generate new triggers<br>
The same trigger represents a line of execution, so a new generation of triggers for multi-line events represents an event page that can be executed multiple times at the same time
##### Parameters
	mainType 0-Scene-related event categories 1-Scene-object-related event categories 2-Interface-related event categories 3-Event library event categories 4-Segment event event categories (corresponds to CommandTrigger.COMMAND_MAIN_TYPE_XXX)
	indexType Corresponding subcategory 0-N e.g. this is a custom trigger type event for a scene object - "click event"
	scene Scenes
	executor Executor: The executor of the current event

##### Return
Event Triggers

## addModule
###### **[addModule](#addModule)**(soModule : SceneObjectModule,  sendEvent? : boolean): boolean :
Add Module
##### Parameters
	soModule Modules
	sendEvent [Optional] Default=true Whether to add successfully

##### Return
[boolean] Whether to add successfully

## addModuleAt
###### **[addModuleAt](#addModuleAt)**(soModule : SceneObjectModule,  index : number,  sendEvent? : boolean): boolean :
Add module - to the specified location
##### Parameters
	soModule Modules
	index Specified location
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[boolean] Whether to add successfully

## addModuleByID
###### **[addModuleByID](#addModuleByID)**(moduleID : number,  sendEvent? : boolean): SceneObjectModule :
Adding modules - by module number<br>
-- Properties of the module are default values
##### Parameters
	moduleID Module Number
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[SceneObjectModule] The module being added, or null if unsuccessful

## addModuleByIDAt
###### **[addModuleByIDAt](#addModuleByIDAt)**(moduleID : number,  index : number,  sendEvent? : boolean): SceneObjectModule :
Add a module - to the specified location - according to the module number
##### Parameters
	moduleID Module Number
	index Specified location
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[SceneObjectModule] The module being added, or null if unsuccessful

## removeAllModules
###### **[removeAllModules](#removeAllModules)**(isDispose? : boolean,  sendEvent? : boolean): void :
Remove all modules
##### Parameters
	isDispose [Optional] Default=true Whether to destroy the module
	sendEvent [Optional] Default = true Whether to dispatch the event



## removeModuleByID
###### **[removeModuleByID](#removeModuleByID)**(moduleID : number,  isDispose? : boolean,  sendEvent? : boolean): SceneObjectModule :
Remove the specified number of modules
##### Parameters
	moduleID Module number
	isDispose [Optional] Default=true Whether to destroy the module
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[SceneObjectModule] The removed module, or null if unsuccessful

## removeModule
###### **[removeModule](#removeModule)**(soModule : SceneObjectModule,  isDispose? : boolean,  sendEvent? : boolean): boolean :
Remove modules - according to the modules they own
##### Parameters
	soModule Owned modules
	isDispose [Optional] Default=true Whether to destroy the module
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[boolean] Whether the removal is successful

## removeModuleAt
###### **[removeModuleAt](#removeModuleAt)**(index : number,  isDispose? : boolean,  sendEvent? : boolean): boolean :
Remove module - according to the specified location
##### Parameters
	index Specified location
	isDispose [Optional] Default=true Whether to destroy
	sendEvent [Optional] Default = true Whether to dispatch the event

##### Return
[boolean] Whether the removal is successful

## setModuleIndex
###### **[setModuleIndex](#setModuleIndex)**(soModule : SceneObjectModule,  toIndex : number): boolean :
Set the owned modules to the specified location
##### Parameters
	soModule Owned modules
	toIndex Set to arrive at the specified location

##### Return
[boolean] Is it successful

## setModuleIndexByID
###### **[setModuleIndexByID](#setModuleIndexByID)**(moduleID : number,  toIndex : number): boolean :
Set the owned modules to the specified location - according to the module number
##### Parameters
	moduleID The number of the owned module
	toIndex Set to arrive at the specified location

##### Return
[boolean] Is it successful

## setModuleIndexByIndex
###### **[setModuleIndexByIndex](#setModuleIndexByIndex)**(fromIndex : number,  toIndex : number): boolean :
Adjustment of module position
##### Parameters
	fromIndex Original position of the module
	toIndex New location of the module

##### Return
[boolean] Is it successful

## getModule
###### **[getModule](#getModule)**(moduleID : number): SceneObjectModule :
Get owned modules - by module number
##### Parameters
	moduleID Module Number

##### Return
[SceneObjectModule] Returns the module owned, or null if it is not owned

## getModuleByName
###### **[getModuleByName](#getModuleByName)**(moduleName : string): SceneObjectModule :
Get owned modules - by module name
##### Parameters
	moduleName Module Name

##### Return
[SceneObjectModule] Returns the module owned, or null if it is not owned

## getModuleAt
###### **[getModuleAt](#getModuleAt)**(index : number): SceneObjectModule :
Get owned modules - based on module location
##### Parameters
	index Module Location

##### Return
[SceneObjectModule] Returns the module owned, or null if it is not owned

## getModuleIndex
###### **[getModuleIndex](#getModuleIndex)**(soModule : SceneObjectModule): number :
Get the location of owned modules
##### Parameters
	soModule Modules

##### Return
[number] The location of the owned module, or -1 if not owned

## getModuleIndexByID
###### **[getModuleIndexByID](#getModuleIndexByID)**(moduleID : number): number :
Get the location of owned modules - based on the module number
##### Parameters
	moduleID Module Number

##### Return
[number] The location of the owned module, or -1 if not owned



