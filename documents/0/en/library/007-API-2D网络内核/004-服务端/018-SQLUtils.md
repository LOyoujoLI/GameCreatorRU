# SQLUtils Database manipulation tools
>Encapsulates the addition, deletion and modification of MYSQL<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on:2018-01-12

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Methods
|<div style="width:1000px;text-align:left" >Methods</div>   |
| ---  |
| **[query](#query)**(tableName : string,  params : string,  condition : string): any[]<br>[Static] Query Data
| **[insert](#insert)**(tableName : string,  sqlObj : any): boolean<br>[Static] Insert single data
| **[update](#update)**(tableName : string,  sqlObj : any,  where : string): boolean<br>[Static] Update single data
| **[delete_data](#delete_data)**(tableName : string,  condition : string): boolean<br>[Static] Delete data
| **[safely_mysql_insert](#safely_mysql_insert)**(tableName : string,  data : string): boolean<br>[Static] [Secure] Insert data
| **[safely_mysql_delete](#safely_mysql_delete)**(tableName : string,  condition : string): boolean<br>[Static] [Security Version] Delete Data
| **[safely_mysql_update](#safely_mysql_update)**(tableName : string,  condition : string): boolean<br>[Static] [Security Version] Update Data

## Details



## query
###### **[query](#query)**(tableName : string,  params : string,  condition : string): any[] :
[Static] Query Data<br>
For example, query the varID and varValue of the playervariable table<br>
>var res:{varID:number,varValue:number}[] = SQLUtils.query("playervariable", "varID,varValue", "where uid=5") as any[];<br>
>trace("Query to data entry",res.length);<br>
>


##### Parameters
	tableName Table Name
	params Parameters
	condition terms
	Data object: data whose keys correspond to the parameters of the table

##### Return
[any[]] Returns the result, or null if the connection to the database fails

## insert
###### **[insert](#insert)**(tableName : string,  sqlObj : any): boolean :
[Static] Insert single data<br>
&nbsp;-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data<br>
>var isSuccess = SQLUtils.insert("playervariable",{uid:3,varID:5,varValue:678});<br>
>>trace("Whether the insertion is successful",isSuccess);<br>
>


##### Parameters
	tableName Table Name
	sqlObj Data object: data whose keys correspond to the parameters of the table

##### Return
[boolean] Is it successful

## update
###### **[update](#update)**(tableName : string,  sqlObj : any,  where : string): boolean :
[Static] Update single data<br>
-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data<br>
>var isSuccess = SQLUtils.update("playervariable",{varValue:678},"where uid=3 and varID=5");<br>
>trace("Is the update successful",isSuccess);<br>
>


##### Parameters
	tableName Table Name
	sqlObj Data object: data whose keys correspond to the parameters of the table
	where Conditional Statements

##### Return
[boolean] Is it successful

## delete_data
###### **[delete_data](#delete_data)**(tableName : string,  condition : string): boolean :
[Static] Delete data<br>
-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data<br>
>var isSuccess = SQLUtils.delete_data("playervariable","where uid=3 and varID=5");<br>
>trace("Is the update successful",isSuccess);<br>
>


##### Parameters
	tableName Table Name
	condition Conditional statements: such as "where id>5"

##### Return
[boolean] Is it successful

## safely_mysql_insert
###### **[safely_mysql_insert](#safely_mysql_insert)**(tableName : string,  data : string): boolean :
[Static] [Secure] Insert data<br>
-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data
##### Parameters
	tableName Table name table
	data Insert String "(name,age) values('kds',18)"
	
##### Return
[boolean] Is it successful

## safely_mysql_delete
###### **[safely_mysql_delete](#safely_mysql_delete)**(tableName : string,  condition : string): boolean :
[Static] [Security Version] Delete Data<br>
-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data
##### Parameters
	tableName Table Name such as table
	condition Insert String "where id>5"

##### Return
[boolean] Is it successful

## safely_mysql_update
###### **[safely_mysql_update](#safely_mysql_update)**(tableName : string,  condition : string): boolean :
[Static] [Security Version] Update Data<br>
-- If the database cannot be connected it will keep requesting until the connection is successful and then write the data
##### Parameters
	tableName Table Name such as table
	condition Insert String "set name='kds' where id=5"

##### Return
[boolean] Is it successful



