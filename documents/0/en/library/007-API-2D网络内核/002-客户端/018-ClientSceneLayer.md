# ClientSceneLayer Scene Layer - Show Objects
>Includes image layers and block layers<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-22

**Inheritance**  →GameSprite<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **scene** : ClientScene;<br>Corresponding map objects  |
| **dx** : number;<br>Offset-X Default=0  |
| **dy** : number;<br>Offset value-Y Default=0  |
| **xMove** : number;<br>X-direction auto-scroll Default=0  |
| **yMove** : number;<br>Automatic scrolling in Y direction Default=0  |
| **[isChangeChildZOrder](#isChangeChildZOrder)** : boolean;<br>Whether to automatically change the sub-display object level Refresh according to the display object Y coordinate  |
| **xLoop** : boolean;<br>x-loop (tiling) After changing this item in the middle, you need to call refreshLoopShow to refresh  |
| **yLoop** : boolean;<br>y-loop (tiling) After changing this item in the middle, you need to call refreshLoopShow to refresh  |
| **prospectsPerX** : number;<br>Vision scale X-axis Default value = 1.0 means 100% Normal map is 100%, the smaller the value, the slower the movement, multiple vision is generally made by changing this property  |
| **prospectsPerY** : number;<br>Vision scale Y axis Default value = 1.0 means 100% Normal map is 100%, the smaller the value the slower the movement, multiple vision is generally made by changing this property  |
| **mapUrl** : string;<br>[Read Only] Map layer image resource address  |
| **drawMode** : boolean;<br>Whether it is drawing mode (block) or not, you need to set it when creating before you can use block mode to draw  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(scene : [ClientScene](?file=007-API-2D网络内核/002-客户端/017-ClientScene))<br>Constructors
| **[refreshLoopShow](#refreshLoopShow)**(): void<br>Refresh the loop display, call this after changing xLoop or yLoop in the middle to refresh
| **[drawTile](#drawTile)**(xGrid : number,  yGrid : number,  tileData : { tex): void<br>When drawing blocks, you need to call flushTile for printing after drawing. When drawing multiple blocks at the same time, you can print them uniformly after drawing in order to save unnecessary performance loss.
| **[drawAutoTile](#drawAutoTile)**(xGrid : number,  yGrid : number,  autoTileID : number,  texture : Texture): void<br>When drawing automatic block components, you need to call flushTile for printing after drawing. When drawing multiple blocks at the same time, you can print them uniformly after finishing drawing in order to save unnecessary performance loss.
| **[flushTile](#flushTile)**(): void<br>Refresh blocks: display previously drawn blocks in one place
| **[clearTile](#clearTile)**(): void<br>Clear the blocks, empty all the current blocks
| **[setBigImage](#setBigImage)**(imgURL : string): void<br>Set the full image as the map image for the layer, only the image layer is available
| **[setBigTexture](#setBigTexture)**(t : Texture): void<br>Set the background according to the texture, only the image layer is available

## Details

### isChangeChildZOrder
###### isChangeChildZOrder : boolean;
Whether to automatically change the sub-display object level Refresh according to the display object Y coordinate<br>
For example, in a normal RPG game, A below B will block B, and when A moves above B will be blocked by B. Turning this on will automatically calculate


## constructor
###### **[constructor](#constructor)**(scene : [ClientScene](?file=007-API-2D网络内核/002-客户端/017-ClientScene)) :
Constructors
##### Parameters
	scene Affiliated scenes



## refreshLoopShow
###### **[refreshLoopShow](#refreshLoopShow)**(): void :
Refresh the loop display, call this after changing xLoop or yLoop in the middle to refresh



## drawTile
###### **[drawTile](#drawTile)**(xGrid : number,  yGrid : number,  tileData : { tex): void :
When drawing blocks, you need to call flushTile for printing after drawing. When drawing multiple blocks at the same time, you can print them uniformly after drawing in order to save unnecessary performance loss.<br>
The layer must be in draw mode (drawMode==true)
##### Parameters
	xGrid Grid coordinates x
	yGrid Grid coordinates y
	tileData Mapping object, block ID, sample of the block (x,y,width,height) If null, it means erase



## drawAutoTile
###### **[drawAutoTile](#drawAutoTile)**(xGrid : number,  yGrid : number,  autoTileID : number,  texture : Texture): void :
When drawing automatic block components, you need to call flushTile for printing after drawing. When drawing multiple blocks at the same time, you can print them uniformly after finishing drawing in order to save unnecessary performance loss.<br>
The layer must be in draw mode (drawMode==true)
##### Parameters
	xGrid Grid coordinates x
	yGrid Grid coordinates y
	autoTileID ID of automatic components
	texture Mapping of automatic components



## flushTile
###### **[flushTile](#flushTile)**(): void :
Refresh blocks: display previously drawn blocks in one place



## clearTile
###### **[clearTile](#clearTile)**(): void :
Clear the blocks, empty all the current blocks



## setBigImage
###### **[setBigImage](#setBigImage)**(imgURL : string): void :
Set the full image as the map image for the layer, only the image layer is available
##### Parameters
	imgURL Full image address



## setBigTexture
###### **[setBigTexture](#setBigTexture)**(t : Texture): void :
Set the background according to the texture, only the image layer is available
##### Parameters
	t Poster




# Related code examples
Create an image layer to add to the current scene<br>
>Create a layer and set the image, add it to the scene, the default is in the upper left corner (0,0)<br>
>var layer = new ClientSceneLayer(Game.currentScene);<br>
>layer.setBigImage("asset/image/xxxx.png");<br>
>Game.currentScene.addLayer(layer);<br>
>

<br>
Create a block layer and draw the block<br>
>// Create a block layer<br>
>var layer = new ClientSceneLayer(Game.currentScene);<br>
>layer.drawMode = true;<br>
>layer.graphics.drawRect(0,0,100,100,"#FF0000");<br>
>// Load the specified mapping as a block material<br>
>AssetManager.loadImage("asset/image/tile/矿洞.png", Callback.New((tex: Texture) => {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// Get the 48x48 map from the map source 0,0 and draw it to the position of grid 3,0<br>
>&nbsp;&nbsp;&nbsp;&nbsp;layer.drawTile(3, 0, { tex: tex, texID: 1, x: 0, y: 0, w: 48, h: 48 });<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// Get the 48x48 plot from the plot source 96,0 and draw it to the grid 4,0<br>
>&nbsp;&nbsp;&nbsp;&nbsp;layer.drawTile(4, 0, { tex: tex, texID: 1, x: 96, y: 0, w: 48, h: 48 });<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// Submit to draw<br>
>&nbsp;&nbsp;&nbsp;&nbsp;layer.flushTile();<br>
>}, this));<br>
><br>
>// Load the specified auto component mapping as an auto component material<br>
>AssetManager.loadImage("asset/image/tile/GCAT1a.png", Callback.New((tex: Texture) => {<br>
>&nbsp;&nbsp;&nbsp;// Plot to coordinates 3,3 as automatic component #6<br>
>&nbsp;&nbsp;&nbsp;layer.drawAutoTile(3, 3, 6, tex);<br>
>&nbsp;&nbsp;&nbsp;// Submit to draw<br>
>&nbsp;&nbsp;&nbsp;layer.flushTile();<br>
>}, this));<br>
><br>
>// Add to the scene<br>
>Game.currentScene.addLayer(layer);<br>
>


