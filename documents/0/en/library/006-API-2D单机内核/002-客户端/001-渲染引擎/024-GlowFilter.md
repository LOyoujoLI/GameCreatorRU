# GlowFilter Luminous filter
>Can also be used as a shadow filter<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[Filter](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/021-Filter)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **offY** : number;<br>Offset in X-axis direction  |
| **offX** : number;<br>Offset in Y-axis direction  |
| **blur** : number;<br>Degree of ambiguity  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(color : string,  blur? : number,  offX? : number,  offY? : number)<br>Create Glow Filter
| **[getColor](#getColor)**(): Array<any><br>Get the color format in array form [R,G,B,A] range 0~1

## Details



## constructor
###### **[constructor](#constructor)**(color : string,  blur? : number,  offX? : number,  offY? : number) :
Create Glow Filter<br>
@param	color	Color of the filter<br>
@param	blur	Size of edge blur Default = 4<br>
@param	offX	Offset in X-axis direction Default = 6<br>
@param	offY	Offset in Y-axis direction Default value = 6



## getColor
###### **[getColor](#getColor)**(): Array<any> :
Get the color format in array form [R,G,B,A] range 0~1

##### Return
[Array]



