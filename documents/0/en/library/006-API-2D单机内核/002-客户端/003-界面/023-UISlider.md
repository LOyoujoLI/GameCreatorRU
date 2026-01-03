# UISlider Slider assembly
>Component for specifying a range min and max, sliding between min and max to obtain a value<br>Related events:<br>&nbsp;EventObject.CHANGE Dispatch when value is changed<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>Usage:<br>var a = new UISlider();<br>a.image1 = "asset/image/picture/control/slider_bg.png";<br>a.image2 = "asset/image/picture/control/slider_block.png";<br>a.image3 = "asset/image/picture/control/slider_bgfill.png";<br>a.value = 45;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **image1** : string;<br>Background image  |
| **image2** : string;<br>Slider diagram  |
| **image3** : string;<br>Slider Fill Chart  |
| **transverseMode** : boolean;<br>Horizontal mode Default=true  |
| **min** : number;<br>Minimum Default = 0  |
| **max** : number;<br>Maximum value Default value = 100  |
| **value** : number;<br>Set and get current value Default = 50  |
| **step** : number;<br>Step Value Default = 1  |
| **[bgGrid9](#bgGrid9)** : string;<br>Background image nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |
| **[blockGrid9](#blockGrid9)** : string;<br>Slider image nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |
| **[blockFillGrid9](#blockFillGrid9)** : string;<br>Slider fill chart nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)  |
| **blockFillMode** : number;<br>Display mode: 0-Display slider only 1-Fill mode 2-Display slider's fill mode Default = 2  |
| **isBindingVarID** : boolean;<br>Whether to bind numeric variables  |
| **bindingVarID** : number;<br>Set the number of the bound numeric variable  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setValueForce](#setValueForce)**(value : number): void<br>Set the current value, this function does not dispatch EventObject.CHANGE event

## Details

### bgGrid9
###### bgGrid9 : string;
Background image nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### blockGrid9
###### blockGrid9 : string;
Slider image nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"
### blockFillGrid9
###### blockFillGrid9 : string;
Slider fill chart nine-pane settings: top margin, right margin, bottom margin, left margin, whether tiled (1 means tiled)<br>
Make the material not simply stretched, but stretched according to the nine-grid approach Default = "0,0,0,0,0"


## setValueForce
###### **[setValueForce](#setValueForce)**(value : number): void :
Set the current value, this function does not dispatch EventObject event
##### Parameters
	value value





