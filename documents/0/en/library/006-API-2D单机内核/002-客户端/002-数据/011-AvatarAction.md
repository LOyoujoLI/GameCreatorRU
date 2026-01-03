# AvatarAction Avatar action data
>An Avatar may contain several actions, each of which has a series of atlases corresponding to each direction<br>Orientation of the system reference keypad to the other numbers centered on 5: 1-bottom left 2-bottom 3-bottom right 4-left 6-right 7-top left 8-top 9-top right<br>7 8 9<br>4 5 6<br>1 2 3<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-12-07

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **id** : number;<br>Action ID Corresponds to the ID in the action library  |
| **[frameImageInfo](#frameImageInfo)** : AvatarFrameImage[][];<br>Frame data information for the atlas Default value=[]  |
| **[oriMode](#oriMode)** : number;<br>Directional mode 1 2 3 4 5 8  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getFrameLength](#getFrameLength)**(ori : number,  useMapping? : boolean): number<br>Get the total number of frames for the specified orientation
| **[getFrameImage](#getFrameImage)**(ori : number,  frame : number,  useMapping? : boolean): AvatarFrameImage<br>Get the data image of a certain direction and a certain frame in the current action
| **[hasOri](#hasOri)**(ori : number): boolean<br>Does the orientation exist

## Details

### frameImageInfo
###### frameImageInfo : AvatarFrameImage[][];
Frame data information for the atlas Default value=[]<br>
[Facing] Corresponding keypad - Frame map<br>
such as [2] = AvatarFrameImage[] Indicates the set of frame map data under the action orientation
### oriMode
###### oriMode : number;
Directional mode 1 2 3 4 5 8<br>
Which 1, 3, 5 direction will automatically mirror flip


## getFrameLength
###### **[getFrameLength](#getFrameLength)**(ori : number,  useMapping? : boolean): number :
Get the total number of frames for the specified orientation
##### Parameters
	ori Orientation
	useMapping [Optional] Default=true Use mapping to get the actual faces, e.g. if there are no 7 faces then use 4 faces instead



## getFrameImage
###### **[getFrameImage](#getFrameImage)**(ori : number,  frame : number,  useMapping? : boolean): AvatarFrameImage :
Get the data image of a certain direction and a certain frame in the current action
##### Parameters
	ori Orientation
	frame Frame
	useMapping [Optional] Default=true Use mapping to get the actual faces, e.g. if there are no 7 faces then use 4 faces instead

##### Return
Data Images

## hasOri
###### **[hasOri](#hasOri)**(ori : number): boolean :
Does the orientation exist
##### Parameters
	ori Orientation

##### Return
[boolean]



