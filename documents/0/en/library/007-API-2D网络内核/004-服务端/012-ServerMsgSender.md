# ServerMsgSender Network message sender
>Used to send messages to the client, while encapsulating the ability to call client methods directly (RPC)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-21

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Properties
|<div style="width:1000px;text-align:left" >Properties</div>   |
| ---  |
| **[send](#send)**(player : ServerPlayer,  msg : string): void<br>[Static] Sending String Messages
| **[eval](#eval)**(player : ServerPlayer,  code : string): void<br>[Static] Let the client execute the code
| **[rpc](#rpc)**(player : ServerPlayer,  className : string,  funcName : string,  params : any[]): void<br>【[Static] Remote Calling of Client Methods

## Details



## send
###### **[send](#send)**(player : ServerPlayer,  msg : string): void :
[Static] Sending String Messages
##### Parameters
	player Player
	msg String Message



## eval
###### **[eval](#eval)**(player : ServerPlayer,  code : string): void :
[Static] Let the client execute the code
##### Parameters
	player Player
	code Client code



## rpc
###### **[rpc](#rpc)**(player : ServerPlayer,  className : string,  funcName : string,  params : any[]): void :
[Static] Remote Calling of Client Methods
##### Parameters
	className Class Name
	funcName Method name
	params Parameters





