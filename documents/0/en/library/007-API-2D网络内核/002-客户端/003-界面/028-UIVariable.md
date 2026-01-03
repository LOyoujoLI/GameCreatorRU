# UIVariable Display variable components
>You can select a variable binding to display the component of that variable, and the text of that component will be updated automatically when the variable is changed.<br>Related Events<br>EventObject.CHANGE When the text changes<br>[变量系统]Automatically register requests for synchronization of server player variables when displayed<br>使用方式：<br>var a = new UIVariable();<br>a.varID = 2; // Variable ID<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.CHANGE,this,this.onChange);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIString](?file=007-API-2D网络内核/002-客户端/003-界面/025-UIString)→[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **varID** : string;<br>Player value variable ID  |




