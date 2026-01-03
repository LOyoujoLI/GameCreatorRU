# Variable Collection of variables
>Contains numeric variables, string variables, and switch variables<br>There are global variables (or two-week variables for the standalone version) and player variables<br>&nbsp;-- About the standalone kernel-Second-cycle variables: do not change with the reading of the file, but throughout the game.<br>&nbsp;-- About the Web-based Kernel-Global variables: variables for the whole world, all players access the same world variables<br>Changes to variables can affect some components and scene objects that have emergent conditions<br>The system is designed to listen for changes in variables, and the corresponding places are automatically synchronized when the variables change.<br>&nbsp;-- Interface controls: some components can bind variables, and after binding the variable changes will automatically display the latest value without additional implementation<br>&nbsp;&nbsp;&nbsp;&nbsp;-- Player value variable component [UIVariable]<br>&nbsp;&nbsp;&nbsp;&nbsp;-- Player switch variable components [UISwitch]<br>&nbsp;&nbsp;&nbsp;&nbsp;-- Text component (can bind player string variables) [UIString]<br>&nbsp;-- The client script actively listens for changes in player variables, refer to [ClientPlayer]<br>&nbsp;-- The stand-alone version supports listening to two weekly variables, the network version only supports one acquisition, refer to [ClientWorld]<br>Classes that carry variables: player ([Player](?file=006-API-2D单机内核/001-通用/022-Player)), World ([ClientWorld]、[ServerWorld])<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-04-17

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getVariable](#getVariable)**(varID : number): number<br>Get numeric variables
| **[setVariable](#setVariable)**(varID : number,  v : number): void<br>Set numeric variables
| **[getSwitch](#getSwitch)**(varID : number): number<br>Get switch variables
| **[setSwitch](#setSwitch)**(varID : number,  v : number): void<br>Set switch variables
| **[getString](#getString)**(varID : number): string<br>Get string variables
| **[setString](#setString)**(varID : number,  v : string): void<br>Set string variables

## Details



## getVariable
###### **[getVariable](#getVariable)**(varID : number): number :
Get numeric variables
##### Parameters
	index Variable ID



## setVariable
###### **[setVariable](#setVariable)**(varID : number,  v : number): void :
Set numeric variables
##### Parameters
	varID Variable ID
	v Numerical value



## getSwitch
###### **[getSwitch](#getSwitch)**(varID : number): number :
Get switch variables
##### Parameters
	varID Variable ID



## setSwitch
###### **[setSwitch](#setSwitch)**(varID : number,  v : number): void :
Set switch variables
##### Parameters
	index Variable ID
	v Switch value 0-Off 1-On



## getString
###### **[getString](#getString)**(varID : number): string :
Get string variables
##### Parameters
	varID Variable ID



## setString
###### **[setString](#setString)**(varID : number,  v : string): void :
Set string variables
##### Parameters
	varID Variable ID
	v String Value





