# ArrayUtils Arrays tool class
>GC internal encapsulation of some common array methods<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[randOrder](#randOrder)**(arr : any[]): void<br>[Static] Randomly disordering within an array
| **[insert](#insert)**(arr : any[],  index : number,  ...arg : any[]): number<br>[Static] Adding data
| **[delete](#delete)**(arr : any[],  index : number): any<br>[Static] Delete data
| **[remove](#remove)**(arr : any[],  obj : any): any<br>[Static] Remove data and return a new array
| **[removeSameObjectD2](#removeSameObjectD2)**(arr : any[],  attrName : string,  ifNullIgnore : boolean): any[]<br>[Static] Reject identical elements and return a new array based on whether the child elements have the same attributes
| **[get](#get)**(arr : any[],  index : number): any<br>[Static] Get data
| **[set](#set)**(arr : any[],  index : number,  paramValue : any): any[]<br>[Static] Change the value in the data
| **[insertToNullPosition](#insertToNullPosition)**(arr : any[],  obj : any): number<br>[Static] Insert Data Find Null or Add
| **[getNullPosition](#getNullPosition)**(arr : any[],  startIndex? : number): number<br>[Static] Find an empty position
| **[removeSameObject](#removeSameObject)**(arr : any[]): any[]<br>[Static] Eliminate the same elements
| **[matchAttributes](#matchAttributes)**(arr : any,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[]<br>[Static] Matching data, such as in a set of object data, filtering out the set of objects that contain certain attributes with the value of how many
| **[matchAttributesD2](#matchAttributesD2)**(arr : any,  attribute : string,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[]<br>[Static] Matching data Depth 2, used to match whether the object in the object contains the property
| **[matchAttributesD3](#matchAttributesD3)**(arr : any,  attribute : string,  attribute2 : string,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[]<br>[Static] Matching Data Depth 3
| **[getChildAttributeToCreateArray](#getChildAttributeToCreateArray)**(arr : any,  attributeName : string,  ignoreNullChild? : boolean): any[]<br>[Static] Get the value of the specified property of the object/array within the object to form a new array
| **[getElementSize](#getElementSize)**(arr : any[],  value : any): number<br>[Static] Get the number of occurrences of an element in an array
| **[createObjects](#createObjects)**(objCls: any, size: number, onCreateOne?: (index : number,  obj : any) => void,  arr? : any[]): any[]<br>[Static] Batch loading to create objects
| **[swap](#swap)**(arr : any[],  index1 : number,  index2 : number): void<br>[Static] Swapping Positions in Arrays
| **[setIndex](#setIndex)**(arr : any[],  element : any,  index : number): void<br>[Static] Adjusting the position of elements in an array
| **[sort](#sort)**(arr : any[],  attributeName : string,  isAsc : boolean): void<br>[Static] Sorted by asc (ignore case)
| **[compare](#compare)**(aArr : any[],  bArr : any[])<br>[Static] Compare, list the different elements in array B relative to array A
| **[getTreeNodeArray](#getTreeNodeArray)**(treeNode : any,  childrenAttr? : string,  arrayList? : any[],  checkIsOpen? : boolean,  isOpenAttr? : string,  ignoreChildrenCondition? : Callback): any[]<br>[Static] Get the list of child nodes in all nodes under the tree structure (including its own nodes)

## Details



## randOrder
###### **[randOrder](#randOrder)**(arr : any[]): void :
[Static] Randomly disordering within an array
##### Parameters
	arr Arrays



## insert
###### **[insert](#insert)**(arr : any[],  index : number,  ...arg : any[]): number :
[Static] Adding data
##### Parameters
	arr Data sets
	index Index -1 = added to the end of the array
	arg Added data



## delete
###### **[delete](#delete)**(arr : any[],  index : number): any :
[Static] Delete data
##### Parameters
	arr Data sets
	index Index -1 = Delete tail-end data

##### Return
[any] Deleted data objects

## remove
###### **[remove](#remove)**(arr : any[],  obj : any): any :
[Static] Remove data and return a new array
##### Parameters
	arr Data sets
	obj Data Objects

##### Return
[any]

## removeSameObjectD2
###### **[removeSameObjectD2](#removeSameObjectD2)**(arr : any[],  attrName : string,  ifNullIgnore : boolean): any[] :
[Static] Reject identical elements and return a new array based on whether the child elements have the same attributes
##### Parameters
	arr Original array
	attrName Property Name
	ifNullIgnore Whether the property is not removed if it is null

##### Return
[any] Original array

## get
###### **[get](#get)**(arr : any[],  index : number): any :
[Static] Get data
##### Parameters
	arr Data sets
	index Index -1 = Tail-end data

##### Return
[any]

## set
###### **[set](#set)**(arr : any[],  index : number,  paramValue : any): any[] :
[Static] Change the value in the data
##### Parameters
	arr Data sets
	index Index
	paramValue Parameters and values Object
	The actual array of objects being changed



## insertToNullPosition
###### **[insertToNullPosition](#insertToNullPosition)**(arr : any[],  obj : any): number :
[Static] Insert Data Find Null or Add
##### Parameters
	arr Arrays
	obj Object to be inserted

##### Return
[number] Indexes inserted into

## getNullPosition
###### **[getNullPosition](#getNullPosition)**(arr : any[],  startIndex? : number): number :
[Static] Find an empty position
##### Parameters
	arr Arrays
	startIndex [Optional] Default value = 0 Index

##### Return
[number] Find empty position index

## removeSameObject
###### **[removeSameObject](#removeSameObject)**(arr : any[]): any[] :
[Static] Eliminate the same elements
##### Parameters
	arr Original array

##### Return
[any] New Arrays

## matchAttributes
###### **[matchAttributes](#matchAttributes)**(arr : any,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[] :
[Static] Matching data, such as filtering out the set of objects that contain data on a set of objects with certain attribute values<br> 
Usage examples: <br>
>var arr = [{a:6},{a:7},{a:8},{a:6}];<br>
>var m = ArrayUtils.matchAttributes(arr,{a:6},false); // There are two results in the return group [{a:6},{a:6}]<br>
>var m = ArrayUtils.matchAttributes(arr,{a:6},false,">"); // There are two results in the return group [{a:7},{a:8}]<br>
>var m = ArrayUtils.matchAttributes(arr,{a:6},false,"==",true); // Returns the index of the two results in the group, relative to the original array [0,3]<br>
>var m = ArrayUtils.matchAttributes(arr,{a:6},true); // Return 1 result in the group [{a:6}]<br>
>


##### Parameters
	arr Arrays
	matchObj Parameters
	onlyOne Whether to match only one data
	symbol [Optional] Default value = "==" Contrast symbol
	indexOfMode [Optional] Default=false Returns the index of the match instead of the matching object

##### Return
[any] Returns number[] if indexOfMode, otherwise returns data of the same type as arr

## matchAttributesD2
###### **[matchAttributesD2](#matchAttributesD2)**(arr : any,  attribute : string,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[] :
[Static] Matching data Depth 2, used to match whether an object in an object contains this attribute<br> 
Usage examples: <br>
>var arr = [{a:{b:2}},{a:{b:3},{a:{b:5}},{a:{b:7}}];<br>
>var m = ArrayUtils.matchAttributesD2(arr,"a",{b:2},false); // Return [{a:{b:2}}]<br>
>


##### Parameters
	arr Arrays
	attribute Properties
	matchObj Parameters
	onlyOne Whether to match only one data
	symbol [Optional] Default value = "==" Contrast symbol
	indexOfMode [Optional] Default=false Returns the index of the match instead of the matching object

##### Return
[any]

## matchAttributesD3
###### **[matchAttributesD3](#matchAttributesD3)**(arr : any,  attribute : string,  attribute2 : string,  matchData : any,  onlyOne : boolean,  symbol? : string,  indexOfMode? : boolean): any[] :
[Static] Matching Data Depth 3
##### Parameters
	arr Arrays
	attribute Properties
	attribute2 Attribute 2
	matchObj Parameters
	onlyOne Whether to match only one data
	symbol [Optional] Default value = "==" Contrast symbol
	indexOfMode [Optional] Default=false Returns the index of the match instead of the matching object

##### Return
[any]

## getChildAttributeToCreateArray
###### **[getChildAttributeToCreateArray](#getChildAttributeToCreateArray)**(arr : any,  attributeName : string,  ignoreNullChild? : boolean): any[] :
[Static] Get the value of the specified property of the object/array within the object to form a new array
##### Parameters
	arr Original object/Arrays
	attributeName The name of the specified property of the object in the original array
	ignoreNullChild [Optional] Default = true Whether to ignore child objects that are NULL in arr so that they are not added to the new array

##### Return
[any]

## getElementSize
###### **[getElementSize](#getElementSize)**(arr : any[],  value : any): number :
[Static] Get the number of occurrences of an element in an array
##### Parameters
	arr Arrays
	value chemical element

##### Return
[number] Number of occurrences

## createObjects
###### **[createObjects](#createObjects)**(objCls: any, size: number, onCreateOne?: (index : number,  obj : any) => void,  arr? : any[]): any[] :
[Static] Batch loading to create objects
##### Parameters
	objCls Object Class
	size Number
	obj
	arr [Optional] Default=null Array to load to, set to load with this array

##### Return
[any]

## swap
###### **[swap](#swap)**(arr : any[],  index1 : number,  index2 : number): void :
[Static] Swapping Positions in Arrays
##### Parameters
	arr Arrays
	index1 Position 1
	index2 Position 2



## setIndex
###### **[setIndex](#setIndex)**(arr : any[],  element : any,  index : number): void :
[Static] Adjusting the position of elements in an array
##### Parameters
	arr Arrays
	element chemical element
	index position



## sort
###### **[sort](#sort)**(arr : any[],  attributeName : string,  isAsc : boolean): void :
[Static] Sorted by asc (ignore case)
##### Parameters
	arr Arrays
	attributeName Name of the property
	isAsc Whether to sort in positive order



## compare
###### **[compare](#compare)**(aArr : any[],  bArr : any[]) :
[Static] Compare, list the different elements in array B relative to array A
##### Parameters
	aArr A-array
	bArr B-array
	appended List of added elements
	subtract List of reduced elements



## getTreeNodeArray
###### **[getTreeNodeArray](#getTreeNodeArray)**(treeNode : any,  childrenAttr? : string,  arrayList? : any[],  checkIsOpen? : boolean,  isOpenAttr? : string,  ignoreChildrenCondition? : Callback): any[] :
[Static] Get the list of child nodes in all nodes under the tree structure (including its own nodes)
##### Parameters
	reeNode Tree structure nodes
	childrenAttr [optional] default="children" as in "children"
	arrayList [Optional] Default=null Array of loaded data
	checkIsOpen [Optional] Default=false Whether to check the open status, if so, the unopened data will not be counted in the return list
	isOpenAttr [Optional] Default="isOpen" Name of the open status attribute
	ignoreChildrenCondition [Optional] Default=null Ignore child object conditions such asignoreChildrenCondition(treeNode: any){return treeNode.ignoreChildren;}





