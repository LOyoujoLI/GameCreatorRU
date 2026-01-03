# ClientWorld Game World - Client
<br>-Have features:<br>-- Custom world properties: the editor supports custom setting of world properties, accessed here via ClientWorld.data<br>-- Access to global variables (single player kernel means two-week variables, network version means variables common to all players)<br>-- Single player kernel for event library, interface-wide event management<br><br >
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-06-02

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **EVENT_INITED** : string;<br>[Static] event: engine initialization is complete (only when the game is running) default value = "ClientMain_EVENT_INITED"  |
| **EVENT_BEHAVIOR_VIEW_INITED** : string;<br>[Static] Event: Behavior Editor preview side initialized Default="BehaviorViewClientWorldInited"  |
| **data** : typeof WorldData;<br>[Static] World Customized Data  |
| **variable** : Variable;<br>[Static] Global Variables  |
| **commonEventPages** : CommandPage[];<br>[Static] Event Set of Event Library  |
| **[uiCustomCommandPages](#uiCustomCommandPages)** : {<br>[Static] Interface custom event set id-CommandPage 0~N  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[addListenerVariable](#addListenerVariable)**(type : number,  varID : number,  onChange : Callback): void<br>[Static] Listening when global variables are changed
| **[removeListenerVariable](#removeListenerVariable)**(type : number,  varID : number,  onChange : Callback): void<br>[Static] Cancel Listening: When the global variable is changed

## Details

### uiCustomCommandPages
###### uiCustomCommandPages : {
[Static] Interface custom event set id-CommandPage 0~N<br>
For example, if the interface has a click event and a mouse hover event, then the same control supports two event pages Default = {}


## addListenerVariable
###### **[addListenerVariable](#addListenerVariable)**(type : number,  varID : number,  onChange : Callback): void :
[Static] Listening when global variables are changed<br>
>// Listening to global value variable #2<br>
>ClientWorld.addListenerVariable(0, 2, Callback.New((type: number, varID: number, value: number) => {<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>}, this));<br>
>


##### Parameters
	type 0-variable 1-switch 2-string
	onChange onChange(type:number,varID:number,value:number|string);



## removeListenerVariable
###### **[removeListenerVariable](#removeListenerVariable)**(type : number,  varID : number,  onChange : Callback): void :
[Static] Cancel Listening: When the global variable is changed<br>
>// Listening to global value variable #2<br>
>var cb = Callback.New((type: number, varID: number, value: number) => {<br>
>&nbsp;&nbsp;&nbsp;// to do<br>
>}, this)<br>
>// Cancel Listening<br>
>ClientWorld.addListenerVariable(0, 2, cb);<br>
>


##### Parameters
	type 0-variable 1-switch 2-string
	onChange





