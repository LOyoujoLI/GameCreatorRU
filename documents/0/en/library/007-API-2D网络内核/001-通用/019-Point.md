# Point Point Object
>denotes the x,y of the two-dimensional coordinate system, used to assist in the calculation<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-06-03

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **x** : number;<br>Horizontal Coordinates  |
| **y** : number;<br>Vertical Coordinates  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(x? : number,  y? : number)<br>Constructors
| **[setTo](#setTo)**(x : number,  y : number): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>Set horizontal and vertical coordinates at once
| **[distance](#distance)**(x : number,  y : number): number<br>Calculates the distance between the current point and the specified point (x, y).
| **[toString](#toString)**(): string<br>Returns the value in the form of a string displaying: x,y
| **[interpolate](#interpolate)**(to : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  from : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  per : number): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>[Static] Return the point in the middle of from-to two points
| **[interpolate2](#interpolate2)**(toX : number,  toY : number,  fromX : number,  fromY : number,  per : number): number[]<br>[Static] Return the point in the middle of from-to two points
| **[distance](#distance)**(from : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  to : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): number<br>[Static] Return the distance between two points of from-to
| **[distance2](#distance2)**(fromX : number,  fromY : number,  toX : number,  toY : number): number<br>[Static] Return the distance between two points of from-to
| **[distanceSquare](#distanceSquare)**(p1 : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  p2 : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): number<br>[Static] Square of distance
| **[distanceSquare2](#distanceSquare2)**(ax : number,  ay : number,  bx : number,  by : number): number<br>[Static] Square of distance

## Details



## constructor
###### **[constructor](#constructor)**(x? : number,  y? : number) :
Constructors
##### Parameters
	x [Optional] Default value = 0 Horizontal coordinates
	y [Optional] Default value = 0 Vertical coordinates



## setTo
###### **[setTo](#setTo)**(x : number,  y : number): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
Set horizontal and vertical coordinates at once
##### Parameters
	x Horizontal Coordinates
	y Vertical Coordinates

##### Return
[Point] Current Object

## distance
###### **[distance](#distance)**(x : number,  y : number): number :
Calculates the distance between the current point and the specified point (x, y).<br>
@param	x The horizontal coordinate of the specified point.<br>
@param	y The vertical coordinate of the specified point.<br>
@return	Returns the distance between the current point and the specified point.



## toString
###### **[toString](#toString)**(): string :
Returns the value in the form of a string displaying: x,y

##### Return
[string]

## interpolate
###### **[interpolate](#interpolate)**(to : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  from : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  per : number): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
[Static] Return the point in the middle of from-to two points
##### Parameters
	to Target Points
	from starting point
	per The ratio of from-to 0~1, 0 is equal to from, 1 is equal to to

##### Return
[Point]

## interpolate2
###### **[interpolate2](#interpolate2)**(toX : number,  toY : number,  fromX : number,  fromY : number,  per : number): number[] :
[Static] Return the point in the middle of from-to two points
##### Parameters
	toX Target point x
	toY Target point y
	fromX Starting point x
	fromY Starting point y
	per The ratio of from-to 0~1, 0 is equal to from, 1 is equal to to

##### Return
[number]

## distance
###### **[distance](#distance)**(from : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  to : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): number :
[Static] Return the distance between two points of from-to
##### Parameters
	from starting point
	to Endpoint

##### Return
[number]

## distance2
###### **[distance2](#distance2)**(fromX : number,  fromY : number,  toX : number,  toY : number): number :
[Static] Return the distance between two points of from-to
##### Parameters
	fromX Starting point X
	fromY Starting point Y
	toX Arrival point X
	toY Arrival point Y

##### Return
[number]

## distanceSquare
###### **[distanceSquare](#distanceSquare)**(p1 : [Point](?file=007-API-2D网络内核/001-通用/019-Point),  p2 : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): number :
[Static] Square of distance<br>
Sometimes, in order to optimize the calculation, just compare the length of the two distances without the specific value, you can call this function, reducing the calculation of the open square than distance
##### Parameters
	p1 starting point
	p2 Endpoint

##### Return
[number] Square of the distance from the starting point to the end point

## distanceSquare2
###### **[distanceSquare2](#distanceSquare2)**(ax : number,  ay : number,  bx : number,  by : number): number :
[Static] Square of distance<br>
Sometimes, in order to optimize the calculation, just compare the length of the two distances without the specific value, you can call this function, reducing the calculation of the open square than distance
##### Parameters
	ax Starting point x
	ay Starting point y
	bx End point x
	by End point y

##### Return
[number] Square of the distance from the starting point to the end point



