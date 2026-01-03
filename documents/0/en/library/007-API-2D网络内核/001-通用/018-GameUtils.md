# GameUtils Common tools for game related methods
>About orientation<br>&nbsp;--For orientation, refer to the keypad numbers centered on 5:<br>&nbsp;&nbsp;&nbsp;1-bottom left 2-bottom 3-bottom right 4-left 6-right 7-top left 8-top 9-top right<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-08-08

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getAssetOri](#getAssetOri)**(ori : number,  oriMode? : number): number<br>[static] to get the actual resource orientation, as the actual resource may not have the specified orientation, here will be done as a mapping
| **[getOriByAngle](#getOriByAngle)**(angle : number): number<br>[Static] Get the corresponding orientation according to the 0-360 angle
| **[getAngleByOri](#getAngleByOri)**(ori : number): number<br>【Static】According to the orientation to obtain 0-360 degrees
| **[getFlipOri](#getFlipOri)**(ori : number): number<br>[Static] Get the opposite orientation
| **[getGridPostion](#getGridPostion)**(p : Point,  helpP? : Point): Point<br>[Static][Actual coordinates]->[Grid coordinates
| **[getGridCenter](#getGridCenter)**(p : Point,  helpP? : Point): Point<br>[Static][Actual coordinate]->[Actual coordinate center point
| **[getGridCenterByGrid](#getGridCenterByGrid)**(gridP : Point,  helpP? : Point): Point<br>[Static] [Grid coordinates] -> [Actual coordinate center point
| **[getSameStateGrid](#getSameStateGrid)**(mapData : any[][],  gridX : number,  gridY : number,  width : number,  height : number,  attributes : string[],  limit? : number): Point[]<br>[Static] Query the adjacent path with the same state, such as the GameCreator editor paint bucket is used in this method
| **[getMendingGrids](#getMendingGrids)**(grid1 : Point,  grid2 : Point,  per? : number): Point[]<br>[Static] Get the complementary grid between two grids
| **[getAutoFitSizePre](#getAutoFitSizePre)**(rect : Rectangle,  canvasRect : Rectangle): number<br>Static】Get the minimum of the ratio canvasRect.width/rect.width to canvasRect.height/rect.height
| **[isInheritNode](#isInheritNode)**(node : any,  parentNode : any): boolean<br>[Static] Determine if it inherits from a node (the parent attribute is required in the node system to point to the parent node)
| **[getVarID](#getVarID)**(value : string): number<br>[Static] Get n based on a specific string $n, return 0 if it doesn't match
| **[isLegalVarName](#isLegalVarName)**(varName : string): boolean<br>[Static] Checking for legal variable names
| **[getCurveData](#getCurveData)**(curveStrData : string): any[]<br>[Static] Get curve data, based on string format
| **[getBezierPoint2ByGroupValue](#getBezierPoint2ByGroupValue)**(groupValue : any[],  x : number): number<br>[Static] Get the value of a point from curve data
| **[getTransData](#getTransData)**(transDataStr : string): TransData<br> [Static] Get transition component Object type data based on string format data
| **[getValueByTransData](#getValueByTransData)**(transData : TransData,  x : number): number<br>[Static] Get the value corresponding to the transition according to the incoming parameter x

## Details



## getAssetOri
###### **[getAssetOri](#getAssetOri)**(ori : number,  oriMode? : number): number :
[static] to get the actual resource orientation, as the actual resource may not have the specified orientation, here will be done as a mapping<br>
If there is only a four-directional avatar, the right direction is mapped to the right if the upper right direction is obtained.
##### Parameters
	ori Orientation
	oriMode [Optional] Default value = 8

##### Return
[number] Replace the mapped orientation

## getOriByAngle
###### **[getOriByAngle](#getOriByAngle)**(angle : number): number :
【Static】According to the 0-360 angle to get the corresponding face
##### Parameters
	angle Angle 0-360

##### Return
[number] Back to facing 1/2/3/4/6/7/8/9

## getAngleByOri
###### **[getAngleByOri](#getAngleByOri)**(ori : number): number :
【Static】According to the orientation to obtain 0-360 degrees
##### Parameters
	ori Orientation 1/2/3/4/6/7/8/9

##### Return
[number] Angle 0-360

## getFlipOri
###### **[getFlipOri](#getFlipOri)**(ori : number): number :
[Static] Get the opposite orientation
##### Parameters
	ori Orientation 1/2/3/4/6/7/8/9

##### Return
Returns the opposite direction of ori, e.g., the opposite of 2 is 8

## getGridPostion
###### **[getGridPostion](#getGridPostion)**(p : Point,  helpP? : Point): Point :
[Static][Actual coordinates]->[Grid coordinates]
##### Parameters
	p Actual Coordinates
	helpP [Optional] Default=null Use this object to self-load if it exists instead of creating a new Point object

##### Return
[Point] Grid coordinates

## getGridCenter
###### **[getGridCenter](#getGridCenter)**(p : Point,  helpP? : Point): Point :
[Static][Actual coordinate]->[Actual coordinate center point]
##### Parameters
	p Actual Coordinates
	helpP [Optional] Default=null Use this object to self-load if it exists instead of creating a new Point object

##### Return
[Point]

## getGridCenterByGrid
###### **[getGridCenterByGrid](#getGridCenterByGrid)**(gridP : Point,  helpP? : Point): Point :
[Static] [Grid coordinates] -> [Actual coordinate center point]
##### Parameters
	gridP Grid coordinates
	helpP [Optional] Default=null Use this object to self-load if it exists instead of creating a new Point object

##### Return
[Point]

## getSameStateGrid
###### **[getSameStateGrid](#getSameStateGrid)**(mapData : any[][],  gridX : number,  gridY : number,  width : number,  height : number,  attributes : string[],  limit? : number): Point[] :
[Static] Query the adjacent path with the same state, such as the GameCreator editor paint bucket is used in this method
##### Parameters
	mapData Figure Data
	gridX source lattice
	gridY source lattice
	width Total width
	height Total height
	attributes Determine the set of attributes with the same state of the grid, i.e., if there is an attribute different from that of the mapData data, it is also regarded as a different state.
	limit Default = 100 Limit the search to a square of the surrounding limit distance

##### Return
[Point]

## getMendingGrids
###### **[getMendingGrids](#getMendingGrids)**(grid1 : Point,  grid2 : Point,  per? : number): Point[] :
[Static] Get the complementary grid between two grids
##### Parameters
	grid1 Starting point grid
	grid2 Terminal grid
	per [Optional] Default = 0.1 Ratio of each traversal, if 0.1 means the starting frame to the end frame is cut 10 times and the middle frame is returned without duplication

##### Return
[Point]

## getAutoFitSizePre
###### **[getAutoFitSizePre](#getAutoFitSizePre)**(rect : Rectangle,  canvasRect : Rectangle): number :
Static】Get the minimum of the ratio canvasRect.width/rect.width to canvasRect.height/rect.height
##### Parameters
	rect
	canvasRect Canvas Rectangle



## isInheritNode
###### **[isInheritNode](#isInheritNode)**(node : any,  parentNode : any): boolean :
[Static] Determine if it inherits from a node (the parent attribute is required in the node system to point to the parent node)
##### Parameters
	node Nodes
	parentNode Suspected parent node

##### Return
Whether it is the true parent node

## getVarID
###### **[getVarID](#getVarID)**(value : string): number :
[Static] Get n based on a specific string $n, return 0 if it doesn't match
##### Parameters
	value Special format: e.g. $6

##### Return
Variable ID: e.g. 6

## isLegalVarName
###### **[isLegalVarName](#isLegalVarName)**(varName : string): boolean :
[Static] Checking for legal variable names
##### Parameters
	varName Variable Name

##### Return
[boolean] Is it legal

## getCurveData
###### **[getCurveData](#getCurveData)**(curveStrData : string): any[] :
[Static] Get curve data, based on string format<br>
Return Format:[[0,0,startY,maxLength,maxHeight],[type,startX,startY,endX,endY,ctrlX,ctrlY],[type,startX,startY,endX,endY,ctrlX,ctrlY],...]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maxLength=maxLength (for reference only) maxHeight=MaxHeight Start x always at 0, end x always at 100 type=0-Linear line segment 1-Quadratic Bessel curve segment (has ctrlX,ctrlY)
##### Parameters
	curveStrData Curve Data

##### Return
groupValue

## getBezierPoint2ByGroupValue
###### **[getBezierPoint2ByGroupValue](#getBezierPoint2ByGroupValue)**(groupValue : any[],  x : number): number :
[Static] Get the value of a point from curve data<br>
Format of the curve data:[[0,0,startY,maxLength,maxHeight],[type,startX,startY,endX,endY,ctrlX,ctrlY],[type,startX,startY,endX,endY,ctrlX,ctrlY],...]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maxLength=maxLength (for reference only) maxHeight=MaxHeight Start x always at 0, end x always at 100 type=0-Linear line segment 1-Quadratic Bessel curve segment (has ctrlX,ctrlY)
##### Parameters
	groupValue Curve Data
	x 0~1 0 means the head of the curve, 1 means the end of the curve Assuming that the curve is a linear curve with only one segment and the value range is 0-5000, the value of 0.5 is 2500

##### Return
value value

## getTransData
###### **[getTransData](#getTransData)**(transDataStr : string): TransData :
[Static] Get the data of transition component Object type based on the data in string format
##### Parameters
	transData String format data



## getValueByTransData
###### **[getValueByTransData](#getValueByTransData)**(transData : TransData,  x : number): number :
[Static] Get the value corresponding to the transition according to the incoming parameter x
##### Parameters
	transData Transition Data
	x Scope 0-1





