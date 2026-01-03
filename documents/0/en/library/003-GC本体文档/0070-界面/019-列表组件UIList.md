# Interface: List component UIList
The list component is a component that supports NxM matrix arrangement, and its internal items (items) are implemented by creating another interface source

## Example diagram
 <img src="img/2/界面/2-16.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>ItemModel</td> <td>itemModelGUI</td> <td>number</td> <td>itemModel</td>
 </tr> <tr>
    <td>Number of editor preview items</td> <td>previewSize</td> <td>number</td> <td>Only for editor preview display</td>
 </tr> <tr>
    <td>Whether to allow selection</td> <td>selectEnable</td> <td>boolean</td> <td>Whether to allow selection</td>
 </tr> <tr>
    <td>Maximum number of horizontal cells</td> <td>repeatX</td> <td>number</td> <td>maximum number of horizontal cells</td>
 </tr> <tr>
    <td>CellWidth</td> <td>itemWidth</td> <td>number</td> <td>CellWidth</td>
 </tr> <tr>
    <td>Cell Height</td> <td>itemHeight</td> <td>number</td> <td>Cell Height</td>
 </tr> <tr>
    <td>Cell horizontal spacing</td> <td>spaceX</td> <td>number</td> <td>Cell horizontal spacing</td>
 </tr> <tr>
    <td>Cell vertical spacing</td> <td>spaceY</td> <td>number</td> <td>Cell vertical spacing</td>
 </tr> <tr>
    <td>ScrollType</td> <td>scrollShowType</td> <td>number</td> <td>scrollType<br>0-no display<br>1-display<br>2-auto display<br>3-display vertical scrollbar only<br>4-display horizontal scrollbar only</td>
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
    <td>SelectImageURL</td> <td>selectImageURL</td> <td>string</td> <td>selectEffectImage</td>
 </tr> <tr>
    <td>SelectImageGrid9</td> <td>selectImageGrid9</td> <td>string</td> <td>selectImageGrid9 (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
 </tr> <tr>
    <td>SelectedImageOnTop</td> <td>selectedImageOnTop</td> <td>boolean</td> <td>SelectedImageOnTop</td>
 </tr> <tr>
    <td>Cursor hover image</td> <td>overImageURL</td> <td>string</td> <td>Cursor effect image</td>
 </tr> <tr>
    <td>Cursor hover image nine-pane grid</td> <td>overImageGrid9</td> <td>string</td> <td>Cursor effect image nine-pane grid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Cursor hover image transparency</td> <td>overImageAlpha</td> <td>number</td> <td>cursor effect image transparency</td>
 </tr> <tr>
    <td>Is the cursor hover image at the top</td> <td>overImageOnTop</td> <td>boolean</td> <td>Is the cursor effect image at the top</td>
 </tr> <tr>
    <td>Mouse hover is selected mode</td> <td>overSelectMode</td> <td>boolean</td> <td>mouse hover is selected effect (default is hover effect)</td>
 </tr> <tr>
    <td>Sliding content area scrolling</td> <td>slowmotionType</td> <td>number</td> <td>sliding the area inside the container with the mouse or hand scrolls the content area inside (needs to be turned on to limit the display to the area and the actual internal content size to be beyond the display area)<br>0- enable this effect for mobile only<br >1-Always enable this effect<br>2-None</td>
 </tr> </table>

## Reference-API
[API-Standalone version - List component:UIList](?file=006-API-2D单机内核/002-客户端/003-界面/019-UIList)<br>
[API-Network version - List component:UIList](?file=007-API-2D网络内核/002-客户端/003-界面/019-UIList)<br>
