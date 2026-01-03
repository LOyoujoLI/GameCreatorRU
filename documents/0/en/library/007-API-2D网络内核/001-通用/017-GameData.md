# GameData Custom modules for game data classes
>After the producer has updated the data, the format of the player's data from the archive will be corrected after reading.<br>For example, if properties or data formats that are not available in older versions of the archive are modified, the preset default values are used<br>-- If there is no age attribute, the default value of the age attribute is 10 after the producer modified it, then the value is 10 after the player reads the file<br>-- If the original age property exists, numeric type, the archive value is 20, the producer modified age is a string type, the default value is "kds", then the player reads the file after the age value is "kds"<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-08-16

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getModuleData](#getModuleData)**(moduleID : number,  dataID : number): any<br>[Static] Get the system preset custom module data model
| **[newModuleData](#newModuleData)**(moduleID : number,  dataID : number,  isCopy? : boolean): any<br>[Static] New data for a specified module
| **[changeModuleDataToCopyMode](#changeModuleDataToCopyMode)**(data : any,  moduleID : number): void<br>[Static] Change the module data to copy mode, use this function to convert the data of the reference relationship to copy
| **[isCopyModeData](#isCopyModeData)**(data : any): boolean<br>[Static] Determining whether data is copy mode
| **[getLength](#getLength)**(moduleID : number,  typeID? : number): number<br>[static] to get the total length of the data of the specified module (the editor's change maximum for the module can be modified)

## Details



## getModuleData
###### **[getModuleData](#getModuleData)**(moduleID : number,  dataID : number): any :
[Static] Get the system preset custom module data model<br>
The system generates a set of pre-defined data for access or reference during initialization, for example, if a module of [props] is made and populated with 10 prop data.<br>
Then the system will automatically generate these 10 props data when the game is running, through this method you can get
##### Parameters
	moduleID Custom Module ID 1-N (refer to Editor Menu - Custom Editor - Module Maker)
	dataID ID of the data

##### Return
[Module_???] Returns a custom module type, based on the module name (e.g. Module_Actor)

## newModuleData
###### **[newModuleData](#newModuleData)**(moduleID : number,  dataID : number,  isCopy? : boolean): any :
[Static] Create a new data of a specified module<br> 
If it is copy data: the data is disconnected from the original data, the change of the original data will not affect the change of this data, the value of this data comes from the archived value. <br> 
For example, if a piece of equipment has +10 original attack, and the attack of the very best equipment is +15, the attack of that equipment is still 15 even after adjusting the original data attack to 25<br> 
If it is not copy data: the relationship is referenced to the original data, and the data still uses the value of the original model data. <br> 
For example, if a piece of equipment has an original attack of +10, and you get it and the designer adjusts the attack to 25, the piece of equipment will automatically become an attack of +25
##### Parameters
	moduleID Custom Module ID 1-N
	dataID Data ID
	isCopy [Optional] Default = true Whether to be a copy of the data

##### Return
[Module_???] Returns a custom module type

## changeModuleDataToCopyMode
###### **[changeModuleDataToCopyMode](#changeModuleDataToCopyMode)**(data : any,  moduleID : number): void :
[Static] Change the module data to copy mode, use this function to convert the data of the reference relationship to copy
##### Parameters
	data Module Data
	moduleID Module Number



## isCopyModeData
###### **[isCopyModeData](#isCopyModeData)**(data : any): boolean :
[Static] Determining whether data is copy mode
##### Parameters
	data Module Data

##### Return
Whether copy mode

## getLength
###### **[getLength](#getLength)**(moduleID : number,  typeID? : number): number :
[static] to get the total length of the data of the specified module (the editor's change maximum for the module can be modified)<br>
Such as getting the total data length of the custom module [prop]
##### Parameters
	moduleID Custom Module ID 1-N
	typeID [Optional] Default = 1 Type 1-16

##### Return
[number] Total data length



