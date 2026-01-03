# UIButton Button assembly
>Button component with three states (normal, on press, on mouse hover)<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>Usage:<br>var a = new UIButton();<br>a.image1 = "asset/image/picture/control/btn_normal.png";<br>a.image2 = "asset/image/picture/control/btn_over.png";<br>a.image3 = "asset/image/picture/control/btn_click.png";<br>a.width = 200;<br>a.height = 100;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **image1** : string;<br>Image path in normal state mouse_out  |
| **image2** : string;<br>Image path on mouse hover mouse_over  |
| **image3** : string;<br>Image path when mouse is pressed mouse_down  |
| **[grid9img1](#grid9img1)** : string;<br>The normal state of the image of the nine grid settings: the top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |
| **[grid9img2](#grid9img2)** : string;<br>Nine grid settings for the picture when the mouse is moved in: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)  |
| **[grid9img3](#grid9img3)** : string;<br>Nine grid settings for the picture when the mouse is clicked: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)  |
| **label** : string;<br>Text displayed on the button  |
| **align** : number;<br>Horizontal text alignment 0-Left 1-Center 2-Right Default=1  |
| **valign** : number;<br>Vertical Text Alignment 0-Top 1-Center 2-Bottom Default = 1  |
| **bold** : boolean;<br>Text Bold Default=false  |
| **italic** : boolean;<br>Italic Default=false  |
| **smooth** : boolean;<br>Smoothing Default=false  |
| **font** : string;<br>Text font, the default value is the preset default font  |
| **color** : string;<br>Text color Default value="#999999"  |
| **overColor** : string;<br>Text color on mouse hover Default="#999999"  |
| **clickColor** : string;<br>Text color on mouse click Default="#999999"  |
| **fontSize** : number;<br>Text font size Default value=16  |
| **textDx** : number;<br>Horizontal offset of text, default value=0  |
| **textDy** : number;<br>Vertical offset of text, default value=0  |



## Details

### grid9img1
###### grid9img1 : string;
The normal state of the image of the nine grid settings: the top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### grid9img2
###### grid9img2 : string;
Nine grid settings for the picture when the mouse is moved in: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### grid9img3
###### grid9img3 : string;
Nine grid settings for the picture when the mouse is clicked: top margin, right margin, bottom margin, left margin, and whether to tile (1 means tile)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"




