# GameUI Interface Manager
>Characteristics:<br>&nbsp;&nbsp;-- There is only one interface created through the system with the same number<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example, if you create interface #1 by GameUI.show(1), the second call will still be this interface<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The interface opened by event visualization is the same as GameUI.show<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If you need to create multiple identical interfaces, you can use GameUI.load(1,true); which means create 1 as a clone<br>Only one interface with the same ID exists, if you need to create an additional interface you can new GUI_XXX<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_OPEN_SYSTEM_UI](#EVENT_OPEN_SYSTEM_UI)** : string;<br>[static] event: event dispatched when the system group interface is opened onOpenUI(uiID:number) uiID=interface number  |
| **[EVENT_CLOSE_SYSTEM_UI](#EVENT_CLOSE_SYSTEM_UI)** : string;<br>[Static] event: event dispatched when closing the system group interface onCloseUI(uiID:number)  |
| **[EVENT_CREATE_UI](#EVENT_CREATE_UI)** : string;<br>[Static] Events: Events dispatched when an interface is created, regardless of whether the interface is created as a system group or as a copy  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[isOpened](#isOpened)**(uiID : number): boolean<br>[static]Is open
| **[load](#load)**(id : number,  copy? : boolean): GUI_BASE<br>[Static] Loading screen
| **[getAllSystemGroupUIs](#getAllSystemGroupUIs)**(): any<br>[Static] Get the existing system group interface (including the previously opened and closed, if released, it is no longer in the list)
| **[get](#get)**(id : number): GUI_BASE<br>[Static] Get the interface of the specified number in the system group list, if the system group has not opened the interface, then get to null
| **[dispose](#dispose)**(id : number): void<br>[Static] Release the interface of the specified number in the system group list
| **[show](#show)**(id : number): GUI_BASE<br>Static】Display the interface of the specified number in the system group list, if the interface is not found in the system group list, it will be created and added to the system group list, if it exists, it will return to the interface directly.
| **[hide](#hide)**(id : number): void<br>[Static] Hide the interface of the specified number in the system group list, or ignore it if it is not found in the system group list
| **[hideAll](#hideAll)**(): void<br>[Static] Hide the interface of all system group list
| **[getAllCompChildren](#getAllCompChildren)**(ui : GUI_BASE,  keyValueMode : boolean,  conditionFunc? : Function): any<br>[Static] Get all its child component objects

## Details

### EVENT_OPEN_SYSTEM_UI
###### EVENT_OPEN_SYSTEM_UI : string;
[static] event: event dispatched when the system group interface is opened onOpenUI(uiID:number) uiID=interface number<br>
>&nbsp;EventUtils.addEventListenerFunction(GameUI,GameUI.EVENT_OPEN_SYSTEM_UI,(uiID: number) => {<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;},this);<br>
>


### EVENT_CLOSE_SYSTEM_UI
###### EVENT_CLOSE_SYSTEM_UI : string;
[Static] event: event dispatched when closing the system group interface onCloseUI(uiID:number)<br>
>&nbsp;EventUtils.addEventListenerFunction(GameUI,GameUI.EVENT_CLOSE_SYSTEM_UI,(uiID: number) => {<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;},this);<br>
>


### EVENT_CREATE_UI
###### EVENT_CREATE_UI : string;
[Static] Events: Events dispatched when an interface is created, regardless of whether the interface is created as a system group or as a copy<br>
>&nbsp;EventUtils.addEventListenerFunction(GameUI,GameUI.EVENT_CREATE_UI,(ui: GUI_BASE)=> {<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>&nbsp;},this);<br>
>




## isOpened
###### **[isOpened](#isOpened)**(uiID : number): boolean :
[Static]Is open
##### Parameters
	uiID System Group Interface ID

##### Return
[boolean]

## load
###### **[load](#load)**(id : number,  copy? : boolean): GUI_BASE :
[Static] Loading screen
##### Parameters
	id Interface ID
	copy [可选] Default=false Whether it is a cloned interface false=Interface belonging to the system group (will be saved in the system group list) true=Interface belonging to the new one created by yourself

##### Return
[GUI_BASE]

## getAllSystemGroupUIs
###### **[getAllSystemGroupUIs](#getAllSystemGroupUIs)**(): any :
[Static] Get the existing system group interface (including the previously opened and closed, if released, it is no longer in the list)

##### Return
{ [uiID: number]: GUI_BASE }

## get
###### **[get](#get)**(id : number): GUI_BASE :
[Static] Get the interface of the specified number in the system group list, if the system group has not opened the interface, then get to null
##### Parameters
	id Interface number

##### Return
This interface for the system group

## dispose
###### **[dispose](#dispose)**(id : number): void :
[Static] Release the interface of the specified number in the system group list
##### Parameters
	id Interface number



## show
###### **[show](#show)**(id : number): GUI_BASE :
[Static] Display the interface of the specified number in the system group list, if the interface is not found in the system group list, it will be created and added to the system group list, if it exists, it will return to the interface directly.
##### Parameters
	id Interface number

##### Return
[GUI_BASE]

## hide
###### **[hide](#hide)**(id : number): void :
[Static] Hide the interface of the specified number in the system group list, or ignore it if it is not found in the system group list
##### Parameters
	id Interface number



## hideAll
###### **[hideAll](#hideAll)**(): void :
[Static] Hide the interface of all system group list



## getAllCompChildren
###### **[getAllCompChildren](#getAllCompChildren)**(ui : GUI_BASE,  keyValueMode : boolean,  conditionFunc? : Function): any :
[Static] Get all its child component objects
##### Parameters
	keyValueMode Whether it contains keyValue format, if it does, the value of keyValue exists in the return value
	conditionFunc [optional] default=null condition method, filter the required components by condition, no method exists or returns true as if the component is required conditionFunc(uiComp:Sprite)

##### Return
{ arr: UIBase[], keyValue: { [compID: string]: UIBase } }



