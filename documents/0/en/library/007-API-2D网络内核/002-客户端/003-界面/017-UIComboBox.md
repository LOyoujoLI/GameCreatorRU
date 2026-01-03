# UIComboBox Drop down box component
>A drop-down box is a component that, when clicked, brings up a set of options and allows one to be selected<br>Related events:<br>&nbsp;EventObject.CHANGE Dispatch when changing state<br>&nbsp;EventObject.LOADED Event when loading is complete<br>&nbsp;UIComboBox.OPEN Dispatched when the dropdown box is opened<br>&nbsp;UIComboBox.CLOSE Dispatch when dropdown box is closed<br>Usage:<br>var a = new UIComboBox();<br>a.bgSkin = "asset/image/picture/control/tab_selected.png";<br>a.itemLabels = "1,2,3,4,5"<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br>a.on(EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-11-11

**Inheritance**  →[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **OPEN** : string;<br>[Static] Event: Dispatch event when the drop-down box is opened  |
| **CLOSE** : string;<br>[Static] Event: Dispatch event when the drop-down box is closed  |
| **isComboBoxOpen** : boolean;<br>Whether to open in  |
| **bgSkin** : string;<br>Path to the background image of the display box  |
| **[bgGrid9](#bgGrid9)** : string;<br>The background image of the display box nine-box setting Default value="0,0,0,0,0"  |
| **align** : number;<br>Text Horizontal Alignment 0-Left 1-Center 2-Right Default=1  |
| **valign** : number;<br>Text Vertical Alignment 0 - Top 1 - Center 2 - Bottom Default = 1  |
| **bold** : boolean;<br>Whether the text is bold or not Default=false  |
| **italic** : boolean;<br>Italics Default=false  |
| **smooth** : boolean;<br>Smoothing Default=false  |
| **font** : string;<br>Text font, the default value is the preset default font  |
| **color** : string;<br>Text color Default="#FFFFFF"  |
| **fontSize** : number;<br>Text Font Size Default = 16  |
| **textDx** : number;<br>Text Horizontal Offset Default = 0  |
| **textDy** : number;<br>Text Vertical Offset Default = 0  |
| **selectedIndex** : number;<br>Current selected item Default=0  |
| **itemLabels** : string;<br>The set of text options in the drop-down list, format: 1,2,3,4,5 means 5 options  |
| **itemHeight** : number;<br>Height of the unit option in the drop-down list Default = 20  |
| **displayItemSize** : number;<br>Maximum number of options to be displayed simultaneously in the drop-down list Default = 5  |
| **listScrollBg** : string;<br>Path to the scrollbar background image in the dropdown list Default="asset/image/picture/UI/uicomboboxbg.png"  |
| **listScrollBar** : string;<br>Scrolling axis background image path in the dropdown list Default="asset/image/picture/UI/uicomboboxslider.png"  |
| **listBgColor** : string;<br>Background color of the drop-down list Default value="#FFFFFF"  |
| **itemAlign** : number;<br>Horizontal alignment of the text in the drop-down list 0-Left 1-Center 2-Right Default=0  |
| **itemValign** : number;<br>Vertical horizontal alignment of the drop-down list 0-centered 1-centered 2-centered Default=1  |
| **itemBold** : boolean;<br>Whether the text of the drop-down list is bold or not Default=false  |
| **itemFont** : string;<br>The text font of the drop-down list, the default value is the preset default font  |
| **itemColor** : string;<br>Text color of the dropdown list Default="#000000"  |
| **itemOverColor** : string;<br>Text color when selected for the dropdown list Default="#FFFFFF"  |
| **itemOverBgColor** : string;<br>Background text color for dropdown list when selected Default="#000000"  |
| **itemFontSize** : number;<br>Text font size of the drop-down list Default = 12  |
| **itemTextDx** : number;<br>Horizontal offset of the text in the drop-down list Default = 0  |
| **itemTextDy** : number;<br>Vertical offset of the text in the drop-down list Default = 0  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setSelectedForce](#setSelectedForce)**(V : number): void<br>Currently selected item, not dispatched EventObject.CHANGE Events

## Details

### bgGrid9
###### bgGrid9 : string;
The background image of the display box nine-box setting default value = "0,0,0,0,0"<br>
Nine grid settings: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Instead of simply stretching the material, make it stretch according to a nine-box grid


## setSelectedForce
###### **[setSelectedForce](#setSelectedForce)**(V : number): void :
Currently selected item, not dispatched EventObject.CHANGE Events
##### 参数
	v Selected item value





