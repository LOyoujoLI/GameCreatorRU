# AsynTask Asynchronous task tool class
>Multiple tasks at the same time, need to wait until all tasks are executed before calling back<br>Usage:<br>&nbsp;var task = new AsynTask(Callback.New(() => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Logical processing at the end of all tasks<br>&nbsp;}, this));<br>&nbsp;task.execute(Arbitrary expressions); // 如 task.execute(1);<br>&nbsp;task.execute(Arbitrary expressions);<br>&nbsp;task.complete(); // Two tasks are performed above, and the following needs to be completed twice to be considered complete<br>&nbsp;task.complete();<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **length** : number;<br>Total number of tasks  |
| **currentCount** : number;<br>Number of currently executed tasks  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(onFin : Callback)<br>Asynchronous Constructors
| **[execute](#execute)**(code : any): void<br>Execution
| **[complete](#complete)**(): void<br>Callback on completion

## Details



## constructor
###### **[constructor](#constructor)**(onFin : Callback) :
Asynchronous Constructors
##### Parameters
	onFin Callback Methods
	thisPtr Scope



## execute
###### **[execute](#execute)**(code : any): void :
Execution
##### Parameters
	code Just execute the code directly, just append the count here



## complete
###### **[complete](#complete)**(): void :
Callback on completion





