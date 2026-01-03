# ColorFilter Color Filters
>Use the ColorFilter class to apply a 4 x 5 matrix transformation to the RGBA color and alpha value of each pixel on the input image.<br>to produce results with a new set of RGBA colors and alpha values. This class allows saturation changes, hue rotation, luminance to alpha, and various other effects.<br>You can apply a filter to any display object (i.e., an object inherited from the Sprite class).<br>Note: For RGBA values, the highest valid byte represents the red channel value, and the subsequent valid bytes represent the green, blue, and alpha channel values, respectively.<br>With this color matrix you can create: hue, shade, grayscale, hue, etc.<br>// Default Value<br>1,0,0,0,0,<br>0,1,0,0,0,<br>0,0,1,0,0,<br>0,0,0,1,0<br>// principle<br>a[0]  a[1]  a[2]  a[3]  a[4]<br>a[5]  a[6]  a[7]  a[8]  a[9]<br>a[10] a[11] a[12] a[13] a[14]<br>a[15] a[16] a[17] a[18] a[19]<br>redResult   = (a[0]  * srcR) + (a[1]  * srcG) + (a[2]  * srcB) + (a[3]  * srcA) + a[4]<br>greenResult = (a[5]  * srcR) + (a[6]  * srcG) + (a[7]  * srcB) + (a[8]  * srcA) + a[9]<br>blueResult  = (a[10] * srcR) + (a[11] * srcG) + (a[12] * srcB) + (a[13] * srcA) + a[14]<br>alphaResult = (a[15] * srcR) + (a[16] * srcG) + (a[17] * srcB) + (a[18] * srcA) + a[19]<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[Filter](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/021-Filter)<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(mat? : Array<any>)<br>Constructor Default = 4

## Details



## constructor
###### **[constructor](#constructor)**(mat? : Array<any>) :
Constructor Default = 4





