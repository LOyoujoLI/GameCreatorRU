# Interface: Slider Components UISlider
Component for specifying a range min and max, sliding between min and max to obtain a value

## Example diagram
 <img src="img/2/界面/2-15.png" /><br>

## Property Description
<table>
 <tr>
    <td><b>Properties</b></td> <td><b>Property variable name</b></td> <td><b>Type</b></td> <td><b>Description</b></td>
 </tr> <tr>
    <td>Background image</td> <td>image1</td> <td>string</td> <td>Slider background image</td>
 </tr> <tr>
    <td>Background image nine-pane grid</td> <td>bgGrid9</td> <td>string</td> <td>Background image nine-pane grid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Slider image</td> <td>image2</td> <td>string</td> <td>slider image</td>
 </tr> <tr>
    <td>Slider image nine-pane grid</td> <td>blockGrid9</td> <td>string</td> <td>slider image nine-pane grid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Fill Image</td> <td>image3</td> <td>string</td> <td>Fill Image</td>
 </tr> <tr>
    <td>FillGraphNineGrid</td> <td>blockFillGrid9</td> <td>string</td> <td>FillGraphNineGrid (format: top margin, right margin, bottom margin, left margin, tiled or not)</td>
 </tr> <tr>
    <td>Step value</td> <td>step</td> <td>number</td> <td>step value</td>
 </tr> <tr>
    <td>Min</td> <td>number</td> <td>minimum value</td>
 </tr> <tr>
    <td>Maximum</td> <td>max</td> <td>number</td> <td>maximum</td>
 </tr> <tr>
    <td>Value</td>  <td>value</td> <td>number</td> <td>value</td>
 </tr> <tr>
    <td>Transverse mode</td> <td>transverseMode</td> <td>boolean</td> <td>Is it transverse mode</td>
 </tr> <tr>
    <td>Display mode</td> <td>blockFillMode</td> <td>number</td> <td>Mode of progress bar display<br>0-block mode<br>1-fill mode<br>2-block and fill at the same time</td>
 </tr> <tr>
    <td>Initial Slider Position</td> <td>blockPosMode</td> <td>number</td> <td>Default Slider Inner Boundary Alignment<br>0-slider inner boundary alignment<br>1-slider center point alignment<br>2-slider outer boundary alignment</td>
 </tr> <tr>
    <td>Fill image using mask</td> <td>fillStrething</td> <td>boolean</td> <td>Fill image using mask mode that does not stretch the control by the same width and height</td>
 </tr> </table>

## Reference-API
[API-Stand-alone version-slider assembly:UISlider](?file=006-API-2D单机内核/002-客户端/003-界面/023-UISlider)<br>
[API-Network version-slider assembly:UISlider](?file=007-API-2D网络内核/002-客户端/003-界面/023-UISlider)<br>
