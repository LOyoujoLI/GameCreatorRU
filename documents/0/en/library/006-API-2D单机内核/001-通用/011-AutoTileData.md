# AutoTileData Automatic component data
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-06-08

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **url** : string;<br>Image path  |
| **[dataLayers](#dataLayers)** : number[];<br>Data layer data - as the automatic component is considered only one cell Default = []  |
| **[GCATMode](#GCATMode)** : number;<br>Specification mode  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getAutoTileData](#getAutoTileData)**(texID : number): [AutoTileData](?file=006-API-2D单机内核/001-通用/011-AutoTileData)<br>[Static] Used at runtime to get block data

## Details

### dataLayers
###### dataLayers : number[];
Data layer data - as the automatic component is considered only one cell Default = []<br>
[dataGridIndex] = 1/0
### GCATMode
###### GCATMode : number;
Specification mode<br>
0-Specifications of GCAT1


## getAutoTileData
###### **[getAutoTileData](#getAutoTileData)**(texID : number): [AutoTileData](?file=006-API-2D单机内核/001-通用/011-AutoTileData) :
[Static] Used at runtime to get block data
##### Parameters
	texID Numbering of automatic components (1~N)





