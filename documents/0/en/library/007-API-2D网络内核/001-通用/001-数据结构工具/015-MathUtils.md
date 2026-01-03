# MathUtils Mathematical tools
>GC internal package of some common math-related functions<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-08-22

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[angle2Radian](#angle2Radian)**(angle : number): number<br>[Static] Angle to radian.
| **[radian2Angle](#radian2Angle)**(radian : number): number<br>[Static] Convert radians to angles.
| **[rand](#rand)**(n : number): number<br>[Static] Return a positive integer from 0 to n-1
| **[direction360](#direction360)**(x1 : number,  y1 : number,  x2 : number,  y2 : number): number<br>[Static] Get the angle between two points 0-360
| **[fixIntDigit](#fixIntDigit)**(s : any,  fixDigit? : number): string<br>[Static] Fixed integer bits, not full then replenish 0
| **[int](#int)**(v : any): number<br>[Static] Forced conversion to integers
| **[float](#float)**(v : any): number<br>[Static] Convert to floating point
| **[inAngleRange](#inAngleRange)**(limitMax : number,  limitMin : number,  angle : number): boolean<br>[Static] Determining if it is within the degree range
| **[isPowerOfTwo](#isPowerOfTwo)**(x : number): boolean<br>[Static] Determining whether a number is the nth power of 2
| **[nextHighestPowerOfTwo](#nextHighestPowerOfTwo)**(x : number): number<br>[Static] Get the nearest power of 2 to x
| **[getBezierPoint2](#getBezierPoint2)**(startX : number,  startY : number,  CtrlX : number,  CtrlY : number,  endX : number,  endY : number,  t : number,  resultPoint? : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point)<br>[Static] Calculate the specific position of a point on a quadratic Bessel curve

## Detailss



## angle2Radian
###### **[angle2Radian](#angle2Radian)**(angle : number): number :
[static] Angle to radian. <br> 
@param angle The angle value. <br> 
@return Return the radian value.



## radian2Angle
###### **[radian2Angle](#radian2Angle)**(radian : number): number :
[static] Radian to angle conversion. <br> 
@param radian The radian value. <br> 
@return Return the angle value.



## rand
###### **[rand](#rand)**(n : number): number :
[Static] Return a positive integer from 0 to n-1
##### Parameters
	n

##### Return
[number]

## direction360
###### **[direction360](#direction360)**(x1 : number,  y1 : number,  x2 : number,  y2 : number): number :
[Static] Get the angle between two points 0-360
##### Parameters
	x1 Starting point x
	y1 Starting point y
	x2 End point x
	y2 End point y

##### Return
[number] The angle of the end point relative to the start point

## fixIntDigit
###### **[fixIntDigit](#fixIntDigit)**(s : any,  fixDigit? : number): string :
[Static] Fixed integer bits, not full then replenish 0<br>
such as fixIntDigit(2,3)  -->  003
##### Parameters
	s Numerical value string | number
	fixDigit [Optional] Default value = 4 Fixed number of bits

##### Return
[string]

## int
###### **[int](#int)**(v : any): number :
[Static] Forced conversion to integers
##### Parameters
	v For parameters that do not meet the requirements are converted to 0



## float
###### **[float](#float)**(v : any): number :
[Static] Convert to floating point
##### Parameters
	v For parameters that do not meet the requirements are converted to 0



## inAngleRange
###### **[inAngleRange](#inAngleRange)**(limitMax : number,  limitMin : number,  angle : number): boolean :
[Static] Determining if it is within the degree range
##### Parameters
	limitMax Upper limit -360~360
	limitMin Go offline -360~360
	angle Specified angle

##### Return
[boolean]

## isPowerOfTwo
###### **[isPowerOfTwo](#isPowerOfTwo)**(x : number): boolean :
[Static] Determining whether a number is the nth power of 2
##### Parameters
	x A number

##### Return
[boolean]

## nextHighestPowerOfTwo
###### **[nextHighestPowerOfTwo](#nextHighestPowerOfTwo)**(x : number): number :
[Static] Get the nearest power of 2 to x
##### Parameters
	x

##### Return
[number]

## getBezierPoint2
###### **[getBezierPoint2](#getBezierPoint2)**(startX : number,  startY : number,  CtrlX : number,  CtrlY : number,  endX : number,  endY : number,  t : number,  resultPoint? : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): [Point](?file=007-API-2D网络内核/001-通用/019-Point) :
[Static] Calculate the specific position of a point on a quadratic Bessel curve
##### Parameters
	startX Starting point x
	startY Starting point y
	CtrlX Control point x
	CtrlY Control point y
	endX End point x
	endY End point y
	t 0~1 Indicates the position information of a point between the start and the end 0 means the start, 1 means the end, and 0.5 means half of the start - end
	resultPoint [Optional] Default=null Load data into the point if it exists

##### Return
Calculate the exact location of the point



