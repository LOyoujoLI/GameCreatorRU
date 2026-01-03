# GameFunction Game built-in function function
>Will soon be outlawed by upper-level custom events and not as a built-in feature in the GC2D kernel<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-02-04

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[shake](#shake)**(strength : number,  t : number): void<br>[Static] Scene vibration: the current frame vibrates directly, total vibration t frames
| **[tonal](#tonal)**(r : number,  g : number,  b : number,  gray : number,  t : number,  mr : number,  mg : number,  mb : number,  layer? : number,  tCur? : number): void<br>[Static] Change scene color: change color directly in the current frame, total t frames changed
| **[cameraMove](#cameraMove)**(type : number,  x : number,  y : number,  soIndex : number,  tween : boolean,  t : number,  tCur? : number,  window_width? : number,  window_height? : number): void<br>[Static] Scene camera movement: the current frame starts moving directly, total t frames moved
| **[fogSet](#fogSet)**(url : string,  sx : number,  sy : number,  dx : number,  dy : number,  alpha : number,  blendMode : number): void<br>[Static] Scene fog graphics change

## Details



## shake
###### **[shake](#shake)**(strength : number,  t : number): void :
[Static] Scene vibration: the current frame vibrates directly, total vibration t frames
##### Parameters
	strength Range
	t Frame Rate



## tonal
###### **[tonal](#tonal)**(r : number,  g : number,  b : number,  gray : number,  t : number,  mr : number,  mg : number,  mb : number,  layer? : number,  tCur? : number): void :
[Static] Change scene color: change color directly in the current frame, total t frames changed
##### Parameters
	r Red
	g Green
	b Blue
	gray Grayscale
	t Time (frames)
	mr Red Exposure
	mg Green Exposure
	mb Blue Exposure
	layer Levels (advanced features added later)
	tCur Current T



## cameraMove
###### **[cameraMove](#cameraMove)**(type : number,  x : number,  y : number,  soIndex : number,  tween : boolean,  t : number,  tCur? : number,  window_width? : number,  window_height? : number): void :
[Static] Scene camera movement: the current frame starts moving directly, total t frames moved
##### Parameters
	type 0-Direct coordinates 1-Locked object
	x The specified coordinates x
	y The specified coordinate y
	soIndex Locked objects
	tween Slow motion
	t Frame Rate
	tCur Current number of frames (first time is null)



## fogSet
###### **[fogSet](#fogSet)**(url : string,  sx : number,  sy : number,  dx : number,  dy : number,  alpha : number,  blendMode : number): void :
[Static] Scene fog graphics change
##### Parameters
	url Map layer resource address
	sx X-axis scale value, default is 1. Set to negative to achieve horizontal inversion, e.g. scaleX=-1.
	sy Y-axis zoom value, default value is 1. Set to negative to achieve vertical inversion effect, e.g. scaleX=-1.
	dx X-direction flow
	dy Y-directional flow
	alpha Transparency, the value is 0-1, the default value is 1, which means opaque. Changing the alpha value will affect the drawcall.
	blendMode Specifies the blend mode to use. Currently only "lighter" is supported.





