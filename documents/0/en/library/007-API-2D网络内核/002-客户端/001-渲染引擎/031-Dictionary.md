# Dictionary Data Dictionary
>Can be used for key-value pairs that are not strings as keys (similar to an object's memory address as a key)<br>Ordinary key-value pairs are string storage keys, such as {a:123}, in which a is the string "a", while if you want to use an object as a key, you can use this type<br>Use the native JS implementation of Map<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **values** : Array<any>;<br>[Read-only] Get a list of all child elements.  |
| **keys** : Array<any>;<br>[Read-only] Get a list of all child element key names.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[set](#set)**(key : any,  value : any): void<br>Sets the value for the specified key name.
| **[indexOf](#indexOf)**(key : any): number<br>Get the key name index of the specified object.
| **[get](#get)**(key : any): any<br>Returns the value of the specified key name.
| **[remove](#remove)**(key : any): boolean<br>Removes the value of the specified key name.
| **[clear](#clear)**(): void<br>Clears the list of key names and the list of key values for this object.

## Details



## set
###### **[set](#set)**(key : any,  value : any): void :
Sets the value for the specified key name.<br>
@param	key Key Name.<br>
@param	value Value.



## indexOf
###### **[indexOf](#indexOf)**(key : any): number :
Get the key name index of the specified object.<br>
@param	key Key name object.

##### Return
Key name index.

## get
###### **[get](#get)**(key : any): any :
Returns the value of the specified key name.<br>
@param	key Key name object.

##### Return
Specifies the value of the key name.

## remove
###### **[remove](#remove)**(key : any): boolean :
Removes the value of the specified key name.<br>
@param	key Key name object.

##### Return
Whether the removal was successful.

## clear
###### **[clear](#clear)**(): void :
Clears the list of key names and the list of key values for this object.





