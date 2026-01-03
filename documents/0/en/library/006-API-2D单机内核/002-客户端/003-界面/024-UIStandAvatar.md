# UIStandAvatar Standing Avatar Components
>Interface components that encapsulate the standing avatar<br>Related Events<br>&nbsp;EventObject.LOADED Event when loading is complete<br>&nbsp;Avatar.ACTION_PLAY_COMPLETED<br>&nbsp;Avatar.RENDER Dispatched when a new frame is actually reached, not dispatched if the body does not have an actual frame<br>Usage:<br>var a = new UIStandAvatar();<br>a.avatarID =5;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br>a.on(Avatar.ACTION_PLAY_COMPLETED,this,this.onActionPlayComplete);<br>a.on(Avatar.RENDER,this,this.onRender);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-01-27

**Inheritance**  →[UIAvatar](?file=006-API-2D单机内核/002-客户端/003-界面/012-UIAvatar)→[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **flip** : boolean;<br>Whether to flip horizontally  |





