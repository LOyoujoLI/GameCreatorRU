# Interface: drop-down box component UIComboBox
A drop-down box is a component that, when clicked, brings up a set of options and allows one to be selected

## Example diagram
 <img src="img/2/界面/2-18.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Options</td> <td>itemLabels</td> <td>string</td> <td>Dropdown box options, comma-separated</td>
 </tr> <tr>
    <td>Default selected index</td> <td>selectedIndex</td> <td>number</td> <td>Default selected index, corresponding to the preset option, 0 means the first selected item</td>
 </tr> <tr>
    <td>Background image</td> <td>bgSkin</td> <td>string</td> <td>Dropdown box background image</td>
 </tr> <tr>
    <td>Background image nine-pane grid</td> <td>bgGrid9</td> <td>string</td> <td>Dropdown box background image nine-pane grid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Text Horizontal Alignment</td> <td>align</td> <td>number</td> <td>Text Horizontal Alignment<br>0-Left<br>1-Center<br>2-Right</td>
 </tr> <tr>
    <td>Text vertical alignment</td> <td>valign</td> <td>number</td> <td>Text vertical alignment<br>0-above<br>1-center<br>2-below</td>
 </tr> <tr>
    <td>Bold</td> <td>bold</td> <td>boolean</td> <td>Is the text font bold</td>
 </tr> <tr>
    <td>Text Text Style</td> <td>font</td> <td>string</td> <td>Text Text Style</td>
 </tr> <tr>
    <td>Text text color</td> <td>color</td> <td>string</td> <td>text text color</td>
 </tr> <tr>
    <td>TextSize</td> <td>fontSize</td> <td>number</td> <td>TextSize</td>
 </tr> <tr>
    <td>Text horizontal offset</td> <td>textDx</td> <td>number</td> <td>text horizontal offset</td>
 </tr> <tr>
    <td>Text Stroke Size</td> <td>textStroke</td> <td>number</td> <td>Text Stroke Effect</td>
 </tr> <tr>
    <td>Text Stroke Color</td> <td>textStrokeColor</td> <td>string</td> <td>Text Stroke Color</td>
 </tr> <tr>
    <td>Number of cells displayed</td> <td>displayItemSize</td> <td>number</td> <td>number of cells displayed</td>
 </tr> <tr>
    <td>Dropdown box scrollbar background image</td> <td>listScrollBg</td> <td>string</td> <td>Dropdown box scrollbar background image</td>
 </tr> <tr>
    <td>Dropdown Box ScrollBar Slider</td> <td>listScrollBar</td> <td>string</td> <td>Dropdown Box ScrollBar Slider</td>
 </tr> <tr>
    <td>Dropdown box list transparency</td> <td>listAlpha</td> <td>number</td> <td>Dropdown box list transparency</td>
 </tr> <tr>
    <td>CellHeight</td> <td>itemHeight</td> <td>number</td> <td>dropdown box cell height</td>
 </tr> <tr>
    <td>Scrollbar background color</td> <td>listBgColor</td> <td>string</td> <td>Dropdown box scrollbar background color</td>
 </tr> <tr>
    <td>Cell Horizontal Alignment</td> <td>itemAlign</td> <td>number</td> <td>Dropdown Box Cell Horizontal Alignment<br>0-Left<br>1-Center<br>2-Right</td>
 </tr> <tr>
    <td>Cell Vertical Alignment</td> <td>itemValign</td> <td>number</td> <td>Dropdown Box Cell Horizontal Alignment<br>0-Up<br>1-Center<br>2-Down</td>
 </tr> <tr>
    <td>Cell Bold</td> <td>itemBold</td> <td>boolean</td> <td>Whether the drop-down box cell text is bold</td>
 </tr> <tr>
    <td>Cell Text Font Style</td> <td>itemFont</td> <td>string</td> <td>Cell Text Font Style</td>
 </tr> <tr>
    <td>Cell Text Color</td> <td>itemColor</td> <td>string</td> <td>Cell Text Color</td>
 </tr> <tr>
    <td>Cell Hover Text Color</td> <td>itemOverColor</td> <td>string</td> <td>Cell Hover Text Color</td>
 </tr> <tr>
    <td>Cell hover background color</td> <td>itemOverBgColor</td> <td>string</td> <td>Background color of mouse over cell text</td>
 </tr> <tr>
    <td>Cell Text Font Size</td> <td>itemFontSize</td> <td>number</td> <td>Cell Text Font Size</td>
 </tr> <tr>
    <td>Cell Text Horizontal Offset</td> <td>itemTextDx</td> <td>number</td> <td>Cell Text Horizontal Offset</td>
 </tr> <tr>
    <td>Cell Text Vertical Offset</td> <td>itemTextDy</td> <td>number</td> <td>Cell Text Vertical Offset</td>
 </tr> <tr>
    <td>Cell Text Stroke Size</td> <td>itemTextStroke</td> <td>number</td> <td>Cell Text Stroke Effect</td>
 </tr> <tr>
    <td>Cell Text Stroke Color</td> <td>itemTextStrokeColor</td> <td>string</td> <td>Cell Text Stroke Color</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version - drop-down box component:UIComboBox](?file=006-API-2D单机内核/002-客户端/003-界面/017-UIComboBox)<br>
[API-Network version - drop-down box component:UIComboBox](?file=007-API-2D网络内核/002-客户端/003-界面/017-UIComboBox)<br>
