# AvatarFrameImage Avatar frame image data
>Frame cut data currently available for Avatar and Standing avatar<br><br>
>Maintenance personnel:**黑暗之神KDS **  
>Created on 2018-12-07

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **index** : number;<br>Frame index  |
| **picUrlIndex** : number;<br>Index to the corresponding gallery Avatar的picUrls  |
| **graphics** : Graphics;<br>Images  |
| **rect** : Rectangle;<br>Cut data null means use the whole picture directly  |
| **x** : number;<br>Coordinate X Offset value displayed x  |
| **y** : number;<br>Coordinate Y Offset value of the display y  |
| **width** : number;<br>width, if it exists, use that width, otherwise use the cut width  |
| **height** : number;<br>Height, use it if it exists, otherwise use the cut height  |
| **rotation** : number;<br>Rotation angle Default value 0  |
| **alpha** : number;<br>Transparent 0~1 Default value 1  |
| **hue** : number;<br>Hue -180~180 Default value 0  |
| **blur** : number;<br>Blur 0~N 0 means no blur Default value 0  |
| **tonal_r** : number;<br>Hue: Red -255~255 Default value 0  |
| **tonal_g** : number;<br>Hue: Green -255~255 Default value 0  |
| **tonal_b** : number;<br>Hue: Blue -255~255 Default value 0  |
| **tonal_gray** : number;<br>Hue: Gray 0~100 Default 0  |
| **tonal_mr** : number;<br>Red exposure 0~10 Default value 0  |
| **tonal_mg** : number;<br>Green exposure 0~10 Default value 0  |
| **tonal_mb** : number;<br>Blue exposure 0~10 Default value 0  |
| **wait_type** : number;<br>Waiting type 0/null-none (according to frame rate) 1-Waiting for X frames 2-Waiting for X milliseconds  |
| **[wait_count](#wait_count)** : number;<br>Wait count (frames/ms)  |
| **positiveRect** : Rectangle;<br>[Read-only] Obtain the tangent positive data of the image  |



## Details

### wait_count
###### wait_count : number;
Wait count (frames/ms)<br>
-- Where the frame is calculated according to the avatar frame rate, for example, the frame rate is set to 20, the game frame rate is 60, then wait 1 frame then the game actually rendered 3 frames of time (60/20 * 1)<br>
&nbsp;&nbsp;&nbsp;That means waiting for 3 frames means waiting for 3 times the interval time<br>
-- Parts follow the body's wait




