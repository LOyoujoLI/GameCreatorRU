# UISwitch Switch Components
>A checkbox component used to bind the player switch, when the player switch is on, the component is checked, and vice versa in the unchecked state<br>Related events:<br>&nbsp;EventObject.LOADED Event when loading is complete<br>[Variable System] will automatically register a request to synchronize the display of server player variables when displayed<br>Usage:<br>var a = new UISwitch();<br>a.image1 = "asset/image/picture/control/check_unselected.png";<br>a.image2 = "asset/image/picture/control/check_selected.png";<br>a.width = 100;<br>a.height = 100;<br>a.switchID = "5"; // Bind 5 player switch<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-04-14

**Inheritance**  →[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **switchID** : number;<br>Specify the bound player switch ID  |
| **image1** : string;<br>Unchecked effect picture  |
| **image2** : string;<br>Effect picture when selected Default Value="asset/image/picture/control/check_selected.png"  |
| **[grid9img1](#grid9img1)** : string;<br>Nine grid settings for unselected images: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)  |
| **[grid9img2](#grid9img2)** : string;<br>Nine grid settings of the selected state picture: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |



## Details

### grid9img1
###### grid9img1 : string;
Nine grid settings for unselected images: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### grid9img2
###### grid9img2 : string;
Nine grid settings for the selected state picture: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"




