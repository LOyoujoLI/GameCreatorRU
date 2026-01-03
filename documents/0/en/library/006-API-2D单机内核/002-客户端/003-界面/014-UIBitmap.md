# UIBitmap Image Components
>Component for displaying a picture, supports binding player string variables (string variables store addresses)<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>&nbsp;EventObject.CHANGE Event when image image changes<br>Usage:<br>var a = new UIBitmap();<br>a.image = "asset/image/xxx.jpg"; // Loading fixed images<br>a.image = "$5"; // Bind the image address of player string variable #5<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br>a.on(EventObject.CHANGE,this,this.onChange);<br>[Variable System] will automatically register a request to synchronize the display of server player variables when displayed<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  [GameImage](?file=007-API-2D网络内核/002-客户端/026-GameImage)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[image](#image)** : string;<br>Image address, supports player string variables, e.g. $5 means use player string variable #5  |
| **[texture](#texture)** : Texture;<br>Image source, you can set the image style through the image source  |
| **[grid9](#grid9)** : string;<br>Nine grid settings: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)  |
| **flip** : boolean;<br>Horizontal Flip Default=false  |
| **pivotType** : number;<br>Home Alignment Mode 0-Home 1-Center Default = 0  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setImageForce](#setImageForce)**(image : string): void<br>Set image address (does not dispatch EventObject.CHANGE event)

## Details

### image
###### image : string;
Image address, supports player string variables, e.g. $5 means use player string variable #5<br>
>var img = new UIBitmap();<br>
>img.image = "$5";<br>
>Game.layer.uiLayer.addChild(img);<br>
>


### texture
###### texture : Texture;
Image source, you can set the image style through the image source<br>
If this property is set manually, the system will not uninstall the mapping when uninstalling the component, if necessary, you can uninstall it manually
### grid9
###### grid9 : string;
Nine grid settings: top margin, right margin, bottom margin, left margin, tiled or not (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-pattern approach Default = 0,0,0,0,0


## setImageForce
###### **[setImageForce](#setImageForce)**(image : string): void :
Set image address (does not dispatch EventObject.CHANGE event)
##### Parameters
	image Image address, supports player string variables, e.g. $5 means use player string variable #5





