# Graphics Image drawing
>The system renders the image based on the draw command, and one command produces one render draw (drawcall).<br>The number of rendering on the performance of a large impact, generally the entire game per frame global rendering number of control within 1000 will be more appropriate<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[dispose](#dispose)**(): void<br>Destroy the object
| **[clear](#clear)**(): void<br>Clear all drawing commands.
| **[drawTexture](#drawTexture)**(tex : Texture,  x? : number,  y? : number,  width? : number,  height? : number,  m? : Matrix,  alpha? : number): void<br>Draw the entire mapping
| **[fillTexture](#fillTexture)**(tex : Texture,  x : number,  y : number,  width? : number,  height? : number,  type? : string,  offset? : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): void<br>Filled mapping, croppable to show only part of the mapping
| **[fillText](#fillText)**(text : string,  x : number,  y : number,  font : string,  color : string,  textAlign : string): void<br>Drawing text
| **[drawLine](#drawLine)**(fromX : number,  fromY : number,  toX : number,  toY : number,  lineColor : string,  lineWidth? : number): void<br>Drawing lines
| **[drawLines](#drawLines)**(x : number,  y : number,  points : number[],  lineColor : string,  lineWidth? : number): void<br>Draw a series of line segments
| **[drawCurves](#drawCurves)**(x : number,  y : number,  points : number[],  lineColor : string,  lineWidth? : number): void<br>Plot a series of curves
| **[drawRect](#drawRect)**(x : number,  y : number,  width : number,  height : number,  fillColor : any,  lineColor? : string,  lineWidth? : number): void<br>Drawing rectangles
| **[drawCircle](#drawCircle)**(x : number,  y : number,  radius : number,  fillColor : string,  lineColor? : string,  lineWidth? : number): void<br>Drawing circles
| **[drawPie](#drawPie)**(x : number,  y : number,  radius : number,  startAngle : number,  endAngle : number,  fillColor : string,  lineColor? : string,  lineWidth? : number): void<br>Drawing a sector
| **[drawPoly](#drawPoly)**(x : number,  y : number,  points : number[],  fillColor : any,  lineColor? : string,  lineWidth? : number): void<br>Drawing polygons

## Details



## dispose
###### **[dispose](#dispose)**(): void :
Destroy the object



## clear
###### **[clear](#clear)**(): void :
Clear all drawing commands.



## drawTexture
###### **[drawTexture](#drawTexture)**(tex : Texture,  x? : number,  y? : number,  width? : number,  height? : number,  m? : Matrix,  alpha? : number): void :
Draw the entire mapping
##### Parameters
	tex Poster
	x [Optional] Default value = 0 X-axis offset
	y [Optional] Default value = 0 Y-axis offset
	width [Optional] Default value = 0 Width Default based on mapping width
	height [Optional] Default value = 0 Height Default based on mapping height
	m [Optional] Default=null Matrix information
	alpha [Optional] Default value = 1 Transparency



## fillTexture
###### **[fillTexture](#fillTexture)**(tex : Texture,  x : number,  y : number,  width? : number,  height? : number,  type? : string,  offset? : [Point](?file=007-API-2D网络内核/001-通用/019-Point)): void :
Filled mapping, croppable to show only part of the mapping
##### Parameters
	tex Poster
	x X-axis offset
	y Y-axis offset
	width [Optional] Default value = 0 Width Default based on mapping width
	height [Optional] Default value = 0 Height Default based on mapping height
	type [Optional] Default="repeat" Padding type repeat|repeat-x|repeat-y|no-repeat Indicates a tiled loop
	offset [Optional] Default = null Offset for mapping sampling, if only the middle of the mapping is drawn, the value is not 0,0 points



## fillText
###### **[fillText](#fillText)**(text : string,  x : number,  y : number,  font : string,  color : string,  textAlign : string): void :
Drawing text
##### Parameters
	text Text Content
	x X-axis offset
	y Y-axis offset
	font Font size and font e.g. "20px Song"
	color Text color like "#FFFF00"
	textAlign Alignment mode "left", "center", "right"



## drawLine
###### **[drawLine](#drawLine)**(fromX : number,  fromY : number,  toX : number,  toY : number,  lineColor : string,  lineWidth? : number): void :
Drawing lines
##### Parameters
	fromX X-axis start position
	fromY Y-axis start position
	toX X-axis end position
	toY Y-axis end position
	lineColor Color
	lineWidth [Optional] Default = 1 Line width



## drawLines
###### **[drawLines](#drawLines)**(x : number,  y : number,  points : number[],  lineColor : string,  lineWidth? : number): void :
Draw a series of line segments
##### Parameters
	x X-axis position to start drawing
	y Y-axis position to start drawing
	points The set of points of a line segment Format:[x1,y1,x2,y2,x3,y3...]
	lineColor Line Color
	lineWidth [Optional] Default value = 1



## drawCurves
###### **[drawCurves](#drawCurves)**(x : number,  y : number,  points : number[],  lineColor : string,  lineWidth? : number): void :
Plot a series of curves
##### Parameters
	x X-axis position to start drawing
	y Y-axis position to start drawing
	points The set of points of a line segment, in the format[startx,starty,ctrx,ctry,startx,starty...]
	lineColor Line segment colors, or gradient objects that fill the drawing
	lineWidth [Optional] Default value = 1



## drawRect
###### **[drawRect](#drawRect)**(x : number,  y : number,  width : number,  height : number,  fillColor : any,  lineColor? : string,  lineWidth? : number): void :
Drawing rectangles
##### Parameters
	x X-axis position to start drawing
	y Y-axis position to start drawing
	width Rectangle width
	height Rectangular height
	fillColor Fill Color
	lineColor [Optional] Default=null Border color
	lineWidth [Optional] Default value = 1 Border width



## drawCircle
###### **[drawCircle](#drawCircle)**(x : number,  y : number,  radius : number,  fillColor : string,  lineColor? : string,  lineWidth? : number): void :
Drawing circles
##### Parameters
	x Round point X-axis position
	y Y-axis position of circle point
	radius radius
	fillColor Fill color, or fill gradient object of the drawing
	lineColor [Optional] Default=null Border color
	lineWidth [Optional] Default value = 1 Border width



## drawPie
###### **[drawPie](#drawPie)**(x : number,  y : number,  radius : number,  startAngle : number,  endAngle : number,  fillColor : string,  lineColor? : string,  lineWidth? : number): void :
Drawing a sector<br>
>var sp = new Sprite();<br>
>sp.graphics.drawPie(0,0,30,-90,90,"#FF0000");<br>
>stage.addChild(sp);<br>
>sp.x = 500;<br>
>sp.y = 500;<br>
>


##### Parameters
	x X-axis position to start drawing
	y Y-axis position to start drawing
	radius Sector Radius
	startAngle Start angle -90 degrees at 12 o'clock, 90 degrees at 6 o'clock, start drawing in clockwise direction
	endAngle Ending Angle
	fillColor Fill Color
	lineColor [Optional] Default=null Border color
	lineWidth [Optional] Default value = 1 Border width



## drawPoly
###### **[drawPoly](#drawPoly)**(x : number,  y : number,  points : number[],  fillColor : any,  lineColor? : string,  lineWidth? : number): void :
Drawing polygons<br>
>var sp = new Sprite();<br>
>sp.graphics.drawPoly(0,0,[100,100,200,200,100,300,50,250],"#FF0000");<br>
>stage.addChild(sp);<br>
>sp.x = 300;<br>
>sp.y = 300;<br>
>


##### Parameters
	x X-axis position to start drawing
	y Y-axis position to start drawing
	points Set of points of a polygon Format[x1,y1,x2,y2...]
	fillColor Fill Color
	lineColor [Optional] Default=null Border color
	lineWidth [Optional] Default value = 1 Border width





