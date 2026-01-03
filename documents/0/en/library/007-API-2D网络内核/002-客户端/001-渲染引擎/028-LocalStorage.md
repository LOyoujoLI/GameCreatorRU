# LocalStorage Browser Cache
>Used for data storage without time limit, similar to permanent cookies for web pages, which will be invalidated by clearing the cache or changing the browser<br>Storage and reading are synchronized, so you can code up and down operations<br>== Usage ==<br>var a = {b:123,c:456,d:"gamecreator"};<br>// Cache<br>LocalStorage.setJSON("myKey",a);<br>// Read Cache<br>LocalStorage.getJSON("myKey",b);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **items** : any;<br>[Static] Data list.  |
| **support** : boolean;<br>[Static] Indicates whether LocalStorage is supported.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setItem](#setItem)**(key : string,  value : string): void<br>[Static] Store the specified key name and key value, string type.
| **[getItem](#getItem)**(key : string): string<br>[Static] Get the value of the specified key name.
| **[setJSON](#setJSON)**(key : string,  value : any): void<br>Static] Store the specified key name and its corresponding Object type value.
| **[getJSON](#getJSON)**(key : string): any<br>Static] Get the value of Object type corresponding to the specified key name.
| **[removeItem](#removeItem)**(key : string): void<br>[Static] Delete the information of the specified key name.
| **[clear](#clear)**(): void<br>[Static] Clear the local storage information.

## Details



## setItem
###### **[setItem](#setItem)**(key : string,  value : string): void :
[Static] Store the specified key name and key value, string type.
##### Parameters
	key Key Name.
	value Key value.



## getItem
###### **[getItem](#getItem)**(key : string): string :
[Static] Get the value of the specified key name.
##### Parameters
	key Key Name.

##### Return
String type value.

## setJSON
###### **[setJSON](#setJSON)**(key : string,  value : any): void :
Static] Store the specified key name and its corresponding Object type value.
##### Parameters
	key Key Name.
	value The key value. is an Object type, this is converted to a JSON string for storage.



## getJSON
###### **[getJSON](#getJSON)**(key : string): any :
Static] Get the value of Object type corresponding to the specified key name.
##### Parameters
	key Key Name.

##### Return
Object Type Value

## removeItem
###### **[removeItem](#removeItem)**(key : string): void :
[Static] Delete the information of the specified key name.
##### Parameters
	key Key Name.



## clear
###### **[clear](#clear)**(): void :
[Static] Clear the local storage information.





