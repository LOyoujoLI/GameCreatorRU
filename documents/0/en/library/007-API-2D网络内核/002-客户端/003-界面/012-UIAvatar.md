# UIAvatar Avatar component
>Wrapped Avatar interface component<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>&nbsp;Avatar.ACTION_PLAY_COMPLETED<br>&nbsp;Avatar.RENDER Dispatched when a new frame is actually reached, not dispatched if the body does not have an actual frame<br>Usage:<br>var a = new UIAvatar();<br>a.avatarID = 5;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br>a.on(Avatar.ACTION_PLAY_COMPLETED,this,this.onActionPlayComplete);<br>a.on(Avatar.RENDER,this,this.onRender);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-12-11

**Inheritance**  →UIBase<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **avatarID** : number;<br>AVATAR-ID  |
| **avatar** : Avatar;<br>[Read Only] Avatar Object  |
| **isPlay** : boolean;<br>Whether to play  |
| **playOnce** : boolean;<br>Play only once  |
| **scaleNumberX** : number;<br>Horizontal Scaling 1 for 100% Default = 1  |
| **scaleNumberY** : number;<br>Vertical Scaling 1 for 100% Default = 1  |
| **avatarFrame** : number;<br>Start frame default=1  |
| **avatarFPS** : number;<br>Frame rate Default = 12  |
| **actionID** : number;<br>Action expression Default=1  |


