# TileData Block material configuration data
>Block material data from the editor preset<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-10-16

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **id** : number;<br>Unique ID  |
| **name** : string;<br>name  |
| **url** : string;<br>Image path Default value=""  |
| **dataLayers** : number[][][];<br>Data Layer Data [Custom Data Layer Index][xGrid][yGrid] Default Value=[]  |
| **width** : number;<br>Width Default=0  |
| **height** : number;<br>Height Default=0  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getTileData](#getTileData)**(texID : number): [TileData](?file=006-API-2D单机内核/001-通用/027-TileData)<br>[Static] Get block data

## Details



## getTileData
###### **[getTileData](#getTileData)**(texID : number): [TileData](?file=006-API-2D单机内核/001-通用/027-TileData) :
[Static] Get block data
##### Parameters
	texID Block material ID

##### Return
Block material configuration data



