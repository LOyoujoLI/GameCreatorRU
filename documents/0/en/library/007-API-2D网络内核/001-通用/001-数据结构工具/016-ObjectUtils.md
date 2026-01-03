# ObjectUtils Object Tool Class
>Common functions for GC internally wrapped objects<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-24

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getInstanceID](#getInstanceID)**(): number<br>[Static] Get unique ID: the value is automatically accumulated from 0 after the program starts, to ensure that each ID is unique, but not suitable for storage
| **[getRandID](#getRandID)**(): string<br>[static] Get random unique ID: suitable for storage, basically will not encounter the same ID value
| **[clone](#clone)**(form : any,  to : any): void<br>[Static] Cloning A's properties to B (direct setting)
| **[cloneExcludeNonExistentAttribute](#cloneExcludeNonExistentAttribute)**(form : any,  to : any): void<br>[Static] Clone the attributes of A to B, only for the attributes that exist in B
| **[depthClone<T>](#depthClone<T>)**(o : T): T<br>[Static] Deep Cloning Properties
| **[same](#same)**(a : any,  b : any): boolean<br>[Static] Determining if two objects are different Iterating over the properties of a is the same as b
| **[depthSame](#depthSame)**(a : any,  b : any): boolean<br>[Static] Determining if two objects are different Iterating over the properties of a is the same as b Deep comparison
| **[assignment](#assignment)**(a : any,  b : any): void<br>[Static] Assignment, assigning the value of B to A, without changing the type
| **[reDefineGetSet](#reDefineGetSet)**(target : string,  defineContent : any): void<br>[Static] Redefining get/set
| **[redefinedEventFunc](#redefinedEventFunc)**(clsName : string,  types : string[],  toObjName : string): void<br>[Static] Mapping specified class event-related methods, replacing types with methods of specified objects

## Detailss



## getInstanceID
###### **[getInstanceID](#getInstanceID)**(): number :
[Static] Get unique ID: the value is automatically accumulated from 0 after the program starts, to ensure that each ID is unique, but not suitable for storage



## getRandID
###### **[getRandID](#getRandID)**(): string :
[Static] Get random unique ID: suitable for storage, basically will not encounter the same ID value



## clone
###### **[clone](#clone)**(form : any,  to : any): void :
[Static] Cloning A's properties to B (direct setting)<br>
>// Internal Implementation<br>
>for (var i in form) {<br>
>&nbsp;&nbsp;&nbsp;&nbsp;to[i] = form[i];<br>
>}<br>
>


##### Parameters
	a Object A - Data Source
	b Object B - the object to which the value is assigned



## cloneExcludeNonExistentAttribute
###### **[cloneExcludeNonExistentAttribute](#cloneExcludeNonExistentAttribute)**(form : any,  to : any): void :
[Static] Clone the attributes of A to B, only for the attributes that exist in B<br>
>// Internal Implementation<br>
>for (var i in to) {<br>
>&nbsp;&nbsp;&nbsp;to[i] = form[i];<br>
>}<br>
>


##### Parameters
	a Object A - Data Source
	b Object B - the object to which the value is assigned



## depthClone<T>
###### **[depthClone<T>](#depthClone<T>)**(o : T): T :
[Static] Deep Cloning Properties
##### Parameters
	o Objects that need to be cloned, data that can be JSONized



## same
###### **[same](#same)**(a : any,  b : any): boolean :
[Static] Determining if two objects are different Iterating over the properties of a is the same as b
##### Parameters
	a Object A
	b Object B

##### Return
Is the same

## depthSame
###### **[depthSame](#depthSame)**(a : any,  b : any): boolean :
[Static] Determining if two objects are different Iterating over the properties of a is the same as b Deep comparison
##### Parameters
	a 对象A
	b 对象B

##### Return
Is the same

## assignment
###### **[assignment](#assignment)**(a : any,  b : any): void :
[Static] Assignment, assigning the value of B to A, without changing the type<br>
-- Only attributes that exist in B will be assigned<br>
-- Keep the type of A unchanged (so that the methods under that type can be preserved)
##### Parameters
	a Object
	b object



## reDefineGetSet
###### **[reDefineGetSet](#reDefineGetSet)**(target : string,  defineContent : any): void :
[Static] Redefining get/set
##### Parameters
	target Target audience
	defineContent {x:function(v){code}}



## redefinedEventFunc
###### **[redefinedEventFunc](#redefinedEventFunc)**(clsName : string,  types : string[],  toObjName : string): void :
[Static] Mapping specified class event-related methods, replacing types with methods of specified objects
##### Parameters
	clsName Class Object
	types Collection of types to be replaced
	toObjName Specify the name of the object to replace to





