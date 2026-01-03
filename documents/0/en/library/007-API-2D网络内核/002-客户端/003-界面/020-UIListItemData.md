# UIListItemData Item data base classes in interface components
>Corresponding to the data bound by the item in UIList, each item display object will correspond to an item data (an instance of that class or its subclass)<br>Usage can be found in [UIList](?file=007-API-2D网络内核/002-客户端/003-界面/019-UIList)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-07-09

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **data** : any;<br>Arbitrary additional data  |
| **isOpen** : boolean;<br>Whether it is in the open state (the case of tree nodes)  |
| **parent** : UIListItemData;<br>[Read-only] Get parent node  |
| **numChildren** : number;<br>[Read-only] Total number of child nodes  |
| **children** : UIListItemData[];<br>[Read-only] Child Node List  |
| **[root](#root)** : UIListItemData;<br>[Read-only] Get the root node of the tree structure  |
| **[depth](#depth)** : number;<br>[Read-only] Get the depth of the tree you are in  |
| **isHideNode** : boolean;<br>[Read-only] whether it is a hidden node (i.e. the parent node may be turned off)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getSaveData](#getSaveData)**(includeData? : boolean): any<br>Extraction of stored data
| **[recoverySaveData](#recoverySaveData)**(saveData : any): [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)<br>[Static] Restore stored data
| **[addChild](#addChild)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): void<br>Add Node
| **[addChildAt](#addChildAt)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData),  index : number): void<br>Add nodes to the specified index
| **[removeChild](#removeChild)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): void<br>Remove Node
| **[removeChildAt](#removeChildAt)**(index : number): void<br>Remove a node to the specified index
| **[removeAll](#removeAll)**(): void<br>Remove all nodes
| **[getChildAt](#getChildAt)**(index : number): [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)<br>Get nodes by index
| **[getChildIndex](#getChildIndex)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): number<br>Get node index
| **[isInherit](#isInherit)**(data : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): boolean<br>Whether to inherit from the specified node
| **[getList](#getList)**(arr? : UIListItemData[]): UIListItemData[]<br>Get the list of child nodes in all nodes under the tree structure (including its own nodes)

## Details

### root
###### root : UIListItemData;
[Read-only] Get the root node of the tree structure<br>
@return [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)
### depth
###### depth : number;
[Read-only] Get the depth of the tree you are in<br>
@return [number]


## getSaveData
###### **[getSaveData](#getSaveData)**(includeData? : boolean): any :
Extraction of stored data
##### Parameters
	includeData [Optional] Default=false Whether to include custom additional data, please ensure that the data can be JSONized



## recoverySaveData
###### **[recoverySaveData](#recoverySaveData)**(saveData : any): [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData) :
[Static] Restore stored data
##### Parameters
	saveData



## addChild
###### **[addChild](#addChild)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): void :
Add Node
##### Parameters
	item Node Data Objects



## addChildAt
###### **[addChildAt](#addChildAt)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData),  index : number): void :
Add nodes to the specified index
##### Parameters
	item Node Data Objects
	index Insert the index where



## removeChild
###### **[removeChild](#removeChild)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): void :
Remove Node
##### Parameters
	item Node Data Objects



## removeChildAt
###### **[removeChildAt](#removeChildAt)**(index : number): void :
Remove a node to the specified index
##### Parameters
	index The index where the node is located



## removeAll
###### **[removeAll](#removeAll)**(): void :
Remove all nodes



## getChildAt
###### **[getChildAt](#getChildAt)**(index : number): [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData) :
Get nodes by index
##### Parameters
	index The index where the node is located

##### Return
[UIListItemData]

## getChildIndex
###### **[getChildIndex](#getChildIndex)**(item : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): number :
Get node index
##### Parameters
	item Node Data Objects



## isInherit
###### **[isInherit](#isInherit)**(data : [UIListItemData](?file=007-API-2D网络内核/002-客户端/003-界面/020-UIListItemData)): boolean :
Whether to inherit from the specified node



## getList
###### **[getList](#getList)**(arr? : UIListItemData[]): UIListItemData[] :
Get the list of child nodes in all nodes under the tree structure (including its own nodes)
##### Parameters
	arr [Optional] Default=null The specified array is used to load the fetched result data





