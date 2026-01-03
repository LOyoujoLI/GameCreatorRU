# Interface: Image Component UIBitmap
Component for displaying a picture, supports binding player string variables (string variables store addresses)

## Example diagram
 <img src="img/2/界面/2-5.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Image path</td> <td>image</td> <td>string</td> <td>Image skin path, or if using a variable, the corresponding image address will be displayed based on the current value of the variable</td>
 </tr> <tr>
    <td>Nine-pane grid</td> <td>grid9</td> <td>string</td> <td>nine-pane grid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Horizontal flip</td> <td>flip</td> <td>boolean</td> <td>Horizontal flip</td>
 </tr> <tr>
    <td>Axis point</td> <td>pivotType</td> <td>number</td> <td>Axis point (affects rotation, scaling of images)<br>0- top left corner<br>1-center point</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version Photo component:UIBitmap](?file=006-API-2D单机内核/002-客户端/003-界面/014-UIBitmap)<br>
[API-Network version Image component:UIBitmap](?file=007-API-2D网络内核/002-客户端/003-界面/014-UIBitmap)<br>
