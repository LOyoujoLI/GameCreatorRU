# Interface: Tabs tab component UITabBox
A component for displaying the tab bar, supporting horizontally aligned tabs and vertically aligned tabs<br> 
If there are N tabs in the tab component, then the component's child objects can be automatically switched to display the child objects by putting 3 of them

## Example diagram
 <img src="img/2/界面/2-14.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>SelectedIndex</td> <td>selectedIndex</td> <td>number</td> <td>selectedIndex</td>
 </tr> <tr>
    <td>Image when tag is not selected</td> <td>itemImage1</td> <td>string</td> <td>Image displayed when tag is not selected</td>
 </tr> <tr>
    <td>Nine-pane grid when tag is unselected</td> <td>grid9img1</td> <td>string</td> <td>Nine-pane grid when tag is unselected (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Image when tag is selected</td> <td>itemImage2</td> <td>string</td> <td>Image displayed when tag is selected</td>
 </tr> <tr>
    <td>Nine-pane grid when tag is not selected</td> <td>grid9img2</td> <td>string</td> <td>Nine-pane grid when tag is selected (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Width of tag</td> <td>itemWidth</td> <td>number</td> <td>Width of tag</td>
 </tr> <tr>
    <td>Height of tag</td> <td>itemHeight</td> <td>number</td> <td>height of tag</td>
 </tr> <tr>
    <td>Label spacing</td> <td>spacing</td> <td>number</td> <td>label spacing</td>
 </tr> <tr>
    <td>TextFont</td> <td>labelFont</td> <td>string</td> <td>TextFont</td>
 </tr> <tr>
    <td>Label text horizontal offset</td> <td>labelDx</td> <td>number</td> <td>label text horizontal offset value</td>
 </tr> <tr>
    <td>Label text vertical offset</td> <td>labelDy</td> <td>number</td> <td>label text vertical offset value</td>
 </tr> <tr>
    <td>Bold</td> <td>labelBold</td> <td>boolean</td> <td>Whether text is bold</td>
 </tr> <tr>
    <td>Italic</td> <td>labelItalic</td> <td>boolean</td> <td>Is text italic</td>
 </tr> <tr>
    <td>Text Horizontal Alignment</td> <td>labelAlign</td> <td>number</td> <td>Text Horizontal Alignment<br>0-Left<br>1-Center<br>2-Right</td>
 </tr> <tr>
    <td>Text font size</td> <td>labelSize</td> <td>number</td> <td>text font size</td>
 </tr> <tr>
    <td>Tag items</td> <td>items</td> <td>string</td> <td>tag items, separated by commas \nPutting components under sublevels of that component will automatically take effect \nFor example, if there are three tags, you should put three levels of subcomponents underneath them to switch the display</td>
 </tr> <tr>
    <td>Whether to align vertically</td> <td>rowMode</td> <td>boolean</td> <td>Whether to align vertically</td>
 </tr> <tr>
    <td>Text color when selected</td> <td>labelSelectedColor</td> <td>string</td> <td>text color when selected</td>
 </tr> <tr>
 </tr> <tr>
    <td>Text Stroke Size</td> <td>labelStroke</td> <td>number</td> <td>Text Stroke Effect</td>
 </tr> <tr>
    <td>Text Stroke Color</td> <td>labelStrokeColor</td> <td>string</td> <td>Text Stroke Color</td>
 </tr> </table>

## Reference-API
[API-Standalone version - Tabs tab component:UITabBox](?file=006-API-2D单机内核/002-客户端/003-界面/027-UITabBox)<br>
[API-Network version - Tabs tab component:UITabBox](?file=007-API-2D网络内核/002-客户端/003-界面/027-UITabBox)<br>
