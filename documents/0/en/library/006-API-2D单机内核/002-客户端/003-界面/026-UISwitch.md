# UISwitch Switch Components
<br>A checkbox component used to bind a player switch, which is in the checked state when the player switch is on, and vice versa<br>Related events:<br>&nbsp;EventObject.LOADED Event when loading is complete<br>[Variable system] will display the switch variables in sync when displayed<br>Usage:<br> var a = new UISwitch();<br>a.image1 = "asset/image/picture/control/check_unselected.png";<br>a.image2 = "asset/image/picture/control/check _selected.png";<br>a.width = 100;<br>a.height = 100;<br>a.switchID = "5"; // Bind player switch #5<br>stage.addChild(a);<br>// Event Listening Example<br>a.on( EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-04-14

**Inheritance**  →[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **switchID** : number;<br>Specify the bound player switch ID  |
| **image1** : string;<br>Unchecked effect picture  |
| **image2** : string;<br>Effect image when selected Default ="asset/image/picture/control/check_selected.png"  |
| **[grid9img1](#grid9img1)** : string;<br>Nine grid settings for unselected images: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)  |
| **[grid9img2](#grid9img2)** : string;<br>Nine grid settings for the selected state picture: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |
| **[onChangeFragEvent](#onChangeFragEvent)** : string;<br>Fragment event content: triggered when the selected state is changed  |



## Details

### grid9img1
###### grid9img1 : string;
Nine grid settings for images in unchecked state: top margin, right margin, bottom margin, left margin, whether to tile (1 means tile)<br> 
Make the material not simply stretch, but stretch according to the nine grid way Default="0,0,0,0,0"
### grid9img2
###### grid9img2 : string;
Nine grid settings for images in the selected state: top margin, right margin, bottom margin, left margin, whether to tile (1 means tile)<br> 
Make the material not simply stretch, but stretch according to the nine grid way Default="0,0,0,0,0"
### onChangeFragEvent
###### onChangeFragEvent : string;
Fragment event content: triggered when the selected state is changed<br> 
Active call method: CommandPage.startTriggerFragmentEvent




