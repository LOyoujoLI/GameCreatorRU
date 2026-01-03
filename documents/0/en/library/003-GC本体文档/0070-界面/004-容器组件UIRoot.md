# Interface: Container Components UIRoot
The container component is used to load child display objects and can rectangularly crop areas to display only a portion of the content. <br> 
Sub-objects within a container are affected by the position, rotation, etc. of that container.

## Crop area display - example diagram
 <img src="img/2/界面/2-1.png" /><br>
 <img src="img/2/界面/2-2.png" /><br>
 Cropping area with scroll bar for scrolling display<br>
 <img src="img/2/界面/2-3.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Restricted display in region</td> <td>enabledLimitView</td> <td>boolean</td> <td>Whether child objects are displayed in the restricted region</td>
 </tr> <tr>
    <td>Scroll bar display status</td> <td>scrollShowType</td> <td>number</td> <td>Scroll bar display status<br>0-not displayed<br>1-displayed<br>2-automatically displayed<br>3-vertical scroll bar only<br>4-horizontal scroll bar only</td>
 </tr> <tr>
    <td>Horizontal ScrollBar Slider Skin</td> <td>hScrollBar</td> <td>string</td> <td>Horizontal ScrollBar Slider Skin</td>
 </tr> <tr>
    <td>Horizontal scrollbar background skin</td> <td>hScrollBg</td> <td>string</td> <td>Horizontal scrollbar background skin</td>
 </tr> <tr>
    <td>Vertical ScrollBar Slider Skin</td> <td>vScrollBar</td> <td>string</td> <td>Vertical ScrollBar Slider Skin</td>
 </tr> <tr>
    <td>Vertical scrollbar background skin</td> <td>vScrollBg</td> <td>string</td> <td>Vertical scrollbar background skin</td>
 </tr> <tr>
    <td>ScrollWidth</td> <td>scrollWidth</td> <td>number</td> <td>scrollBarWidth</td>
 </tr> <tr>
    <td>Sliding content area scrolling</td> <td>slowmotionType</td> <td>number</td> <td>sliding the area inside the container with the mouse or hand scrolls the content area inside (needs to be turned on to limit the display to the area and the actual internal content size to be beyond the display area)<br>0- enable this effect for mobile only<br >1-Always enable this effect<br>2-None</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version - Container components:UIRoot](?file=006-API-2D单机内核/002-客户端/003-界面/021-UIRoot)<br>
[API-Network version - Container Components:UIRoot](?file=007-API-2D网络内核/002-客户端/003-界面/021-UIRoot)<br>
