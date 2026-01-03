# Rectangle Rectangular objects
>Determine a rectangle based on x, y, width, height for auxiliary calculations<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-08-08

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **x** : number;<br>The coordinates of the upper left corner of the rectangle x  |
| **y** : number;<br>The coordinates of the upper left corner of the rectangle y  |
| **width** : number;<br>Rectangle width  |
| **height** : number;<br>Rectangular height  |
| **right** : number;<br>[Read-only] Right coordinate x (i.e., the value of x+width)  |
| **bottom** : number;<br>[Read Only] Bottom coordinate y (i.e. the value of y+height)  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(x? : number,  y? : number,  width? : number,  height? : number)<br>Constructors
| **[setTo](#setTo)**(x : number,  y : number,  width : number,  height : number): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Set the specified values one at a time
| **[contains](#contains)**(x : number,  y : number): boolean<br>Whether to include the specified points
| **[intersects](#intersects)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): boolean<br>Intersects or not intersects another specified rectangle
| **[intersection](#intersection)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle),  out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Get the area that intersects the specified rectangle
| **[union](#union)**(source : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle),  out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Combine the two rectangles by filling the horizontal and vertical space between them to create a new Rectangle object
| **[clone](#clone)**(out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)<br>Returns a clone of this object
| **[toString](#toString)**(): string<br>Returns the value in string form: x,y,width,height
| **[equals](#equals)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): boolean<br>Is equal to the specified rectangle
| **[isEmpty](#isEmpty)**(): boolean<br>Determine if this Rectangle object is empty

## Details



## constructor
###### **[constructor](#constructor)**(x? : number,  y? : number,  width? : number,  height? : number) :
Constructors
##### Parameters
	x [Optional] Default value = 0
	y [Optional] Default value = 0
	width [Optional] Default value = 0
	height [Optional] Default value = 0



## setTo
###### **[setTo](#setTo)**(x : number,  y : number,  width : number,  height : number): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Set the specified values one at a time
##### Parameters
	x Value of x-axis
	y Value of y-axis
	width Width
	height Height

##### Return
[Rectangle]

## contains
###### **[contains](#contains)**(x : number,  y : number): boolean :
Whether to include the specified point
##### Parameters
	x x coordinate of the specified point
	y	y-coordinate of the specified point
	@return	Contained or not true=contained false=not contained



## intersects
###### **[intersects](#intersects)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): boolean :
Intersects or not intersects with another specified rectangle<br>
@param	rect The specified rectangle<br>
@return	Intersect or not true = intersect false = not intersect



## intersection
###### **[intersection](#intersection)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle),  out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Get the area that intersects the specified rectangle
##### Parameters
	rect The specified rectangle
	out [optional] default=null return value to this object if passed to reduce overhead

##### Return
[Rectangle] Intersecting areas

## union
###### **[union](#union)**(source : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle),  out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Combine the two rectangles by filling the horizontal and vertical space between them to create a new Rectangle object<br>
Note: The union() method ignores rectangles with a height or width value of 0, e.g.: var rect2:Rectangle = new Rectangle(300,300,50,0);
##### Parameters
	source The Rectangle object to add to this Rectangle object.
	out [optional] default=null return value to this object if passed to reduce overhead

##### Return
A new Rectangle object that acts as a union of two rectangles.

## clone
###### **[clone](#clone)**(out? : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle) :
Returns a clone of this object
##### Parameters
	out [optional] default=null return value to this object if passed to reduce overhead

##### Return
[Rectangle]

## toString
###### **[toString](#toString)**(): string :
Returns the value in string form: x,y,width,height

##### Return
[string]

## equals
###### **[equals](#equals)**(rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): boolean :
Whether equal to the specified rectangle<br> 
@param rect The specified rectangle<br> 
@return Whether equal true=equal false=not equal



## isEmpty
###### **[isEmpty](#isEmpty)**(): boolean :
Determine if this Rectangle object is empty

##### Return
Returns true if the width or height of the Rectangle object is less than or equal to 0, otherwise it returns false



