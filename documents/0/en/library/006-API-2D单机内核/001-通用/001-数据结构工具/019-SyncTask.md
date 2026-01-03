# SyncTask Synchronized Task Tools
>Tasks of the same type can only be executed sequentially, and the tasks that follow are in a waiting state until the current task is completed.<br>Usage:<br>var taskName = "My Synchronization Task 1";<br>// The first synchronized task, and tasks of the same type will wait until the execution of that task is completed before proceeding<br>new SyncTask(taskName, function () {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// 1st sequential task logic<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;xxxxxxxxxxxxx<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// The first sequential task is executed<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SyncTask.taskOver(taskName);<br>});<br>// The second synchronized task, of the same type, will wait until the task is finished before proceeding<br>new SyncTask(taskName, function () {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// 2nd sequential task logic<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;xxxxxxxxxxxxx<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// The 2nd sequential task is executed<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SyncTask.taskOver(taskName);<br>});<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **func** : Function;<br>Methods  |
| **arg** : any[];<br>Parameters  |
| **thisPtr** : any;<br>this pointer  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(taskName : string,  func? : Function,  arg? : any[],  thisPtr? : any,  isConver? : boolean,  jumpQuere? : boolean)<br>Synchronized Task Execution Constructor
| **[taskOver](#taskOver)**(taskName : string): void<br>[Static] Notify the completion of a certain type of task and proceed directly to the next task of the same type
| **[clear](#clear)**(taskName : string): void<br>[Static] Clearing tasks

## Details



## constructor
###### **[constructor](#constructor)**(taskName : string,  func? : Function,  arg? : any[],  thisPtr? : any,  isConver? : boolean,  jumpQuere? : boolean) :
Synchronized Task Execution Constructor
##### Parameters
	taskName Task name
	func Method to execute [optional] Default=null
	arg Parameters [optional] Default=null Parameters carried by the callback function
	thisPtr scope [optional] default=null
	isConver [Optional] Default=false Will duplicate tasks be overwritten
	jumpQuere [Optional] Default=false Whether to cut the queue or not, and if so, to the front



## taskOver
###### **[taskOver](#taskOver)**(taskName : string): void :
[Static] Notify the completion of a certain type of task and proceed directly to the next task of the same type
##### Parameters
	taskName Task name



## clear
###### **[clear](#clear)**(taskName : string): void :
[Static] Clearing tasks
##### Parameters
	taskName Task name





