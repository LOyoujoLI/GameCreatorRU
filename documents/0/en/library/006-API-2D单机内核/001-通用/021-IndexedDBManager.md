# IndexedDBManager Browser IndexedDB mass storage method (asynchronous storage)
>Maintenance personnel:**JayLen**  
>Created on 2021-06-18

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **indexedDB** : IDBFactory;<br>[Static] Database  |
| **support** : boolean;<br>[Static] indicates whether to support  |
| **used** : boolean;<br>[Static] Whether to use IndexedDB mass storage method  |
| **databaseName** : string;<br>[Static] Database name  |
| **version** : number;<br>[Static] Database version number  |
| **tableName** : string;<br>[Static] Form Name  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setIndexDB](#setIndexDB)**(key : string,  value : string,  onFin? : Function): void<br>[Static] Store the specified key name and its corresponding value.
| **[getIndexDB](#getIndexDB)**(key : string,  onFin : Function): void<br>[Static] Get the value corresponding to the specified key name
| **[setIndexDBJson](#setIndexDBJson)**(key : string,  value : any,  onFin? : Function): void<br>[Static] Store the specified key name and its corresponding value.
| **[getIndexDBJson](#getIndexDBJson)**(key : string,  onFin : Function): void<br>[Static] Get the value corresponding to the specified key name
| **[removeIndexDBItem](#removeIndexDBItem)**(key : string,  onFin? : Function): void<br>[Static] Delete the data with specified key name
| **[items](#items)**(onFin : Function): void<br>[Static] Get all data
| **[clear](#clear)**(onFin? : Function): void<br>[Static] Clear the local storage information.

## Details



## setIndexDB
###### **[setIndexDB](#setIndexDB)**(key : string,  value : string,  onFin? : Function): void :
[Static] Store the specified key name and its corresponding value.
##### Parameters
	key key name
	value Key value (string type)
	onFin [Optional] Default=null Callback function onFin(success:boolean)



## getIndexDB
###### **[getIndexDB](#getIndexDB)**(key : string,  onFin : Function): void :
[Static] Get the value corresponding to the specified key name
##### Parameters
	key key name
	onFin Callback onFin(value:string)



## setIndexDBJson
###### **[setIndexDBJson](#setIndexDBJson)**(key : string,  value : any,  onFin? : Function): void :
[Static] Store the specified key name and its corresponding value.
##### Parameters
	key key name
	value Key value (Object type, will be converted to JSON string storage)
	onFin [Optional] Default=null Callback function onFin(success:boolean)



## getIndexDBJson
###### **[getIndexDBJson](#getIndexDBJson)**(key : string,  onFin : Function): void :
[Static] Get the value corresponding to the specified key name
##### Parameters
	&nbsp;key key name
	&nbsp;onFin Callback functions onFin(value:any)



## removeIndexDBItem
###### **[removeIndexDBItem](#removeIndexDBItem)**(key : string,  onFin? : Function): void :
[Static] Delete the data with specified key name
##### Parameters
	key key name
	onFin [Optional] Default=null Callback onFin(success:boolean)



## items
###### **[items](#items)**(onFin : Function): void :
[Static] Get all data
##### Parameters
	onFin Callback onFin(items:{})



## clear
###### **[clear](#clear)**(onFin? : Function): void :
[Static] Clear the local storage information.
##### Parameters
	onFin [Optional] Default=null Callback onFin(success:boolean)





