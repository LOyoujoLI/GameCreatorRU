# UIRoot Container Components
>Generally used to load sub-display objects and can crop areas to display only a portion of the content<br>Related Events<br>&nbsp;EventObject.LOADED Event when loading is complete, dispatched only as the interface itself (root container)<br>Usage:<br>var a = new UIRoot();<br>a.addChild(b);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-12

**Inheritance**  →[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  [UIList](?file=007-API-2D网络内核/002-客户端/003-界面/019-UIList)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **enabledLimitView** : boolean;<br>Whether to restrict the display in the area Default=false  |
| **scrollShowType** : number;<br>Scroll bar display mode 0-No display 1-Display 2-Auto display 3-Display vertical scroll bar only 4-Display horizontal scroll bar only Default=2  |
| **scrollWidth** : number;<br>Scroll bar width Default=16  |
| **vScrollBg** : string;<br>Vertical scrollbar background skin  |
| **vScrollBar** : string;<br>Vertical scrollbar skin  |
| **hScrollBg** : string;<br>Horizontal scrollbar background skin  |
| **hScrollBar** : string;<br>Horizontal scrollbar skin  |
| **[slowmotionType](#slowmotionType)** : number;<br>The content area inside the container can be scrolled by sliding the mouse or hand (need to turn on the restriction to display in the area and the actual internal content size has exceeded the display area)  |
| **vScrollValue** : number;<br>Vertical scrolling value(0~100)  |
| **hScrollValue** : number;<br>Horizontal scrolling value(0~100)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[refresh](#refresh)**(): void<br>Refresh the scrollbar according to the size of the content area, if the size of the child objects inside the container is changed

## Details

### slowmotionType
###### slowmotionType : number;
The content area inside the container can be scrolled by sliding the mouse or hand (need to turn on the restriction to display in the area and the actual internal content size has exceeded the display area)<br>
0=Enable this effect on mobile only,1=Always enable this effect,2=None Default value=0


## refresh
###### **[refresh](#refresh)**(): void :
Refresh the scrollbar according to the size of the content area, if the size of the child objects inside the container is changed<br>
Then you need to call this method to recalculate in order to refresh the scrollbar.





