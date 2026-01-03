# Camera Lens
>Generally used as a shot of the scene, the coordinates are the center point of the shot<br>For example, if a camera is used in the scene Game.currentScene.camera<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-03-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **viewPort** : Rectangle;<br>Contains the camera position and visible width and height Default = new Rectangle(0, 0, 100, 100)  |
| **rotation** : number;<br>Lens rotation angle Default=0  |
| **offsetX** : number;<br>Lens offset x Default value = 0  |
| **offsetY** : number;<br>Lens offset y Default value = 0  |
| **z** : number;<br>Lens z-axis position Default value = 0  |
| **scaleX** : number;<br>Camera lens zoom x (scene specific) default = 1  |
| **scaleY** : number;<br>Camera lens zoom y (scene specific) default = 1  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| (): sceneObject ClientSceneObject<br>The lens locks the scene object, after locking the scene object will be the view center point, if set to null then the viewPort is calculated

## Details



## sceneObject:ClientSceneObject
###### (): sceneObject ClientSceneObject :
The lens locks the scene object, after locking the scene object will be the view center point, if set to null then the viewPort is calculated




# Related code examples
The camera jumps to the specified scene location (e.g. pixel coordinate point 500,500):<br>
>// First unlock the target, if the target is not locked, you can not call this code<br>
>Game.currentScene.camera.sceneObject = null;<br>
>// Set the specified position again<br>
>Game.currentScene.camera.viewPort.x = 500;<br>
>Game.currentScene.camera.viewPort.y = 500;<br>
>

<br>
The camera moves slowly to the specified scene location (with smooth movement effect)<br>
>// First unlock the target, if the target is not locked, you can not call this code<br>
>Game.currentScene.camera.sceneObject = null;<br>
>// Moves the camera to the pixel coordinates 500,500 in 2000 milliseconds in the form of Ease.strongOut jogging<br>
>Tween.to(Game.currentScene.camera.viewPort, { x: 500, y: 500 }, 2000, Ease.strongOut);<br>
>

<br>
Lens zoom (with smooth movement effect)<br>
>// First unlock the target, if the target is not locked, you can not call this code<br>
>Game.currentScene.camera.sceneObject = null;<br>
>// Scaling the lens to 0.5 (i.e. 50%) with 1000 ms in the form of Ease.strongOut jogging<br>
>Tween.to(Game.currentScene.camera, { scaleX: 0.5, scaleY: 0.5 }, 1000, Ease.strongOut);<br>
>

<br>
Continuous lens rotation effect<br>
>// Scaling the lens to 0.5 (i.e. 50%) with 1000 ms in the form of Ease.strongOut jogging<br>
>os.add_ENTERFRAME(() => {<br>
>&nbsp;&nbsp;&nbsp;Game.currentScene.camera.rotation++;<br>
>}, this);<br>
>


