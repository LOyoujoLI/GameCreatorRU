# Interface: Text component UIString
Component for displaying text, with support for binding player string variables

## Example diagram
 <img src="img/2/界面/2-6.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Text content</td> <td>text</td> <td>string</td> <td>text content, or if using a variable, the text will be displayed based on the current value of the variable</td>
 </tr> <tr>
    <td>FontSize</td> <td>fontSize</td> <td>number</td> <td>Text Font Size</td>
 </tr> <tr>
    <td>Font color</td> <td>color</td> <td>string</td> <td>Text font color</td>
 </tr> <tr>
    <td>Bold</td> <td>bold</td> <td>boolean</td> <td>Text font is bold or not</td>
 </tr> <tr>
    <td>Italic</td> <td>italic</td> <td>boolean</td> <td>Is text italic</td>
 </tr> <tr>
    <td>Horizontal alignment</td> <td>align</td> <td>number</td> <td>Text font horizontal alignment<br>0-Left<br>1-Center<br>2-Right</td>
 </tr> <tr>
    <td>Line spacing</td> <td>leading</td> <td>number</td> <td>text font line spacing</td>
 </tr> <tr>
    <td>Font</td> <td>font</td> <td>string</td> <td>Text font formatting</td>
 </tr> <tr>
    <td>Whether to auto-wrap</td> <td>wordWrap</td> <td>boolean</td> <td>Whether to auto-wrap text</td>
 </tr> <tr>
    <td>How to handle when text is out</td> <td>overflow</td> <td>number</td> <td>How to handle when text is out<br>0-show<br>1-hide</td>
 </tr> <tr>
    <td>Vertical alignment</td> <td>valign</td> <td>number</td> <td>Vertical alignment of text fonts<br>0-above<br>1-center<br>2-below</td>
 </tr> <tr>
    <td>Show Shadows</td> <td>shadowEnabled</td> <td>boolean</td> <td>Displays shadows on text</td>
 </tr> <tr>
    <td>shadowColor</td> <td>shadowColor</td> <td>string</td> <td>text shadow color</td>
 </tr> <tr>
    <td>Shadow Horizontal Offset</td> <td>shadowDx</td> <td>number</td> <td>Text Shadow Horizontal Position Offset</td>
 </tr> <tr>
    <td>shadow vertical offset</td> <td>shadowDy</td> <td>number</td> <td>text shadow vertical position offset</td>
 </tr> <tr>
    <td>Font stroke size</td> <td>stroke</td> <td>number</td> <td>Effect of font stroke</td>
 </tr> <tr>
    <td>Font stroke color</td> <td>strokeColor</td> <td>string</td> <td>Font stroke color</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version - Text component:UIString](?file=006-API-2D单机内核/002-客户端/003-界面/025-UIString)<br>
[API-Network version - Text Component:UIString](?file=007-API-2D网络内核/002-客户端/003-界面/025-UIString)<br>
