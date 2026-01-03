# GUI_BASE Interface implementation class base class
>The interface class used for generation (GUI_XX) inherits from this class<br>so that the internal controls can be called at initialization time<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-11

**Inheritance**  →[UIRoot](?file=006-API-2D单机内核/002-客户端/003-界面/021-UIRoot)→[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[prerender](#prerender)** : boolean;<br>Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.  |
| **guiID** : number;<br>Interface ID  |
| **[compsIDInfo](#compsIDInfo)** : any;<br>Find a component based on the unique ID of the component under it compsIDInfo[comp.id] = comp; Default value = {}  |
| **hasRootCommand** : boolean[];<br>Presence or absence of interface propriety events  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(guiID : number)<br>Constructors

## Details

### prerender
###### prerender : boolean;
Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Pre-rendering will consume some performance, you can choose to use this in the case of more interface resources, turn on this will have additional performance and memory overhead
### compsIDInfo
###### compsIDInfo : any;
Find a component based on the unique ID of the component under it compsIDInfo[comp.id] = comp; Default Value={}<br>
Only the components pre-set by the interface editor will be stored in this property, if you dynamically remove the added ones you can manage the list yourself


## constructor
###### **[constructor](#constructor)**(guiID : number) :
Constructors
##### Parameters
	guiID Interface ID





