# ServerThread Server thread operation
>Due to the single-process multi-threaded architecture of the server, some thread synchronization and other functions are included here<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-14

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **MAIN_THREAD_ID** : number;<br>[Static] Main Thread-ID Default=2  |
| **threadID** : number;<br>[Static] [Read-only] Get current thread ID  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[callFunction](#callFunction)**(threadID : number,  funcDomain : string,  funcName : string,  params : any[],  onReturn? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void<br>[Static] Call the function of the specified thread
| **[callAllThreadFunction](#callAllThreadFunction)**(funcDomain : string,  funcName : string,  params : any[],  excludeSelfThread? : boolean): void<br>[Static] Calling functions of all threads
| **[syncCode](#syncCode)**(code : string,  excludeSelfThread : boolean): void<br>[Static] Synchronize the world code and let all other threads that are not the current thread execute the code (including the main thread)
| **[getSceneThread](#getSceneThread)**(sceneID : number): number<br>[Static] Get the thread where the scene is located

## Details



## callFunction
###### **[callFunction](#callFunction)**(threadID : number,  funcDomain : string,  funcName : string,  params : any[],  onReturn? : [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)): void :
[Static] Call the function of the specified thread
##### Parameters
	threadID The specified thread ID
	funcDomain The specified domain, such as ServerWrold
	funcName The name of the specified function, such as happenVarChange
	params Parameter set
	onReturn [Optional] Default=null Function callback, if present, means that the value is returned after the function is executed in the specified thread



## callAllThreadFunction
###### **[callAllThreadFunction](#callAllThreadFunction)**(funcDomain : string,  funcName : string,  params : any[],  excludeSelfThread? : boolean): void :
[Static] Calling functions of all threads
##### Parameters
	funcDomain The specified domain, such as ServerWrold
	funcName The name of the specified function, such as happenVarChange
	params Parameter set
	excludeSelfThread [Optional] Default=false Whether to exclude the thread it is in



## syncCode
###### **[syncCode](#syncCode)**(code : string,  excludeSelfThread : boolean): void :
[Static] Synchronize the world code and let all other threads that are not the current thread execute the code (including the main thread)<br>
For example, data within an array that modifies world data needs to be synchronized<br>
ServerWorld.data.arr[5] = 666;
##### Parameters
	code Executed code
	excludeSelfThread Whether to exclude the current thread



## getSceneThread
###### **[getSceneThread](#getSceneThread)**(sceneID : number): number :
[Static] Get the thread where the scene is located
##### Parameters
	sceneID Scene ID

##### Return
[number] Thread ID



