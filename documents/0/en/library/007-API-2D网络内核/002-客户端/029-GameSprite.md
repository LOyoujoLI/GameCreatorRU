# GameSprite Game Genie Class
>Base class for various advanced display objects (subclasses include Avatar, GCAnimation, various UI controls, etc.)）<br>-- Filter overlay implementation (i.e. parent-child filters are not overwritten but overlaid)<br>-- Hue (R+,B+,G+,GRAY,Rx,Gx,Bx)<br>-- Color phase (using ColorMatrix)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-02-01

**Inheritance**  →Sprite<br>
**Subcategories**  [GCAnimation](?file=007-API-2D网络内核/002-客户端/011-GCAnimation)、[Avatar](?file=007-API-2D网络内核/002-客户端/013-Avatar)、[ClientSceneLayer](?file=007-API-2D网络内核/002-客户端/018-ClientSceneLayer)、[GameImageLayer](?file=007-API-2D网络内核/002-客户端/027-GameImageLayer)、[GameLayer](?file=007-API-2D网络内核/002-客户端/028-GameLayer)<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[ON_DISPOSE](#ON_DISPOSE)** : string;<br>[Static] Event: When the event dispatched before destruction  |
| **objectID** : number;<br>Unique ID  |
| **isDisposed** : boolean;<br>Released or not  |
| **data** : any;<br>Loaded custom data, in addition to the object interface as a List of items displayed, this variable will record its corresponding UIListItemData  |
| **opacity** : number;<br>Transparency final transparency alpha = opacity * dpOpacity * opacityPer (currently only used in the editor)  |
| **rotation1** : number;<br>Rotation1 Final rotation rotation = rotation1 + rotation2 Default value = 0  |
| **rotation2** : number;<br>Rotation2 Final rotation rotation = rotation1 + rotation2 Default = 0  |
| **filterEnabled** : boolean;<br>Whether or not to allow the use of filters (material effects will only take effect if they are allowed) Default value = true  |
| **[hue](#hue)** : number;<br>Hue -180~180  |
| **[blur](#blur)** : number;<br>Fuzzy degree 0~N  |
| **disabled** : boolean;<br>Unavailable state, will disable mouse response and adjust to grayscale  |
| **dpX** : number;<br>Depth coordinate system: horizontal coordinates  |
| **dpY** : number;<br>Depth coordinate system: vertical coordinates  |
| **dpZ** : number;<br>Depth coordinate system: depth, the distance between this value and the camera depth determines the actual display effect, such as near large and far small  |
| **dpWidth** : number;<br>Depth coordinate system: height (pixels)  |
| **dpHeight** : number;<br>Depth coordinate system: width (pixels)  |
| **dpOpacity** : number;<br>Depth coordinate system: transparency, the final transparency will be multiplied by this value  |
| **dpScaleX** : number;<br>Depth coordinate system: horizontal scaling Default value = 1 means 100%  |
| **dpScaleY** : number;<br>Depth coordinate system: vertical scaling Default value = 1 means 100%  |
| **useDPCoordScaleMode** : boolean;<br>Whether to use zoom mode, pictures generally change the size, while the interface, animation, standing avatar generally change the zoom ratio  |
| **dpDisplayPriority** : number;<br>Display priority, used to distinguish the display when the same depth dpZ, the larger, the more in front of the display  |
| **_dpDirty** : boolean;<br>Variables used to implement the depth coordinate system code at the project level: dirty marker  |
| **_dpCameraX** : number;<br>Variables used to implement the depth coordinate system code for the project layer: camera horizontal coordinates  |
| **_dpCameraY** : number;<br>Variables used to implement the depth coordinate system code for the project layer: camera vertical coordinates  |
| **_dpCameraZ** : number;<br>Variables used to implement the depth coordinate system code for the project layer: camera depth coordinates  |
| **_dpTextureWidth** : number;<br>Variable used to implement the depth coordinate system code for the project layer: actual image size width  |
| **_dpTextureHeight** : number;<br>Variable used to implement the depth coordinate system code for the project layer: the actual size of the image height  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[setTonal](#setTonal)**(r : number,  g : number,  b : number,  gray : number,  mr? : number,  mg? : number,  mb? : number): void<br>Change Tone
| **[getTonal](#getTonal)**(): number[]<br>Get the hue parameters.r g b gray mr mg mb
| **[isInherit](#isInherit)**(sp : TreeNode): boolean<br>Whether to inherit from the specified object
| **[dpCoordToRealCoord](#dpCoordToRealCoord)**(): void<br>Calculate and set [actual coordinates] based on [depth coordinates].
| **[realCoordToDPCoord](#realCoordToDPCoord)**(calcCoord : boolean,  calcSize : boolean): any<br>Convert to [depth coordinates] based on [actual coordinates
| **[installMaterialData](#installMaterialData)**(materialData : any,  resetTime? : boolean): void<br>Installation material data
| **[getAllMaterialDatas](#getAllMaterialDatas)**(): any[]<br>Get the full material data you currently have, which can be used for storage, and installMaterialData to install the material data.
| **[addMaterial](#addMaterial)**(materialData : MaterialData,  passage? : number): boolean<br>Add material, based on material data
| **[addMaterialAt](#addMaterialAt)**(materialData : MaterialData,  index : number,  passage? : number): boolean<br>Add a material to the specified location, based on the material data
| **[addMaterialByID](#addMaterialByID)**(materialID : number,  passage? : number): boolean<br>Add material, use default values for material parameters according to material ID
| **[addMaterialAtByID](#addMaterialAtByID)**(materialID : number,  index : number,  passage? : number): boolean<br>Add material, use default values for material parameters according to material ID
| **[removeMaterial](#removeMaterial)**(materialData : MaterialData,  passage? : number): boolean<br>Remove the material, based on the material data, or if the data already exists inside, it will be removed
| **[removeMaterialAt](#removeMaterialAt)**(index : number,  passage? : number): boolean<br>Remove the material, depending on where it is located
| **[removeMaterialByID](#removeMaterialByID)**(materialID : number,  passage? : number): boolean<br>Remove material, based on material ID
| **[getMaterialByID](#getMaterialByID)**(materialID : number,  passage? : number): MaterialData<br>Get material data, based on ID
| **[getMaterialAt](#getMaterialAt)**(index : number,  passage? : number): MaterialData<br>Get material data, indexed by location
| **[getMaterialLength](#getMaterialLength)**(passage? : number): number<br>Get the total number of material data in the specified channel
| **[getMaterialPassLength](#getMaterialPassLength)**(): number<br>Get the total number of material channels
| **[clearMaterials](#clearMaterials)**(): void<br>Clear all materials
| **[clearMaterialsInPass](#clearMaterialsInPass)**(passage : number,  deletePass? : boolean): void<br>Clear the material in the specified channel
| **[setMaterialIndex](#setMaterialIndex)**(material : MaterialData,  toIndex : number,  passage? : number): boolean<br>Change the material position in the same channel
| **[swapMaterialIndex](#swapMaterialIndex)**(fromIndex : number,  toIndex : number,  passage? : number): boolean<br>Change material location
| **[swapMaterialPass](#swapMaterialPass)**(passFromIndex : number,  passToIndex : number): boolean<br>Change the channel order, the channel order affects the rendering sequence
| **[setMaterialsByGameSprite](#setMaterialsByGameSprite)**(gameSprite : [GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite),  cloneMode : boolean): void<br>Set to the same material as the specified GameSprite
| **[setMaterialDirty](#setMaterialDirty)**(): void<br>Calling this function means that the material has been changed, allowing the system to render based on the latest material calculation
| **[setMaterialValueFast](#setMaterialValueFast)**(materialValues : any,  passage? : number): void<br>Calling this function to quickly set the value passed to the shader is a bit more efficient than calling setMaterialDirty after directly modifying the material, reducing the data conversion calculation.

## Details

### ON_DISPOSE
###### ON_DISPOSE : string;
[Static] Event: When the event dispatched before destruction<br>
>// Create Object<br>
>var sp = new GameSprite();<br>
>// Listening for events when destroyed<br>
>sp.once(GameSprite.ON_DISPOSE,this,()=>{<br>
>&nbsp;&nbsp;// to do<br>
>});<br>
>// Destroy the object<br>
>sp.dispose();<br>
>


### hue
###### hue : number;
Hue -180~180<br>
Internal implementation with Tone Filter
### blur
###### blur : number;
Fuzzy degree 0~N<br>
Internal implementation using blur filter


## setTonal
###### **[setTonal](#setTonal)**(r : number,  g : number,  b : number,  gray : number,  mr? : number,  mg? : number,  mb? : number): void :
Change Tone
##### Parameters
	r Red+ -255~255
	g Green+ -255~255
	b Blue+ -255~255
	gray 灰度 0-100
	mr [Optional] Default value=1 0~5
	mg [Optional] Default value=1 0~5
	mb [Optional] Default value=1 0~5



## getTonal
###### **[getTonal](#getTonal)**(): number[] :
Get hue parameters: r g b gray mr mg mb



## isInherit
###### **[isInherit](#isInherit)**(sp : TreeNode): boolean :
Whether to inherit from the specified object
##### Parameters
	sp Specified objects



## dpCoordToRealCoord
###### **[dpCoordToRealCoord](#dpCoordToRealCoord)**(): void :
Calculate and set [actual coordinates] based on [depth coordinates].<br>
Implemented by the upper project layer<br>
If you change dpX, dpY, dpWidth, dpHeight, set the actual x, y, width, height (or scaleX, scaleY) according to the current depth dpZ and the lens



## realCoordToDPCoord
###### **[realCoordToDPCoord](#realCoordToDPCoord)**(calcCoord : boolean,  calcSize : boolean): any :
Convert to [depth coordinates] based on [actual coordinates<br>
Implemented by the upper project layer<br>
If you want to get the dpX, dpY, dpWidth, dpHeight (or dpScaleX, dpScaleY) at the current depth after changing x, y, width, height
##### Parameters
	calcCoord Whether to calculate the coordinates, if so it will convert and set dpX and dpY to the converted values
	calcSize Whether to calculate the size, if so it will convert and set dpWidth and dpHeight to the converted values (dpScaleX and dpScaleY in useDPCoordScaleMode mode)

##### Return
[any] Return { dpX: number, dpy: number, dpScaleX: number, dpScaleY: number, dpWidth: number, dpHeight: number }

## installMaterialData
###### **[installMaterialData](#installMaterialData)**(materialData : any,  resetTime? : boolean): void :
Installation material data
##### Parameters
	materialData  Type { materials: MaterialData[] }[]
	resetTime [Optional] Default = true Whether to reset the transition time within the material data



## getAllMaterialDatas
###### **[getAllMaterialDatas](#getAllMaterialDatas)**(): any[] :
Get the full material data you currently have, which can be used for storage, and installMaterialData to install the material data.

##### Return
{ materials: MaterialData[] }[]

## addMaterial
###### **[addMaterial](#addMaterial)**(materialData : MaterialData,  passage? : number): boolean :
Add material, based on material data
##### Parameters
	material Material Data
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## addMaterialAt
###### **[addMaterialAt](#addMaterialAt)**(materialData : MaterialData,  index : number,  passage? : number): boolean :
Add a material to the specified location, based on the material data
##### Parameters
	material Material Data
	index position
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## addMaterialByID
###### **[addMaterialByID](#addMaterialByID)**(materialID : number,  passage? : number): boolean :
Add material, use default values for material parameters according to material ID
##### Parameters
	material Material Data
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## addMaterialAtByID
###### **[addMaterialAtByID](#addMaterialAtByID)**(materialID : number,  index : number,  passage? : number): boolean :
Add material, use default values for material parameters according to material ID
##### Parameters
	material Material Data
	index position
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## removeMaterial
###### **[removeMaterial](#removeMaterial)**(materialData : MaterialData,  passage? : number): boolean :
Remove the material, based on the material data, if the data already exists inside, it will be removed
##### Parameters
	materialData Material Data
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## removeMaterialAt
###### **[removeMaterialAt](#removeMaterialAt)**(index : number,  passage? : number): boolean :
Remove material, depending on where the material is located
##### Parameters
	index Index of the location of the material data
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## removeMaterialByID
###### **[removeMaterialByID](#removeMaterialByID)**(materialID : number,  passage? : number): boolean :
Remove material, based on material ID
##### Parameters
	materialID Material Data ID
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Is it successful

## getMaterialByID
###### **[getMaterialByID](#getMaterialByID)**(materialID : number,  passage? : number): MaterialData :
Get material data, based on ID
##### Parameters
	materialID Material Data ID
	passage [Optional] Default value = 0 The channel where

##### Return
[MaterialData] Material Data

## getMaterialAt
###### **[getMaterialAt](#getMaterialAt)**(index : number,  passage? : number): MaterialData :
Get material data, indexed by location
##### Parameters
	index Location Index
	passage [Optional] Default value = 0 The channel where

##### Return
[MaterialData] Material Data

## getMaterialLength
###### **[getMaterialLength](#getMaterialLength)**(passage? : number): number :
Get the total number of material data in the specified channel
##### Parameters
	passage [Optional] Default value = 0 The channel where

##### Return
[number]

## getMaterialPassLength
###### **[getMaterialPassLength](#getMaterialPassLength)**(): number :
Get the total number of material channels

##### Return
[number]

## clearMaterials
###### **[clearMaterials](#clearMaterials)**(): void :
Clear all materials



## clearMaterialsInPass
###### **[clearMaterialsInPass](#clearMaterialsInPass)**(passage : number,  deletePass? : boolean): void :
Clear the material in the specified channel
##### Parameters
	passage The channel where
	deletePass Delete Channel



## setMaterialIndex
###### **[setMaterialIndex](#setMaterialIndex)**(material : MaterialData,  toIndex : number,  passage? : number): boolean :
Change the material position in the same channel
##### Parameters
	material Material Data
	toIndex Location Index
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Whether the replacement is successful

## swapMaterialIndex
###### **[swapMaterialIndex](#swapMaterialIndex)**(fromIndex : number,  toIndex : number,  passage? : number): boolean :
Change material location
##### Parameters
	fromIndex The original location of the material
	toIndex New location to which material needs to be replaced
	passage [Optional] Default value = 0 The channel where

##### Return
[boolean] Whether the replacement is successful

## swapMaterialPass
###### **[swapMaterialPass](#swapMaterialPass)**(passFromIndex : number,  passToIndex : number): boolean :
Change the channel order, the channel order affects the rendering sequence
##### Parameters
	passFromIndex The original location of the material channel
	passToIndex New location to which material channels need to be replaced

##### Return
[boolean] Whether the replacement is successful

## setMaterialsByGameSprite
###### **[setMaterialsByGameSprite](#setMaterialsByGameSprite)**(gameSprite : [GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite),  cloneMode : boolean): void :
Set to the same material as the specified GameSprite
##### Parameters
	gameSprite Specified reference GameSprite
	cloneMode If yes, MaterialData is cloned, otherwise it is a reference to



## setMaterialDirty
###### **[setMaterialDirty](#setMaterialDirty)**(): void :
Calling this function means that the material has been changed, allowing the system to render based on the latest material calculation<br>
Normally, there is no need to call this function actively, but you can call it to refresh the object if you have modified the data inside MaterialData.



## setMaterialValueFast
###### **[setMaterialValueFast](#setMaterialValueFast)**(materialValues : any,  passage? : number): void :
Calling this function to quickly set the value passed to the shader is a bit more efficient than calling setMaterialDirty after directly modifying the material, reducing the data conversion calculation.<br>
This function can be called to optimize the calculation when, for example, the frame brush needs to update only a few values.<br>
<br>
[About variable name]<br>
-- Variable name specification: mu material number_variable property<br>
<br>
[About Value]<br>
-- number The attributes of the type are set directly<br>
-- The color attribute should be set to [r,g,b] where r/g/b is 0~1<br>
-- Mapping settings are not supported, and mapping changes still require<br>
<br>
[materialValues Parameter Specification]<br>
{<br>
&nbsp;&nbsp;&nbsp;mu2_abc: 1,<br>
&nbsp;&nbsp;&nbsp;mu3_color: [0.5,0.5,1]<br>
}<br>

##### Parameters
	materialValues Material data to be updated
	passage [Optional] Default value = 0 The channel where





