# UIVariable Display variable components
>You can select a variable binding that shows the component of the variable, and the text of the component will be updated automatically when the variable changes<br>Related events<br>EventObject.CHANGE When the text changes<br>[Variable system] will show the numeric variable in sync when it is displayed<br>How to use:<br>var a = new UIVariable() ;<br>a.varID = 2; // numeric variable ID<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIString](?file=006-API-2D单机内核/002-客户端/003-界面/025-UIString)→[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **varID** : string;<br>Numeric variable ID  |

