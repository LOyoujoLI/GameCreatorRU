# Player Player Base Class
>Support for custom attributes, i.e. attributes preset in the player settings: for example, the player backpack in RPG games is a custom player attribute.<br>&nbsp;&nbsp;-- Visually edit custom attributes: Menu - Custom Editor - Player Attribute Edit<br>&nbsp;&nbsp;-- The archive will automatically include these custom properties<br>Support player variables: numeric variables, switch variables, string variables:<br>&nbsp;&nbsp;-- The archive will automatically include player variables<br>&nbsp;&nbsp;-- Player variable changes will automatically affect places such as variable controls in the interface.<br>The player comes with a scene object data by default:<br>&nbsp;&nbsp;-- When switching scenes, the scene object this.sceneObject will be destroyed, and the base data and custom data will be written to the data this.data.sceneObject<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;And after the switch, a new scene object is created again this.sceneObject<br>&nbsp;&nbsp;-- 存The file will automatically contain the player's display object data (base data [SceneObject] + custom data for the scene object)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-05-22

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **key** : string;<br>Unique key  |
| **uid** : number;<br>Unique uid  |
| **data** : PlayerData;<br>Player properties: contains custom properties and player's scene object data (base data [SceneObject] + custom data of the scene object)  |
| **variable** : Variable;<br>Player variables: contains numeric variables, switch variables, string variables  |
| **sceneObject** : SceneObjectEntity;<br>Player's scene object entity  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[toScene](#toScene)**(sceneID : number,  x? : number,  y? : number): void<br>Enter the specified scene

## Details



## toScene
###### **[toScene](#toScene)**(sceneID : number,  x? : number,  y? : number): void :
Enter the specified scene
##### Parameters
	sceneID Scene ID
	x [Optional] Default value = 0 Actual coordinate x
	y [Optional] Default value = 0 Actual coordinate y





