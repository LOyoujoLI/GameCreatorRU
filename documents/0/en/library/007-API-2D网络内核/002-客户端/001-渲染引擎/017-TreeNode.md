# TreeNode Node category
>Show the base class of the object, have the parent-child node feature, tree structure<br>Support events.<br>EventObject.DISPLAY When added to the display list (i.e. the object is added to the display list of the stage and triggered from not needing to be rendered to when the state that needs to be rendered changes)<br>EventObject.UNDISPLAY When removed from the display list (i.e. when the object is removed from the display list of the stage, triggered when the state changes from needing to be rendered to not needing to be rendered)<br>EventObject.REMOVED Triggered when removed from parent node (no need to be in the display list)<br>EventObject.ADDED Triggered when added to a node (no need to be in the display list)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →EventDispatcher<br>
**Subcategories**  [Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **name** : string;<br>Node Name  |
| **disposed** : boolean;<br>[Read-only] If or not the object has been destroyed. The object cannot be used again after it is destroyed  |
| **numChildren** : number;<br>[Read-only] The number of child objects.  |
| **parent** : TreeNode;<br>Parent Node  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[dispose](#dispose)**(): void<br>Destroy the object. destroy object removes itself from the parent by default and cleans up its own reference relationships, waiting for the js automatic garbage collection mechanism. destroy cannot be used again.
| **[addChild](#addChild)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Add child nodes.
| **[addChildren](#addChildren)**(...args : any[]): void<br>Batch add child nodes
| **[addChildAt](#addChildAt)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode),  index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Add a child node to the specified index location.
| **[getChildIndex](#getChildIndex)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): number<br>Get the index position of the child node based on the child node object.
| **[getChildByName](#getChildByName)**(name : string): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Get the child node object based on the name of the child node.
| **[getChildAt](#getChildAt)**(index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Get the child node object based on the index position of the child node.
| **[setChildIndex](#setChildIndex)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode),  index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Set the index position of the child node.
| **[removeChild](#removeChild)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Delete the child node.
| **[removeSelf](#removeSelf)**(): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Delete itself from the parent container, no exception will be thrown if it has already been deleted.
| **[removeChildByName](#removeChildByName)**(name : string): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Deletes the corresponding child node object according to the child node name, and does not throw an exception if it cannot be found.
| **[removeChildAt](#removeChildAt)**(index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Delete the corresponding child node object according to the child node index position.
| **[removeChildren](#removeChildren)**(beginIndex? : number,  endIndex? : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)<br>Delete all child objects in the specified index interval.
| **[contains](#contains)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): boolean<br>Whether the current container contains the specified TreeNode node object.

## Details



## dispose
###### **[dispose](#dispose)**(): void :
Destroy the object. destroy removes itself from the parent by default, and cleans up its own reference relationships, waiting for js automatic garbage collection mechanism. destroy cannot be used again. <br> 
destroy removes its own thing listener, its own timer listener, removes the child object and removes itself from the parent node.



## addChild
###### **[addChild](#addChild)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Add a child node. <br> 
@param node Node object<br> 
@return Returns the added node



## addChildren
###### **[addChildren](#addChildren)**(...args : any[]): void :
Batch add child nodes<br> 
@param ...args Numerous child nodes.



## addChildAt
###### **[addChildAt](#addChildAt)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode),  index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Adds a child node to the specified index location. <br> 
@param node The node object. <br> 
@param index The index position. <br> 
@return Returns the added node.



## getChildIndex
###### **[getChildIndex](#getChildIndex)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): number :
Get the index position of the child node based on the child node object. <br> 
@param node The child node. <br> 
@return The index position where the child node is located.



## getChildByName
###### **[getChildByName](#getChildByName)**(name : string): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Get the child node object based on the child node's name. <br> 
@param name The name of the child node. <br> 
@return The node object. 


## getChildAt
###### **[getChildAt](#getChildAt)**(index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Get the child node object based on the index position of the child node. <br> 
@param index index position<br> 
@return child node



## setChildIndex
###### **[setChildIndex](#setChildIndex)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode),  index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Set the index position of the child node. <br> 
@param node The child node. <br> 
@param index The new index. <br> 
@return Return the child node itself.



## removeChild
###### **[removeChild](#removeChild)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Deletes a child node. <br> 
@param node child node<br> 
@return Deleted node



## removeSelf
###### **[removeSelf](#removeSelf)**(): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Delete itself from the parent container, no exception will be thrown if it has already been deleted.

##### Return
The current TreeNode object.

## removeChildByName
###### **[removeChildByName](#removeChildByName)**(name : string): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Delete the corresponding child node object based on its name, without throwing an exception if it cannot be found. <br> 
@param name The object name.

##### Return
The TreeNode object that was found.

## removeChildAt
###### **[removeChildAt](#removeChildAt)**(index : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Delete the corresponding child node object based on the child node index position. <br> 
@param index The index position of the node. <br> 
@return The node being deleted. 


## removeChildren
###### **[removeChildren](#removeChildren)**(beginIndex? : number,  endIndex? : number): [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode) :
Delete all child objects in the specified index interval. <br> 
@param beginIndex The start index. Default=0<br> 
@param endIndex Ends the index. Default=0x7fffffff

##### Return
The current node object.

## contains
###### **[contains](#contains)**(node : [TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)): boolean :
Whether the current container contains the specified TreeNode node object. <br> 
@param node The specified TreeNode node object. <br> 
@return A Boolean value indicating whether the specified TreeNode node object is contained.





