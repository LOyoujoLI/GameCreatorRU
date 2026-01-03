# HitArea Mouse click area
>You can set up a series of vector drawings to be drawn as clickable and non-clickable areas (currently only circles, rectangles, polygons are supported)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **hit** : Graphics;<br>Clickable area, which can be set to draw a series of vector images as a clickable area (supports circles, rectangles, polygons)  |
| **unHit** : Graphics;<br>Non-clickable area, can be set to draw a series of vectors as a non-clickable area (supports circles, rectangles, polygons)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[isHitGraphic](#isHitGraphic)**(x : number,  y : number,  graphic : [Graphics](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/012-Graphics)): boolean<br>[Static] Whether to hit Graphic
| **[ptInPolygon](#ptInPolygon)**(x : number,  y : number,  areaPoints : number[]): boolean<br>[Static] Whether the coordinates are inside the polygon
| **[isHit](#isHit)**(x : number,  y : number): boolean<br>Whether to include a point
| **[contains](#contains)**(x : number,  y : number): boolean<br>Detects if the object contains the specified point.

## Details



## isHitGraphic
###### **[isHitGraphic](#isHitGraphic)**(x : number,  y : number,  graphic : [Graphics](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/012-Graphics)): boolean :
[Static] Whether to hit Graphic
##### Parameters
	x x coordinate
	y y coordinate
	graphic Graphics source

##### Return
[boolean]

## ptInPolygon
###### **[ptInPolygon](#ptInPolygon)**(x : number,  y : number,  areaPoints : number[]): boolean :
[Static] Whether the coordinates are inside the polygon
##### Parameters
	x x coordinate
	y y coordinate
	areaPoints Format [x1,y1,x2,y2...]

##### Return
[boolean]

## isHit
###### **[isHit](#isHit)**(x : number,  y : number): boolean :
Whether to include a point
##### Parameters
	x x coordinate
	y y coordinate

##### Return
Whether to click to

## contains
###### **[contains](#contains)**(x : number,  y : number): boolean :
Detects if the object contains the specified point.<br>
@param	x	The X-axis coordinate value (horizontal position) of the point.<br>
@param	y	The value of the Y-axis coordinate (vertical position) of the point.<br>
@return	The value is true if it contains the specified point; otherwise, it is false.