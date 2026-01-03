# ClientWorld Game World - Client
>Possession of characteristics：<br>-- Custom world properties: The editor supports custom setting of world properties, accessed here via ClientWorld.data<br>-- Access to global variables (single-player kernel indicates two-week variables, network version indicates variables that are common to all players)<br>-- Standalone kernel for event library, full interface event management<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-06-02

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **EVENT_INITED** : string;<br>[Static] event: engine initialization is complete (only when the game is running) default value = "ClientMain_EVENT_INITED"  |
| **EVENT_BEHAVIOR_VIEW_INITED** : string;<br>[Static] Event: Behavior Editor preview side initialized Default="BehaviorViewClientWorldInited"  |
| **[EVENT_STRING_MESSAGE](#EVENT_STRING_MESSAGE)** : string;<br>[Static] Event: Receiving string messages  |
| **data** : typeof WorldData;<br>[Static] World Data  |
| **[variable](#variable)** : Variable;<br>[Static] Event variable local cache, the value obtained is the most recent value from the server (if it has been listened to, it is close to the latest value)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[startLogin](#startLogin)**(onLoginSuccess : Callback,  onLoginFail? : Callback): void<br>[Static] Login
| **[logout](#logout)**(): void<br>[Static] Logout
| **[requestGetVariable](#requestGetVariable)**(type : number,  varID : number,  onResponse : Callback): void<br>[Static] Request for world variables

## Details

### EVENT_STRING_MESSAGE
###### EVENT_STRING_MESSAGE : string;
[Static] Event: Receiving string messages<br>
EventUtils.addEventListener(ClientMain); callback(msg:string)
### variable
###### variable : Variable;
[Static] Event variable local cache, the value obtained is the most recent value from the server (if it has been listened to, it is close to the latest value)<br>
-- Automatically listens if a variable is placed in the interface<br>
-- The script is called to actively listen to the


## startLogin
###### **[startLogin](#startLogin)**(onLoginSuccess : Callback,  onLoginFail? : Callback): void :
[Static] Login
##### Parameters
	onLoginSuccess Callback after successful connection
	onLoginFail [optional] default=null Callback on failure/disconnection when login fails onLoginFail(isTimeout:boolean) isTimeout whether from timeout, otherwise it should be that the server is full



## logout
###### **[logout](#logout)**(): void :
[Static] Logout



## requestGetVariable
###### **[requestGetVariable](#requestGetVariable)**(type : number,  varID : number,  onResponse : Callback): void :
[Static] Request for world variables<br>
Requires server call ServerWorld.setWorldVariableAccessible The variable is whitelisted before it is allowed to be acquired
##### Parameters
	type 0-World variable 1-World switch 2-World string
	varID Variable ID
	onResponse rotation onResponse(isSuccess:boolean,type:number,varID:number,value:number|string);





