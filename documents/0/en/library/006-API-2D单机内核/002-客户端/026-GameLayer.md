# GameLayer Total game display level
>Access a unique instance of this class via Game.layer<br>Override initLayer to customize the hierarchy<br>System default level:<br>stage：<br>&nbsp;&nbsp;-- sceneLayer Scene layer: usually scenes should be added to the scene layer<br>&nbsp;&nbsp;-- imageLayer Image layer: usually display pictures animation etc. added in this layer<br>&nbsp;&nbsp;-- uiLayer Interface layer: usually interfaces and dialog boxes are added in this layer<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-01-09

**Inheritance**  →GameSprite<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **sceneLayer** : GameSprite;<br>Scene layer: usually scenes should be added to the scene layer  |
| **imageLayer** : GameImageLayer;<br>Image layer: usually display pictures animation etc. added in this layer  |
| **uiLayer** : GameSprite;<br>UI layer: interface layer: usually interfaces, dialog boxes are added in this layer  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[initLayer](#initLayer)**(): void<br>Initialization level

## Details



## initLayer
###### **[initLayer](#initLayer)**(): void :
Initialization level<br>
You can override this function with GameLayer.prototype.initLayer<br>
The system default levels are, in order<br>
-- Scene layer this.addChild(this.sceneLayer);<br>
-- Image layer this.addChild(this.imageLayer);<br>
-- UI layer this.addChild(this.uiLayer); Dialogs on this layer




# Related code examples
Temporarily hide all interface layers and show them again after a 3-second interval<br>
>Game.layer.uiLayer.visible = false;<br>
>setTimeout(()=>{<br>
>&nbsp;&nbsp;&nbsp;Game.layer.uiLayer.visible = true;<br>
>},3000);<br>
>


