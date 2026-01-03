# SceneLayerData Scene layer data
>Layer data from a pre-defined scene in the editor<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-11-06

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **name** : string;<br>name  |
| **p** : boolean;<br>Representation of object layer flags  |
| **dx** : number;<br>Offset x Default value = 0  |
| **dy** : number;<br>Offset y Default = 0  |
| **scaleX** : number;<br>Scaling x Default = 1  |
| **scaleY** : number;<br>Scaling y Default = 1  |
| **skewX** : number;<br>Slope x Default value = 0  |
| **skewY** : number;<br>Slope y Default = 0  |
| **xMove** : number;<br>Auto scroll speed in x-direction Default=0  |
| **yMove** : number;<br>y-direction auto-scroll speed Default=0  |
| **prospectsPerX** : number;<br>Vision scale X-axis Default value = 1.0 means 100% Normal map is 100%, the smaller the value, the slower the movement, multiple vision is generally made by changing this property  |
| **prospectsPerY** : number;<br>Vision scale Y-axis Default value = 1.0 means 100% Normal map is 100%, the smaller the value the slower the movement, multiple vision is generally made by changing this property  |
| **xLoop** : boolean;<br>x-direction loop Default=false  |
| **yLoop** : boolean;<br>y-direction loop Default=false  |
| **opacity** : number;<br>Transparency Default=1  |
| **blendMode** : string;<br>Hybrid mode null/lighter/blend1-1 (Take the value range 0~14)  |
| **drawMode** : boolean;<br>Drawing mode true=block layer false=picture layer  |
| **tileData** : { texID: number; x: number; y: number; }[][];<br>Block data texID negative number means auto component Default = []  |
| **img** : string;<br>Panorama Address  |
| **tileTexIDs** : { [id: string]: boolean; };<br>Full block data referenced to the set of block ids id negative numbers indicate automatic components  |


