# Texture Posting source
>Texture processing class<br>== Usage ==<br>// Load the whole picture to use<br>AssetManager.loadImage("asset/image/xxx.png", Callback.New((tex: Texture) => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var img = new UIBitmap();<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;img.texture = tex;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;stage.addChild(img);<br>}, this));<br>// Loaded as a mapping<br>AssetManager.loadImage("asset/image/animation/2.png", Callback.New((tex: Texture) => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var g = new Graphics();<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Sampling a 128x128 size cutout from the 256,256 in the graph and displaying it at 50,50<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;g.fillTexture(tex, 50, 50, 128, 128, "repeat", new Point(256, 256));<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var sp = new Sprite();<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sp.graphics = g;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;stage.addChild(sp);<br>}, this));<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **DEF_UV** : Array<any>;<br>[Static] Default UV information  |
| **INV_UV** : Array<any>;<br>[Static] Inverted UV information  |
| **url** : string;<br>Image address  |
| **disposed** : boolean;<br>Read-only] indicates whether the resource has been released  |
| **width** : number;<br>Actual width.  |
| **height** : number;<br>Actual height.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[dispose](#dispose)**(): void<br>Destruction of textures
| **[getPixels](#getPixels)**(x : number,  y : number,  width : number,  height : number): Array<any><br>获取Texture上的某个区域的像素点

## Details



## dispose
###### **[dispose](#dispose)**(): void :
Destruction of textures



## getPixels
###### **[getPixels](#getPixels)**(x : number,  y : number,  width : number,  height : number): Array<any> :
Get the pixel points of an area on the Texture<br>
@param	x<br>
@param	y<br>
@param	width<br>
@param	height

##### Return
 Return the set of pixel points



