# Matrix Matrix
>2D transformation: represents a transformation matrix that determines how points are mapped from one coordinate space to another. You can perform different graphical transformations on a display object by setting the properties of the Matrix object<br>Apply this Matrix object to the matrix property of the Transform object, and then apply this Transform object as the transform property of the display object. These transformation functions include translation (x and y repositioning), rotation, scaling, and tilting<br>a c tx<br>b d ty<br>Translation: tx, ty<br>Scaling: a(scaleX)、d(scaleY)<br>Rotation: q means radian<br>cos(q) -sin(q) tx<br>sin(q) cos(q)  ty<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EMPTY](#EMPTY)** : Matrix;<br>[Static] Empty matrix:  |
| **TEMP** : Matrix;<br>[Static] The matrix auxiliary body for temporary use does not need to create an instance but can reuse the instance as an auxiliary calculation  |
| **a** : number;<br>The value that affects the positioning of pixels along the x-axis when scaling or rotating the image.  |
| **b** : number;<br>The value that affects the positioning of pixels along the y-axis when rotating or tilting the image.  |
| **c** : number;<br>The value that affects the positioning of pixels along the x-axis when rotating or tilting the image.  |
| **d** : number;<br>The value that affects the positioning of pixels along the y-axis when scaling or rotating the image.  |
| **tx** : number;<br>The distance to translate each point along the x-axis.  |
| **ty** : number;<br>The distance to translate each point along the y-axis.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(a? : number,  b? : number,  c? : number,  d? : number,  tx? : number,  ty? : number)<br>Constructors
| **[identity](#identity)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Set this matrix as a unit matrix.
| **[setTranslate](#setTranslate)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Set position: set tx, ty directly.
| **[translate](#translate)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Pan position: add values to the original tx, ty.
| **[scale](#scale)**(x : number,  y : number): void<br>Apply a scaling transformation to the matrix.
| **[rotate](#rotate)**(angle : number): void<br>Apply rotation to the matrix.
| **[skew](#skew)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Apply a tilt transformation to the matrix.
| **[transformPoint](#transformPoint)**(out : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>Applies the geometric transformation of the matrix object representation to the specified point.
| **[invert](#invert)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Performs the inverse transformation of the original matrix.
| **[setTo](#setTo)**(a : number,  b : number,  c : number,  d : number,  tx : number,  ty : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Set the members of the matrix object to the specified values.
| **[concat](#concat)**(matrix : [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Connects the specified matrix to the current matrix, thus effectively combining the geometry of these two matrices.
| **[clone](#clone)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)<br>Returns a copy of this Matrix object.
| **[toString](#toString)**(): string<br>Returns the text value that lists the properties of this Matrix object.
| **[destroy](#destroy)**(): void<br>Destroy this object.

## Details

### EMPTY
###### EMPTY : Matrix;
[Static] Empty matrix:<br>
1 0 0<br>
0 1 0


## constructor
###### **[constructor](#constructor)**(a? : number,  b? : number,  c? : number,  d? : number,  tx? : number,  ty? : number) :
Constructors
##### Parameters
	a [Optional] Default = 1 The value that affects the positioning of pixels along the x-axis when scaling or rotating the image.
	b [Optional] Default = 0 The value that affects the positioning of pixels along the y-axis when rotating or tilting the image.
	c [Optional] Default = 0 The value that affects pixel positioning along the x-axis when rotating or tilting the image.
	d [Optional] Default = 1 The value that affects the positioning of pixels along the y-axis when scaling or rotating the image.
	tx [Optional] Default = 0 The distance to translate each point along the x-axis.
	ty [Optional] Default = 0 The distance to translate each point along the y-axis.



## identity
###### **[identity](#identity)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Set this matrix as a unit matrix.

##### Return
Return the current rectangle.

## setTranslate
###### **[setTranslate](#setTranslate)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Set position: set tx, ty directly.<br> 
@param x The distance to translate each point along the x-axis. <br> 
@param y The distance to translate each point along the y-axis. <br> 
@return Return the object itself



## translate
###### **[translate](#translate)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Pan position: add value to the original tx, ty. <br> 
@param x The amount (in pixels) to move to the right along the x-axis. <br> 
@param y The amount (in pixels) to move down along the y-axis.

##### Return
Returns this rectangle object.

## scale
###### **[scale](#scale)**(x : number,  y : number): void :
Applies a scaling transformation to the matrix. <br> 
@param x Multiplier for scaling objects along the x-axis. 1=100%<br> 
@param y Multiplier for scaling objects along the y-axis. 1=100%



## rotate
###### **[rotate](#rotate)**(angle : number): void :
Applies a rotation to the matrix. <br> 
@param angle The angle of rotation in radians.



## skew
###### **[skew](#skew)**(x : number,  y : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Applies a tilt transformation to the matrix. <br> 
@param x The 2D tilt radian along the X-axis. <br> 
@param y 2D tilt radian along the Y-axis.

##### Return
The current Matrix object.

## transformPoint
###### **[transformPoint](#transformPoint)**(out : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
Applies the geometric transformation of the matrix object representation to the specified point. <br>
 @param out is used to set the point of the output result. <br> 
 @return returns out



## invert
###### **[invert](#invert)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Performs the inverse transformation of the original matrix.

##### Return
The current matrix object.

## setTo
###### **[setTo](#setTo)**(a : number,  b : number,  c : number,  d : number,  tx : number,  ty : number): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Sets a member of the matrix object to the specified value. <br> 
@param a The value that affects pixel positioning along the x-axis when scaling or rotating the image. <br> 
@param b The value that affects the positioning of the pixel along the y-axis when rotating or tilting the image. <br> 
@param c The value that affects the pixel's positioning along the x-axis when rotating or tilting the image. <br> 
@param d The value that affects the positioning of the pixel along the y-axis when scaling or rotating the image. <br> 
@param tx The distance to translate each point along the x-axis. <br> 
@param ty The distance to translate each point along the y-axis.

##### Return
The current matrix object.

## concat
###### **[concat](#concat)**(matrix : [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix)): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Connects the specified matrix to the current matrix, thus effectively combining the geometry of the two matrices. <br> 
@param matrix The matrix to connect to the source matrix.

##### Return
Current Matrix.

## clone
###### **[clone](#clone)**(): [Matrix](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/013-Matrix) :
Returns a copy of this Matrix object.

##### Return
A new Matrix instance with exactly the same properties as the original.

## toString
###### **[toString](#toString)**(): string :
Returns the text value that lists the properties of this Matrix object.

##### Return
A string that contains the values of the Matrix object's attributes: a, b, c, d, tx and ty.

## destroy
###### **[destroy](#destroy)**(): void :
Destroy this object.





