# Callback Callback Methods
>Generally used in various callback functions in order to carry execution fields and parameters<br>[How to use]:<br>Callback.New(this.xxx,this,[1,2,3]);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **EMPTY** : Callback;<br>[Static] A single instance of empty, generally used for empty implementations in must callbacks  |
| **caller** : any;<br>Caller execution domain  |
| **callbackFunc** : Function;<br>Callback Methods  |
| **args** : any[];<br>Callback parameters  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[run](#run)**(): any<br>Run
| **[runWith](#runWith)**(addArgs : any[]): any<br>Run appending additional parameters The appended parameters are always followed by the callback
| **[delayRun](#delayRun)**(delay : number,  delayFunc? : Function,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)<br>Delayed execution
| **[delayRunConver](#delayRunConver)**(delay : number,  delayFunc? : Function,  clearDelayFunc? : Function,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)<br>Delays execution, but overwrites previous delays
| **[stopDelay](#stopDelay)**(clearDelayFunc? : Function): void<br>Stop extension
| **[New](#New)**(callbackFunc : Function,  caller : any,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback)<br>[Static] New callback object, same as new CallBack
| **[CallLater](#CallLater)**(func : Function,  caller : any,  args? : any[],  delay? : number): void<br>[Static] Deferring execution to the next frame ensures that the same method and scope can only be executed once, which can be used to optimize efficiency
| **[CallLaterBeforeRender](#CallLaterBeforeRender)**(func : Function,  caller : any,  args? : any[]): void<br>[Static] deferring execution to the next rendering, ensuring that the same methods and scopes can only be executed once, which can be used to optimize efficiency

## Details



## run
###### **[run](#run)**(): any :
Run
##### Parameters
	addArgs [Optional] Default=null Additional parameters



## runWith
###### **[runWith](#runWith)**(addArgs : any[]): any :
Run appending additional parameters The appended parameters are always followed by the callback
##### Parameters
	addArgs  Additional parameters



## delayRun
###### **[delayRun](#delayRun)**(delay : number,  delayFunc? : Function,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback) :
Delayed execution
##### Parameters
	delay Number of ms delayed
	delayFunc [optional] default=null delayed function, default setTimeout, can be changed, such as setFrameout
	args [Optional] Default value=null Parameters

##### Return
[Callback]

## delayRunConver
###### **[delayRunConver](#delayRunConver)**(delay : number,  delayFunc? : Function,  clearDelayFunc? : Function,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback) :
Delays execution, but overwrites previous delays
##### Parameters
	delay Number of ms delayed
	delayFunc [optional] default=null delayed function, default setTimeout, can be changed, such as setFrameout
	clearDelayFunc [Optional] Default=null Clear delay function, default clearTimeout, can be replaced, such as setFrameout
	args [Optional] Default value=null Parameters

##### Return
[Callback]

## stopDelay
###### **[stopDelay](#stopDelay)**(clearDelayFunc? : Function): void :
Stop extension
##### Parameters
	clearDelayFunc [Optional] Default=null Clear delay function, default clearTimeout, replaceable



## New
###### **[New](#New)**(callbackFunc : Function,  caller : any,  args? : any[]): [Callback](?file=007-API-2D网络内核/001-通用/001-数据结构工具/013-Callback) :
[Static] New callback object, same as new CallBack
##### Parameters
	callbackFunc Callback Methods
	caller Execution Domain
	args [optional] default=null Parameters carried

##### Return
[Callback]

## CallLater
###### **[CallLater](#CallLater)**(func : Function,  caller : any,  args? : any[],  delay? : number): void :
Static] Deferring execution to the next frame ensures that the same method and scope can only be executed once, which can be used to optimize efficiency<br> 
The same method and scope call this method, only the first time it takes effect, where the args parameter will be replaced with the parameter of the most recent call<br> 
The method may be executed before the next render or after the next render, if you have to be sure that it has to be executed before the next render. Execution can be done using CallLaterBeforeRender<br> 
Internally using setTimeout-0ms
##### Parameters
	func Methods of implementation
	caller Scope
	args [Optional] Default=null Attached parameters
	delay [Optional] Default value = 0 Delayed ms



## CallLaterBeforeRender
###### **[CallLaterBeforeRender](#CallLaterBeforeRender)**(func : Function,  caller : any,  args? : any[]): void :
[static] Deferring execution to the next rendering, ensuring that the same method and scope can only be executed once, which can be used to optimize efficiency<br> 
The same method and scope calling this method will only take effect the first time, where the args argument will be replaced with the argument of the most recent call
##### Parameters
	func Methods of implementation
	caller Scope
	args [Optional] Default=null Attached parameters





