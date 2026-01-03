# UICheckBox Checkbox component
>A checkbox is a basic control that has a checked or unchecked state<br>Related events:<br>&nbsp;EventObject.CHANGE Dispatch when selected changes state<br>&nbsp;EventObject.LOADED Event when loading is complete<br>Usage:<br>var a = new UICheckBox();<br>a.image1 = "asset/image/picture/control/check_unselected.png";<br>a.image2 = "asset/image/picture/control/check_selected.png";<br>a.width  = 100;<br>a.height = 100;<br>a.selected = true;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br>a.on(EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-04-14

**Inheritance**  →[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **selected** : boolean;<br>Change selected state Default=false  |
| **image1** : string;<br>The path to the effect image is not selected, i.e. when selected=false  |
| **image2** : string;<br>Effect image path when selected i.e. when selected=true  |
| **[grid9img1](#grid9img1)** : string;<br>Nine grid settings for unselected images: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)  |
| **[grid9img2](#grid9img2)** : string;<br>Nine grid settings of the selected state picture: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setSelectedForce](#setSelectedForce)**(v : boolean): void<br>Change selected status, no dispatch EventObject.CHANGE Events

## Details

### grid9img1
###### grid9img1 : string;
Nine grid settings for unselected images: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Instead of simply stretching the clip, make it stretch according to the nine-pattern approach Default="0,0,0,0,0"
### grid9img2
###### grid9img2 : string;
Nine grid settings for the selected state picture: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Instead of simply stretching the clip, make it stretch according to the nine-pattern approach Default="0,0,0,0,0"


## setSelectedForce
###### **[setSelectedForce](#setSelectedForce)**(v : boolean): void :
Change selected status, no dispatch EventObject.CHANGE Events
##### Parameters
	v Check or not





