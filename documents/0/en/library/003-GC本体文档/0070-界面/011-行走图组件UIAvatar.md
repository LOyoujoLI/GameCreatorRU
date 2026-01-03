# Interface: Avatar component UIAvatar
Interface component that encapsulates [Avatar](?file=003-GC本体文档/0030-行走图/001-概述) 

## Example diagram
 <img src="img/2/界面/2-9.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Avatar ID</td> <td>avatarID</td> <td>number</td> <td>Avatar</td>
 </tr> <tr>
    <td>Scaling horizontally</td> <td>scaleNumberX</td> <td>number</td> <td>scaling horizontally</td>
 </tr> <tr>
    <td>Scaling vertically</td> <td>scaleNumberY</td> <td>number</td> <td>scaling vertically</td>
 </tr> <tr>
    <td>Orientation</td> <td>orientationIndex</td> <td>number</td> <td>4-direction index reference (0-down,1-left,2-right,3-up)\n8-direction index reference (0-left,1-upper-left,2-upper,3-upper-right,4-right,5-under-right,6-down,7-below-left)</td>
 </tr> <tr>
    <td>Playback frame rate</td> <td>avatarFPS</td> <td>number</td> <td>Frames played per second</td>
 </tr> <tr>
    <td>AutoPlay Action</td> <td>isPlay</td> <td>boolean</td> <td>AutoLoop Action</td>
 </tr> <tr>
    <td>Start frame number</td> <td>avatarFrame</td> <td>number</td> <td>Indicates the frame from which the display first started</td>
 </tr> <tr>
    <td>Action ID</td> <td>actionID</td> <td>number</td> <td>action ID</td>
 </tr> <tr>               
    <td>Hue</td> <td>avatarHue</td> <td>number</td> <td>Hue</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version - Avatar component:UIAvatar](?file=006-API-2D单机内核/002-客户端/003-界面/012-UIAvatar)<br>
[API-Network version - Avatar component:UIAvatar](?file=007-API-2D网络内核/002-客户端/003-界面/012-UIAvatar)<br>
