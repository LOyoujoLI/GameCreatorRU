# UITabBox Tab bar component
>A component for displaying the tab bar, supporting both horizontally aligned tabs and vertically aligned tabs<br>How to use in the editor: If there are N labels in the label component, then the subobjects of the component can be placed 3 to automatically switch the display<br>Related events:<br>&nbsp;EventObject.CHANGE Dispatch when changing state<br>&nbsp;EventObject.LOADED Event when loading is complete<br>Usage:<br>var a = new UITabBox();<br>a.itemWidth = 100;<br>a.itemHeight = 20;<br>a.itemImage1 = "asset/image/picture/control/tab_unselected.png";<br>a.itemImage2 = "asset/image/picture/control/tab_selected.png";<br>a.items = "Label 1,Label 2,Label 3,Label 4";<br>stage.addChild(a);<br>// Add two images, corresponding to two tags each<br>var img1 = new UIBitmap;<br>img1.image = "asset/image/image1.png";<br>a.addChild(img1);<br>img1.y = 20;<br>var img2 = new UIBitmap;<br>img2.image = "asset/image/image2.png";<br>a.addChild(img2);<br>img2.y = 20;<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-04-14

**Inheritance**  →[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **selectedIndex** : number;<br>Checked items Default = -1  |
| **items** : string;<br>Tag items Comma separated  |
| **length** : number;<br>[Read only] Total number of items  |
| **itemImage1** : string;<br>Image style when tab item is selected  |
| **itemImage2** : string;<br>Image style when tag items are moved in  |
| **rowMode** : boolean;<br>Aligned as row mode Default=false  |
| **itemWidth** : number;<br>Tag item length Default = 177  |
| **itemHeight** : number;<br>Label item height Default=71  |
| **spacing** : number;<br>Label item spacing Default=5  |
| **labelDx** : number;<br>Label Horizontal Offset Default = 0  |
| **labelDy** : number;<br>Label Vertical Offset Default = 0  |
| **labelSelectedColor** : string;<br>Text color Default="#FFFFFF" when tag item is selected  |
| **labelColor** : string;<br>Text color Default="#666666" when label item is unchecked  |
| **labelSize** : number;<br>Text font size Default=16  |
| **labelFont** : string;<br>Text font, the default is the preset default font  |
| **labelAlign** : number;<br>Text font alignment mode 0-Left 1-Center 2-Right Default=1  |
| **labelBold** : boolean;<br>Text font bold mode Default=false  |
| **labelItalic** : boolean;<br>Italics Default=false  |
| **smooth** : boolean;<br>Smoothing Default=false  |
| **[grid9img1](#grid9img1)** : string;<br>Nine grid settings for images when tab items are selected: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)  |
| **[grid9img2](#grid9img2)** : string;<br>Nine grid settings for images when tab items are moved in: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setSelectedForce](#setSelectedForce)**(v : number): void<br>Set the selected item without dispatching the EventObject.

## Details

### grid9img1
###### grid9img1 : string;
Nine grid settings for images when tab items are selected: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### grid9img2
###### grid9img2 : string;
Nine grid settings for images when tab items are moved in: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"


## setSelectedForce
###### **[setSelectedForce](#setSelectedForce)**(v : number): void :
Set the selected item without dispatching the EventObject.CHANGE





