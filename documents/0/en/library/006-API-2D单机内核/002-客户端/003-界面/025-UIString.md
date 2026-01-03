# UIString Text Components
>Display text component with support for binding player string variables<br>Related events<br>EventObject.CHANGE Text changes when<br>[variable system] automatically synchronizes string variables when displayed<br>Usage: <br>var a = new UIString();<br>a.text = "kds"; // fixed text<br>a.text = "$6"; // bind player string variable #6<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  [UIInput](?file=006-API-2D单机内核/002-客户端/003-界面/018-UIInput)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **text** : string;<br>Text content $5 means use the player string variable #5  |
| **fontSize** : number;<br>Font Size Default=16  |
| **color** : string;<br>Font color Default="#000000"  |
| **bold** : boolean;<br>Bold Default=false |
| **italic** : boolean;<br>Italics Default=false  |
| **smooth** : boolean;<br>Smoothing Default=false  |
| **leading** : number;<br>Line spacing Default=0  |
| **letterSpacing** : number;<br>Word spacing Default=0 |
| **font** : string;<br>Font, the default is the preset default font  |
| **wardWrap** : boolean;<br>Whether or not to automatically line feed Default value = true  |
| **overflow** : number;<br>Handling when text exceeds 0 - Show 1 - Hide Default = 0  |
| **align** : number;<br>Horizontal Alignment 0-Left Alignment 1-Middle Alignment 2-Right Alignment Default=0  |
| **valign** : number;<br>Vertical Alignment 0 - Top Alignment 1 - Center Alignment 2 - Right Alignment Default = 0  |
| **shadowEnabled** : boolean;<br>Whether to turn on shadows  |
| **shadowColor** : string;<br>Shade color Default="#000000"  |
| **shadowDx** : number;<br>Shadow Horizontal Offset (pixels) Default = 1  |
| **shadowDy** : number;<br>Shading Vertical Offset (pixels) Default = 1  |
| **stroke** : number;<br>Stroke pixel size: If the effect is not satisfactory you can use a large font and bold with it, or try another font Default = 0  |
| **strokeColor** : string;<br>Stroke color, displayed when the stroke pixel size is not 0 Default="#000000"  |
| **textWidth** : number;<br>[Read-only] Get the actual text content width  |
| **textHeight** : number;<br>[Read Only] Get the actual text content height  |
| **[onChangeFragEvent](#onChangeFragEvent)** : string;<br>Fragment event content: triggered when the text is changed  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setTextForce](#setTextForce)**(v : string): void<br>Set text (does not dispatch EventObject.CHANGE event)

## Details

### onChangeFragEvent
###### onChangeFragEvent : string;
Fragment event content: triggered when changing text<br> 
Active call method: CommandPage.startTriggerFragmentEvent


## setTextForce
###### **[setTextForce](#setTextForce)**(v : string): void :
Set text (does not dispatch EventObject.CHANGE event) 
##### Parameters 
	v Text content $5 means use player string variable #5





