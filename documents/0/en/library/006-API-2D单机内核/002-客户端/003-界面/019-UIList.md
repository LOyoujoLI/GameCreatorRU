# UIList List Components
>The list component is a component that supports NxM matrix arrangement, and its internal items (items) are implemented by creating another interface source<br>&nbsp;-- Item data base class: UIListItemData (In addition, the system will automatically create each interface as an item data class - ListItem_? please refer to system/UIRuntime.ts)<br>&nbsp;&nbsp;&nbsp;&nbsp;The item data class will automatically create the appropriate property based on the control so that the value or string (and image address, etc.) is automatically rendered when populated<br>&nbsp;&nbsp;&nbsp;&nbsp;Item data mapping value reference.<br>&nbsp;&nbsp;&nbsp;&nbsp;UIBitmap -> string-Image address<br>&nbsp;&nbsp;&nbsp;&nbsp;UIString -> string-Text<br>&nbsp;&nbsp;&nbsp;&nbsp;UIVariable -> number-Numeric variable ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UIAvatar -> number-Avatar ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UIStandAvatar -> number-Standing Avatar ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UIAnimation -> number-Animation ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UIInput -> string-Default Text<br>&nbsp;&nbsp;&nbsp;&nbsp;UICheckBox -> boolean-Checked status<br>&nbsp;&nbsp;&nbsp;&nbsp;UISwitch -> number-Switch ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UITabBox -> string-Index（如aa,bb,cc）<br>&nbsp;&nbsp;&nbsp;&nbsp;UISlider -> number-value<br>&nbsp;&nbsp;&nbsp;&nbsp;UIGUI -> number-Interface ID<br>&nbsp;&nbsp;&nbsp;&nbsp;UIList -> UIListItemData[]-Item data<br>Related events:<br>&nbsp;EventObject.CHANGE Dispatch when changing state  onChange(state:number) state=0 means selectedIndex changed, otherwise it is overIndex<br>&nbsp;EventObject.LOADED Event when loading is complete<br>&nbsp;UIList.OPEN_STATE_CHANGE When the open state is changed<br>&nbsp;UIList.ITEM_CLICK Click on the confirmation item<br>&nbsp;UIList.EVENT_FOCUS_CHANGE [EventUtils Events] Events dispatched when the focus is changed<br>&nbsp;UIList.ITEM_CREATE When creating an item<br>Usage:<br>&nbsp;// Adding data in a list<br>&nbsp;var a = new UIList();<br>&nbsp;a.overImageURL = "asset/image/picture/control/uilistover.png";<br>&nbsp;a.selectImageURL = "asset/image/picture/control/uilistselect.png";<br>&nbsp;a.itemModelGUI = 8; // Use the specified interface ID to create the item, or if you need to specify a class, use the itemModelClass<br>&nbsp;stage.addChild(a);<br>&nbsp;var dArr = [];<br>&nbsp;for(var i=0;i<10;i++){<br>&nbsp;&nbsp;&nbsp;&nbsp;var d:ListItem_8 = new ListItem_8();<br>&nbsp;&nbsp;&nbsp;&nbsp;d.pic = "asset/image/a.jpg"; // Suppose there is a control named pic in interface 8<br>&nbsp;&nbsp;&nbsp;&nbsp;d.txt = "kds"; // Suppose a text named txt exists in interface 8<br>&nbsp;&nbsp;&nbsp;&nbsp;d.Power = 5; // Suppose there is a numeric variable control named Power in screen 8, here bind variable 5<br>&nbsp;&nbsp;&nbsp;&nbsp;dArr.push(d);<br>&nbsp;}<br>&nbsp;a.items = dArr;<br>&nbsp;// Adding data in a tree way: the parent-child node relationship of the data is decided before setting a.items.<br>&nbsp;var child = new ListItem_8();<br>&nbsp;child.pic = "asset/image/a.jpg";<br>&nbsp;child.txt = "kdsChild";<br>&nbsp;child.Power = 5;<br>&nbsp;dArr[2].push(child);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-07-09

**Inheritance**  →UIRoot<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_FOCUS_CHANGE](#EVENT_FOCUS_CHANGE)** : string;<br>[Static] Events: Events dispatched when the focus is changed onFocusChange(lastFocus:UIList,currentFocus:UIList);  |
| **[OPEN_STATE_CHANGE](#OPEN_STATE_CHANGE)** : string;<br>[Static] Event: When the open state is changed onChange(ui,data)  |
| **[ITEM_CLICK](#ITEM_CLICK)** : string;<br>[Static] event: click to confirm the item (when the item has been selected and then click to send the event / or ENTER key)  |
| **[ITEM_CREATE](#ITEM_CREATE)** : string;<br>[Static] Event: When creating an item onItemCreate(ui: UIRoot, data: UIListItemData,index:number)  |
| **KEY_UP** : number[];<br>[Static] Key - Move Up The default shortcut key after enabling keyboard support, support to modify the default value=[Keyboard.UP]  |
| **KEY_DOWN** : number[];<br>[Static] Key - Move Down The default shortcut key after enabling keyboard support, support to modify the default value=[Keyboard.DOWN]  |
| **KEY_LEFT** : number[];<br>[Static] Key - Move Left The default shortcut key after enabling keyboard support, supports modifying the default value=[Keyboard.LEFT]  |
| **KEY_RIGHT** : number[];<br>[Static] Key - Move Right The default shortcut key after enabling keyboard support, supports modifying the default value=[Keyboard.RIGHT]  |
| **KEY_ENTER** : number[];<br>[Static] Key - OK The default shortcut key after enabling keyboard support, support to modify the default value=[Keyboard.ENTER, Keyboard.SPACE]  |
| **KEY_BOARD_ENABLED** : boolean;<br>[Static] Turn on keyboard (handle) support: only the current focus of the UIList can be operated  |
| **[SINGLE_FOCUS_MODE](#SINGLE_FOCUS_MODE)** : boolean;<br>[Static] to open a single focus system (focus on the specified List before you can operate, otherwise the default is the state of inoperable)  |
| **[focus](#focus)** : UIList;<br>[Static] Set List focus:  |
| **overSelectMode** : boolean;<br>Mouse hover is used as a selected effect (default is hover effect) Default Value=false  |
| **onCreateItem** : Callback;<br>Callback when creating ITEM onCreateItem(ui: UIRoot, data: UIListItemData,index:number)  |
| **subitemIndentation** : number;<br>Sub-item indent Default=20  |
| **selectEnable** : boolean;<br>Whether to allow selection Default=true  |
| **repeatX** : number;<br>Number of columns Default value=1  |
| **spaceX** : number;<br>Horizontal spacing Default=2  |
| **spaceY** : number;<br>Redirection interval Default value=20  |
| **itemWidth** : number;<br>Item Width Default=200  |
| **itemHeight** : number;<br>Item Height Default=50  |
| **overImageURL** : string;<br>Picture of the effect when the cursor is hovering  |
| **overImage** : UIBitmap;<br>Object when the cursor is hovering: getting the object is good for adding some extra effect logic of your own  |
| **selectImageURL** : string;<br>The effect picture of the selected item  |
| **selectedImage** : UIBitmap;<br>Effect picture object of the selected item: getting the object is good for appending some additional effect logic yourself  |
| **[overImageGrid9](#overImageGrid9)** : string;<br>The nine-box grid of the effect image when the cursor is above the item Default = "0,0,0,0,0"  |
| **[selectImageGrid9](#selectImageGrid9)** : string;<br>The nine-box grid of the effect picture of the selected item Default="0,0,0,0,0"  |
| **selectedImageAlpha** : number;<br>Transparency of the effect image when the item is selected Default = 0.5  |
| **overImageAlpha** : number;<br>Transparency of the effect image when the cursor is above the item Default = 0.5  |
| **selectedImageOnTop** : boolean;<br>Whether the effect picture is displayed on the upper layer when the item is selected (covers the item) Default=true  |
| **overImageOnTop** : boolean;<br>Effect when the cursor is on top of the item Whether the picture is displayed on the upper level (covering the item) Default = true  |
| **itemModelClass** : any;<br>Class settings for the item  |
| **itemModelGUI** : number;<br>The interface ID corresponding to the item  |
| **items** : UIListItemData[];<br>All item data  |
| **[itemSprites](#itemSprites)** : Sprite[];<br>Get the display object corresponding to all items  |
| **length** : number;<br>[Read only]The total number of data in the list.  |
| **[selectedItem](#selectedItem)** : UIListItemData;<br>Check the item, based on the specified data  |
| **[selectedIndex](#selectedIndex)** : number;<br>Selected items, according to the index (i.e. the location of the data group where they are located, the data group includes hidden tree nodes that are not opened) default value = -1  |
| **overIndex** : number;<br>Hover items, based on index (i.e. the position of the data group where they are located, the data group includes hidden tree nodes that are not opened) Default Value=-1  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setKeyDown](#setKeyDown)**(keyCode : number): void<br>[Static] Simulated key press: Only the UIList with the current focus can be operated
| **[setSelectedIndexForce](#setSelectedIndexForce)**(v : number): void<br>Checked items, according to the index, do not send EventObject.CHANGE events
| **[setOverIndexForce](#setOverIndexForce)**(v : number): void<br>Hover item, based on index, does not dispatch EventObject.CHANGE event
| **[scrollTo](#scrollTo)**(index : number,  ignoreAlreadyInVisible? : boolean,  tween? : boolean,  duration? : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback)): void<br>Scroll to the specified line: ignore scrolling if the object is in full display
| **[replaceItem](#replaceItem)**(itemData : UIListItemData,  index : number): void<br>Replacing the data refreshes the display and triggers the onCreateItem function.
| **[addItem](#addItem)**(itemData : UIListItemData,  index? : number): UIRoot<br>Add data
| **[removeItem](#removeItem)**(itemData : UIListItemData): number<br>Remove Data
| **[removeItemByIndex](#removeItemByIndex)**(index : number): UIListItemData<br>Remove data, based on the specified location
| **[setItemIndex](#setItemIndex)**(itemData : UIListItemData,  toIndex : number): boolean<br>Change Location
| **[setItemIndexByIndex](#setItemIndexByIndex)**(itemIndex : number,  toIndex : number): boolean<br>Change location - depending on where the data is located
| **[getItemUI](#getItemUI)**(index : number): UIRoot<br>Get the display object of the item

## Details

### EVENT_FOCUS_CHANGE
###### EVENT_FOCUS_CHANGE : string;
[Static] Events: Events dispatched when the focus is changed onFocusChange(lastFocus:UIList,currentFocus:UIList);<br>
>// lastFocus - Indicates the last focus list<br>
>// currentFocus - Indicates this focus list<br>
>EventUtils.addEventListenerFunction(UIList,UIList.EVENT_FOCUS_CHANGE,(lastFocus:UIList,currentFocus:UIList)=>{<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### OPEN_STATE_CHANGE
###### OPEN_STATE_CHANGE : string;
[Static] Event: When the open state is changed onChange(ui,data)<br>
>uiList.on(UIList.OPEN_STATE_CHANGE,this,this.onOpenStateChange);<br>
>


### ITEM_CLICK
###### ITEM_CLICK : string;
[Static] event: click to confirm the item (when the item has been selected and then click to send the event / or ENTER key)<br>
>uiList.on(UIList.ITEM_CLICK,this,this.onItemClick);<br>
>


### ITEM_CREATE
###### ITEM_CREATE : string;
[Static] Event: When creating an item onItemCreate(ui: UIRoot, data: UIListItemData,index:number)<br>
>uiList.on(UIList.ITEM_CREATE,this,this.onItemCreate);<br>
>


### SINGLE_FOCUS_MODE
###### SINGLE_FOCUS_MODE : boolean;
[Static] to open a single focus system (focus on the specified List before you can operate, otherwise the default is the state of inoperable)<br>
Activate the specified list for operation by setting UIList.focus
### focus
###### focus : UIList;
[Static] Set List focus:<br>
-- Only keys with focus set are valid<br>
-- If it is a single focus system, only one List is allowed to be enabled at the same time.
### overImageGrid9
###### overImageGrid9 : string;
The nine-box grid of the effect image when the cursor is above the item Default = "0,0,0,0,0"<br>
Nine grid settings: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Instead of simply stretching the material, make it stretch according to a nine-box grid
### selectImageGrid9
###### selectImageGrid9 : string;
The nine-box grid of the effect picture of the selected item Default="0,0,0,0,0"<br>
Nine grid settings: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Instead of simply stretching the material, make it stretch according to a nine-box grid
### itemSprites
###### itemSprites : Sprite[];
Get the display object corresponding to all items<br>
If the item data is updated, the display object will also be replaced with a new one, so please use caution if you need to record the display object.
### selectedItem
###### selectedItem : UIListItemData;
Check the item, based on the specified data<br>
@return [UIListItemData]
### selectedIndex
###### selectedIndex : number;
Selected items, according to the index (i.e. the location of the data group where they are located, the data group includes hidden tree nodes that are not opened) default value = -1<br>
@return [number]


## setKeyDown
###### **[setKeyDown](#setKeyDown)**(keyCode : number): void :
[Static] Simulated key press: Only the UIList with the current focus can be operated
##### Parameters
	keyCode Corresponding keys KEY_UP/KEY_DOWN/KEY_LEFT/KEY_RIGHT/KEY_ENTER



## setSelectedIndexForce
###### **[setSelectedIndexForce](#setSelectedIndexForce)**(v : number): void :
Checked items, according to the index, do not send EventObject.CHANGE events
##### Parameters
	v Selected items



## setOverIndexForce
###### **[setOverIndexForce](#setOverIndexForce)**(v : number): void :
Hover item, based on index, does not dispatch EventObject.CHANGE event
##### Parameters
	v Hover items



## scrollTo
###### **[scrollTo](#scrollTo)**(index : number,  ignoreAlreadyInVisible? : boolean,  tween? : boolean,  duration? : number,  ease? : Function,  complete? : [Callback](?file=006-API-2D单机内核/001-通用/001-数据结构工具/013-Callback)): void :
Scroll to the specified line: ignore scrolling if the object is in full display
##### Parameters
	index Specified Index
	ignoreAlreadyInVisible [Optional] Default=true Ignore the fact that the
	tween [Optional] Default=false Whether to jog
	duration [Optional] Default value = 0 Duration
	ease [Optional] Default=null Jogging method
	complete [Optional] Default=null Callback when jogging is complete



## replaceItem
###### **[replaceItem](#replaceItem)**(itemData : UIListItemData,  index : number): void :
Replacing the data refreshes the display and triggers the onCreateItem function.
##### Parameters
	itemData New Data
	index Index of items to be replaced



## addItem
###### **[addItem](#addItem)**(itemData : UIListItemData,  index? : number): UIRoot :
Add data
##### Parameters
	itemData New Data
	index [Optional] Default = -1 Position of insertion, -1 means insert backward

##### Return
[UIRoot] Data corresponding to the display object

## removeItem
###### **[removeItem](#removeItem)**(itemData : UIListItemData): number :
Remove Data
##### Parameters
	itemData data, or ignore it if it is not in the list

##### Return
[number] Location of the data

## removeItemByIndex
###### **[removeItemByIndex](#removeItemByIndex)**(index : number): UIListItemData :
Remove data, based on the specified location
##### Parameters
	index Specified location

##### Return
[UIListItemData] Data

## setItemIndex
###### **[setItemIndex](#setItemIndex)**(itemData : UIListItemData,  toIndex : number): boolean :
Change Location
##### Parameters
	itemData Data
	toIndex Location to be replaced to

##### Return
[boolean] Whether the replacement is successful

## setItemIndexByIndex
###### **[setItemIndexByIndex](#setItemIndexByIndex)**(itemIndex : number,  toIndex : number): boolean :
Change location - depending on where the data is located
##### Parameters
	itemIndex Location of the data
	toIndex Location to be replaced to

##### Return
[boolean] Whether the replacement is successful

## getItemUI
###### **[getItemUI](#getItemUI)**(index : number): UIRoot :
Get the display object of the item
##### Parameters
	index Index

##### Return
[UIRoot] the display object of the item



