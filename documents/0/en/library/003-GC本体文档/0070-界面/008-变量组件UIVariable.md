# Interface: player value variable component UIVariable
You can select a variable and bind it to the component that displays the variable, and the text of the component will be updated automatically when the variable changes (real-time display)

## Example diagram
 <img src="img/2/界面/2-7.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Value displayed</td> <td>varID</td> <td>number</td> <td>Variable ID, showing the current value of the variable</td>
 </tr> <tr>
    <td>FontSize</td> <td>fontSize</td> <td>number</td> <td>FontSize</td>
 </tr> <tr>
    <td>Font color</td> <td>color</td> <td>string</td> <td>font color</td>
 </tr> <tr>
    <td>Bold</td> <td>bold</td> <td>boolean</td> <td>is bold</td>
 </tr> <tr>
    <td>Italic</td> <td>italic</td> <td>boolean</td> <td>is italic</td>
 </tr> <tr>
    <td>Horizontal alignment</td> <td>align</td> <td>number</td> <td>Horizontal alignment<br>0-Left<br>1-Center<br>2-Right</td>
 </tr> <tr>
    <td>Line spacing</td> <td>leading</td> <td>number</td> <td>line spacing</td>
 </tr> <tr>
    <td>Font</td> <td>font</td> <td>string</td>
 </tr> <tr>
    <td>Whether to auto-wrap</td> <td>wordWrap</td> <td>boolean</td> <td>Whether to auto-wrap</td>
 </tr> <tr>
    <td>Handling when text is out</td> <td>overflow</td> <td>number</td> <td>Handling when text is out<br>0-appears<br>1-hides</td>
 </tr> <tr>
    <td>Vertical alignment</td> <td>valign</td> <td>number</td> <td>Vertical alignment<br>0-above<br>1-center<br>2-below</td>
 </tr> <tr>
    <td>Show Shadows</td> <td>shadowEnabled</td> <td>boolean</td> <td>Show Shadows</td>
 </tr> <tr>
    <td>shadowColor</td> <td>shadowColor</td> <td>string</td> <td>shadow color</td>
 </tr> <tr>
    <td>Shadow Horizontal Offset</td> <td>shadowDx</td> <td>number</td> <td>Shadow Horizontal Position Offset</td>
 </tr> <tr>
    <td>Shadow Vertical Offset</td> <td>shadowDy</td> <td>number</td> <td>Shadow Vertical Position Offset</td>
 </tr> <tr>
    <td>Text Stroke Size</td> <td>stroke</td> <td>number</td> <td>Text Stroke Effect</td>
 </tr> <tr>
    <td>Text stroke color</td> <td>strokeColor</td> <td>string</td> <td>Text stroke color</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version - Player value variable component:UIVariable](?file=006-API-2D单机内核/002-客户端/003-界面/028-UIVariable)<br>
[API-Network version - Player Value Variable Component:UIVariable](?file=007-API-2D网络内核/002-客户端/003-界面/028-UIVariable)<br>
