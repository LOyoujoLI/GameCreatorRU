# AssetManager Resource Manager
>Use reference counting to cache resources, once the reference count is 0, the actual resources will be released automatically<br>Basic resources include: Image resources, Audio resources, JSON resources, Text resources, ArrayBuffer resources<br>[System Rules]<br>-- Advanced display objects contain a variety of base resources, in the creation of these advanced display objects will automatically increase the reference based on the internal association to the base resources, while the release of the object will reduce the reference, advanced display objects contain:<br>&nbsp;&nbsp;&nbsp;-- Avatar/StandAvatar Avatar/Standing Avatar<br>&nbsp;&nbsp;&nbsp;-- GCAnimation Animation<br>&nbsp;&nbsp;&nbsp;-- ClientScene Client Scenarios<br>&nbsp;&nbsp;&nbsp;-- ClientSceneObject Client-side scenario objects<br>&nbsp;&nbsp;&nbsp;-- UIxxx Various interface components (including the overall interface GUI_XXX)<br>&nbsp;&nbsp;&nbsp;-- Advanced display objects added by the project layer itself, etc.<br>-- Preloaded advanced resources, if not set to be automatically released, need to be manually released, otherwise they will keep referring to these resources resulting in not being automatically released.<br>&nbsp;&nbsp;&nbsp;The basic resources are loaded according to the editor's preset configuration, and the basic resources are unloaded according to the editor's preset configuration (independent of the fact that the internal resources are dynamically replaced by the actual scenes used).<br>&nbsp;&nbsp;&nbsp;It is mainly used to pre-occupy resources so that they will not be automatically released by the system during this period, for example, it is designed to pre-load some resources before entering a game scene and release them before entering the next scene so that they will not be automatically released by the system during that scene.<br>&nbsp;&nbsp;&nbsp;The preload interface contains--Pre-loaded advanced resources (each advanced resource contains several basic resources): self-loaded ones need to be unloaded by themselves<br>&nbsp;&nbsp;&nbsp;-- Pre-loaded scenes preLoadSceneAsset                 ==> Unloading scenarios disposeScene<br>&nbsp;&nbsp;&nbsp;-- Preloading scene objects preLoadSceneObjectAsset       ==> Unloading scene objects disposeSceneObject<br>&nbsp;&nbsp;&nbsp;-- Pre-loaded avatar resources preLoadAvatarAsset          ==> Uninstall avatar resources disposeAvatarAsset<br>&nbsp;&nbsp;&nbsp;-- Pre-loading of standing avatar resources preLoadStandAvatarAsset       ==> Uninstallation of standing avatar resources disposeStandAvatarAsset<br>&nbsp;&nbsp;&nbsp;-- Pre-loaded animation resources preLoadAnimationAsset         ==> Uninstall animation resources disposeAnimationAsset<br>&nbsp;&nbsp;&nbsp;-- Pre-loading interface resources preLoadUIAsset                ==> Uninstall interface resources disposeUIAsset<br>&nbsp;&nbsp;&nbsp;-- Preloading dialog box resources preLoadDialog               ==> Uninstall dialog box resources disposeDialog<br>&nbsp;&nbsp;&nbsp;-- Preload the resources involved in the event page preLoadCommandPage   ==> Uninstall the resources involved in the event page disposeCommandPage<br>-- The preload interface contains--Pre-loaded base resources: self-loaded need to unload themselves<br>&nbsp;&nbsp;&nbsp;-- Loading images (parsed as Object) loadImage                     ==> Release Pictures disposeImage<br>&nbsp;&nbsp;&nbsp;-- Load Json file (parsed to Object) loadJson                  ==> Free Json files disposeJson<br>&nbsp;&nbsp;&nbsp;-- Load text files (parsed as strings) loadText                   ==> Free text files disposeText<br>&nbsp;&nbsp;&nbsp;-- Load the original file (parsed as ArrayBuffer) loadFileArrayBuffer  ==> Free the original file disposeFileArrayBuffer<br>&nbsp;&nbsp;&nbsp;-- Loading Audio loadAudio                                   ==> Uninstall Audio disposeAudio<br>-- Resources for avatars used in dialogs<br>&nbsp;&nbsp;&nbsp;-- The headshot resource (reference +1) will be created at the start of each conversation, and then released (reference -1) when the conversation is stopped.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;These headshot resources can be preloaded in advance if you do not want them to be physically recycled by the system within a certain period of time.<br>[Summary]<br>&nbsp;&nbsp;&nbsp;-- Self-created objects need to be destroyed by themselves (gameObject.dispose)<br>&nbsp;&nbsp;&nbsp;-- Self-preloaded resources need to be destroyed by themselves (AssetManager.disposeXXX)<br>[Example 1: Self-created advanced object, self-destruction]<br>&nbsp;&nbsp;&nbsp;// Create a avatar instance #3 that the system recognizes as referencing some of the base resources associated with avatar #3 (+1 reference)<br>&nbsp;&nbsp;&nbsp;var a = new Avatar;<br>&nbsp;&nbsp;&nbsp;a.id = 3;<br>&nbsp;&nbsp;&nbsp;// Release the instance, only after calling release these base resources that were added to the reference will be reduced to allow the system to automatically reclaim the resource (reference-1)<br>&nbsp;&nbsp;&nbsp;a.dispose();<br>&nbsp;&nbsp;&nbsp;// Create interface #2<br>&nbsp;&nbsp;&nbsp;var b = new GUI_2;<br>&nbsp;&nbsp;&nbsp;// Uninstallation 2 interface<br>&nbsp;&nbsp;&nbsp;b.dispose();<br>Example 2: Pre-loaded resources, which will not be released by the system for a certain period of time and will be unloaded manually when they are finished being used]<br>&nbsp;&nbsp;&nbsp;// Preload Avatar #3 (reference +1) At this point the reference of Avatar #3 = 1<br>&nbsp;&nbsp;&nbsp;AssetManager.preLoadAvatarAsset(3, Callback.New(()=>{<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Use Avatar (reference +1) At this point the reference of Avatar #3 = 2<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var a = new Avatar;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a.id = 3;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// After 60 seconds<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;setTimeout(()=>{<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Uninstall Avatar (reference -1) At this point the reference of Avatar #3 = 1<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a.dispose();<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Uninstall the pre-loaded Avatar #3 occupancy (reference -1) At this point the reference of Avatar #3 = 0 The system will automatically recycle<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AssetManager.disposeAvatarAsset(3);<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},60*1000);<br>&nbsp;&nbsp;&nbsp;}));<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-08-08

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **assetCountMap** : {<br>[Static] All resource reference count url(resource address):reference count default={}  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[preLoadSceneAsset](#preLoadSceneAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload the scene resources, if autoDispose is false, then you need to unload manually: AssetManager::disposeScene
| **[preLoadSceneObjectAsset](#preLoadSceneObjectAsset)**(so : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject),  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload scene object resources, if autoDispose is false, then you need to unload manually: AssetManager::disposeSceneObject
| **[preLoadAvatarAsset](#preLoadAvatarAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload Avatar data, if autoDispose is false then you need to unload it manually: AssetManager::disposeAvatarAsset
| **[preLoadStandAvatarAsset](#preLoadStandAvatarAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload the standing avatar data, if autoDispose is false, then you need to unload it manually: AssetManager::disposeStandAvatarAsset
| **[preLoadUIAsset](#preLoadUIAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload the interface, if autoDispose is false then you need to unload it manually: AssetManager::disposeUIAsset
| **[preLoadAnimationAsset](#preLoadAnimationAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Preload animation, if autoDispose is false then you need to unload it manually: AssetManager::disposeAnimationAsset
| **[preLoadCommandPage](#preLoadCommandPage)**(commandPage : [CommandPage](?file=007-API-2D网络内核/001-通用/013-CommandPage),  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean): void<br>[Static] Preload the resources contained in the event page, if autoDispose is false then you need to manually unload: AssetManager::disposeCommandPage
| **[preLoadDialog](#preLoadDialog)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean): void<br>[Static] Preload the resources related to the dialog style, if autoDispose is false then you need to unload it manually: AssetManager::disposeDialog
| **[preloadFonts](#preloadFonts)**(complete? : Callback,  syncCallbackWhenAssetExist? : boolean): void<br>[Static] Preload all fonts preset in the editor (from "File Font Import Management" in Settings)
| **[preloadFont](#preloadFont)**(fontUrl : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean): void<br>[Static] Preload the specified font file
| **[batchPreLoadAsset](#batchPreLoadAsset)**(onFin : Callback,  onProgress : Callback,  images : string[],  scenes : number[],  avatars : number[],  standAvatars : number[],  animations? : number[],  uis? : number[],  jsons? : string[],  audios? : string[],  dialogs? : number[],  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void<br>[Static] Batch Loading Advanced Resources
| **[batchDisposeAsset](#batchDisposeAsset)**(images : string[],  scenes : number[],  avatars : number[],  standAvatars : number[],  animations? : number[],  uis? : number[],  jsons? : string[],  audios? : string[],  dialogs? : number[]): void<br>[Static] Bulk Uninstallation of Advanced Resources
| **[disposeScene](#disposeScene)**(id : number): void<br>[static] to release the scene resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
| **[disposeSceneObject](#disposeSceneObject)**(so : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject)): void<br>[static] to release the scene object resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
| **[disposeAvatarAsset](#disposeAvatarAsset)**(id : number): void<br>[static] to release Avatar resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
| **[disposeStandAvatarAsset](#disposeStandAvatarAsset)**(id : number): void<br>[static] to release the standing avatar resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
| **[disposeUIAsset](#disposeUIAsset)**(id : number): void<br>[static] release interface, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
| **[disposeAnimationAsset](#disposeAnimationAsset)**(id : number): void<br>[static] release animation, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
| **[disposeCommandPage](#disposeCommandPage)**(commandPage : [CommandPage](?file=007-API-2D网络内核/001-通用/013-CommandPage)): void<br>[static] to release the resources loaded due to the preload event page, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
| **[disposeDialog](#disposeDialog)**(id : number): void<br>[static] preload the resources related to the style of dialog box, each call to this function reduces the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general the destruction of the object that will automatically destroy its associated resources)
| **[loadImage](#loadImage)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean,  prerender? : boolean): void<br>[Static] Loading images
| **[loadTexture](#loadTexture)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Loading Texture particle images
| **[loadImages](#loadImages)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean,  prerender? : boolean): void<br>[Static] Load image set, ignore empty addresses, always return the loaded callback
| **[loadTextures](#loadTextures)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Load Texture particle image set, ignore the empty address, always return the loaded callback
| **[loadAudio](#loadAudio)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>Static】Load audio files support formats .mp3 .ogg
| **[loadAudios](#loadAudios)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Load the audio file set, ignore the empty address, always return the loaded callback
| **[loadJson](#loadJson)**(url : string,  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Loading and parsing JSON files
| **[loadJsons](#loadJsons)**(urls : string[],  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Load and parse JSON file set, ignore empty addresses, always return the loaded callback
| **[loadText](#loadText)**(url : string,  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Loading Text files
| **[loadTexts](#loadTexts)**(urls : string[],  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void<br>[Static] Loading Text file set
| **[loadFileArrayBuffer](#loadFileArrayBuffer)**(url : string,  complete : Callback,  useRef? : boolean): void<br>[Static] Loading File Resources (Binary)
| **[getImage](#getImage)**(url : string): Texture<br>[Static] Get mapping resources
| **[getJson](#getJson)**(url : string): any<br>[Static] Get JSON resources
| **[getText](#getText)**(url : string): string<br>[Static] Get text resource
| **[getFileArrayBuffer](#getFileArrayBuffer)**(url : string): ArrayBuffer<br>[Static] Get file resources (binary)
| **[disposeImage](#disposeImage)**(url : string,  force? : boolean): void<br>[Static] Unload picture resources: When the reference count is 0, it will be delayed to clean up all the actual resources and all their cutout resources (need to ensure that the cutout resources Graphics external no longer reference)
| **[disposeImages](#disposeImages)**(urls : string[],  force? : boolean): void<br>[Static] Unload picture resource set: When the reference count is 0, all the actual resources and all their cutout resources will be cleaned up after a delay (need to ensure that the cutout resources Graphics external reference is no longer available)
| **[disposeAudio](#disposeAudio)**(url : string,  force? : boolean): void<br>[Static] Unload audio resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
| **[disposeJson](#disposeJson)**(url : string,  force? : boolean): void<br>[Static] Unload JSON resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
| **[disposeText](#disposeText)**(url : string,  force? : boolean): void<br>[Static] Unload text resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
| **[disposeFileArrayBuffer](#disposeFileArrayBuffer)**(url : string,  force? : boolean): void<br>[Static] Unloading File Resources (Binary)
| **[getClipImage](#getClipImage)**(url : string,  x : number,  y : number,  rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): Graphics<br>[Static] Get the sliced mapping resource according to the image address: the whole resource must have been loaded, when there is no corresponding cut will be temporarily cut once
| **[drawToTexture](#drawToTexture)**(source : any,  textureWidth : number,  textureHeight : number,  offsetX? : number,  offsetY? : number,  mipmap? : boolean,  minFifter? : number,  magFifter? : number): Texture<br>[Static] Screenshot of the display object as a mapping resource (video memory), the size of the mapping is limited by the actual screen size
| **[drawToAtlasSprite](#drawToAtlasSprite)**(source : any,  width : number,  height : number,  mipmap? : boolean,  minFifter? : number,  magFifter? : number,  offsetX? : number,  offsetY? : number): Sprite<br>[Static] Draw to the container as a collage (collage is required because the device limits the size of the map), you need to call disposeAtlasSprite to actively release these maps on the video memory
| **[bigTextureToAtlasSprite](#bigTextureToAtlasSprite)**(texture : Texture,  xLoop? : boolean,  yLoop? : boolean,  mapWidth? : number,  mapHeight? : number): Sprite<br>[Static] Convert large mapping to jigsaw display object to solve the problem that large mapping cannot be displayed when it exceeds the maximum supported mapping size (os.MAX_TEXTURE_SIZE) of graphics card
| **[disposeAtlasSprite](#disposeAtlasSprite)**(root : Sprite): void<br>[Static] Release the tessellated map, i.e., the tessellated map display object generated by drawToAtlasSprite
| **[prerender](#prerender)**(source : any): void<br>[Static] Pre-rendering
| **[textureToBase64](#textureToBase64)**(texture : Texture): string<br>[Static] Mapping to base64 format
| **[textureToArrayBuffer](#textureToArrayBuffer)**(texture : Texture): ArrayBuffer<br>[Static] Mapping to ArrayBuffer format
| **[arrayBufferToTexture](#arrayBufferToTexture)**(arrayBuffer : ArrayBuffer,  onFin : Callback): void<br>[Static] ArrayBuffer to Mapping
| **[arrayBufferToBase64](#arrayBufferToBase64)**(arrayBuffer : ArrayBuffer): string<br>[Static] ArrayBuffer to Base64
| **[base64ToTexture](#base64ToTexture)**(base64 : string,  onFin : Callback): void<br>[Static] ArrayBuffer to Mapping
| **[base64ToArrayBuffer](#base64ToArrayBuffer)**(base64 : string): ArrayBuffer<br>[Static] ArrayBuffer to Base64

## Details



## preLoadSceneAsset
###### **[preLoadSceneAsset](#preLoadSceneAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload the scene resources, if autoDispose is false, then you need to unload manually: AssetManager::disposeScene<br>
-- The relevant JSON file for the scenario<br>
-- If preload map resources are checked: Preload map resources: pictures of layers, pictures of blocks, BGM, BGS<br>
-- If you check Preload Full Scene Object Resources: Preload Full Scene Object Resources (available only for standalone version)<br>
-- If you check Preload resources involved in scene events: Preload resources in the event page triggered by the scene Refer to the preLoadCommandPage method (only available in standalone version)<br>
-- Preset list of custom preloaded resources
##### Parameters
	id Scene ID
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if this is turned on



## preLoadSceneObjectAsset
###### **[preLoadSceneObjectAsset](#preLoadSceneObjectAsset)**(so : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject),  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload scene object resources, if autoDispose is false, then you need to unload manually: AssetManager::disposeSceneObject<br>
-- Load all resources under a custom display object layer (Avatar, interface, animation) based on it
##### Parameters
	so Scene object data
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if this is turned on



## preLoadAvatarAsset
###### **[preLoadAvatarAsset](#preLoadAvatarAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload Avatar data, if autoDispose is false then you need to unload it manually: AssetManager::disposeAvatarAsset
##### Parameters
	id Avatar ID
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=true whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	isStandAvatar [Optional] Default=false Whether it is a standing avatar resource
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if you turn this on



## preLoadStandAvatarAsset
###### **[preLoadStandAvatarAsset](#preLoadStandAvatarAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload the standing avatar data, if autoDispose is false, then you need to unload it manually: AssetManager::disposeStandAvatarAsset
##### Parameters
	id standing avatar Resource ID
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if this is turned on



## preLoadUIAsset
###### **[preLoadUIAsset](#preLoadUIAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload the interface, if autoDispose is false then you need to unload it manually: AssetManager::disposeUIAsset
##### Parameters
	id Interface ID
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if this is turned on



## preLoadAnimationAsset
###### **[preLoadAnimationAsset](#preLoadAnimationAsset)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Preload animation, if autoDispose is false then you need to unload it manually: AssetManager::disposeAnimationAsset
##### Parameters
	id Animation ID
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether to pre-render image resources to ensure that the callback is completed without lagging due to rendering, generally you can try to turn this on when the resources are large, but there will be additional performance and memory overhead if this is turned on



## preLoadCommandPage
###### **[preLoadCommandPage](#preLoadCommandPage)**(commandPage : [CommandPage](?file=007-API-2D网络内核/001-通用/013-CommandPage),  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean): void :
[Static] Preload the resources contained in the event page, if autoDispose is false then you need to manually unload: AssetManager::disposeCommandPage<br>
(currently only available in stand-alone version, the network version of the event is executed on the server side, the client can not get the event data)<br>
(Only system kernel events are supported, if there are resources that need to be loaded into custom instructions support overriding to extend the method)<br>
-- Set object behavior events: Avatar resources<br>
-- Audio events: BGM - background music, BGS - ambient sound effects, SE - sound effects<br>
-- Interface Events: Interface<br>
-- Custom events: the project layer needs to append its own logic, for example, you can override this method to append logic<br>

##### Parameters
	commandPage Event Page Data
	complete [Optional] Default=null Callback on completion
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)



## preLoadDialog
###### **[preLoadDialog](#preLoadDialog)**(id : number,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean): void :
[Static] Preload the resources related to the dialog style, if autoDispose is false then you need to unload it manually: AssetManager::disposeDialog
##### Parameters
	id Dialog box style ID
	complete [Optional] Default=null Callback on completion
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)



## preloadFonts
###### **[preloadFonts](#preloadFonts)**(complete? : Callback,  syncCallbackWhenAssetExist? : boolean): void :
[Static] Preload all fonts preset in the editor (from "File Font Import Management" in Settings)
##### Parameters
	complete [Optional] Default=null Load completion callback
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)



## preloadFont
###### **[preloadFont](#preloadFont)**(fontUrl : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean): void :
[Static] Preload the specified font file
##### Parameters
	fontUrl such as asset/xxx.ttf
	complete [Optional] Default=null Load completion callback
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)



## batchPreLoadAsset
###### **[batchPreLoadAsset](#batchPreLoadAsset)**(onFin : Callback,  onProgress : Callback,  images : string[],  scenes : number[],  avatars : number[],  standAvatars : number[],  animations? : number[],  uis? : number[],  jsons? : string[],  audios? : string[],  dialogs? : number[],  syncCallbackWhenAssetExist? : boolean,  autoDispose? : boolean,  prerender? : boolean): void :
[Static] Batch Loading Advanced Resources
##### Parameters
	onFin Callback when loading is complete
	onProgress [optional] default=null callback onProgress(current:number,count:number); current number of loads,total number of loads
	images [optional] default=[] set of paths to images to be loaded
	scenes [Optional] Default = [] Set of scene IDs to be loaded
	avatars [optional] default=[] set of avatar IDs to be loaded
	standAvatars [Optional] Default=[] Set of standing avatar IDs to be loaded
	animations [Optional] Default=[] The set of animation IDs to be loaded
	uis  [optional] default=[] UI set to be loaded
	jsons [optional] default=[] JSON set to be loaded
	audios [Optional] Default=[] Audio set to be loaded
	dialogs [Optional] Default=[] The style of the dialog to be loaded
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	autoDispose [optional] default=false whether to release the resource automatically (it will be released automatically after a delay after loading, for reference count reduction)
	prerender [Optional] Default=false Whether or not to pre-render the image resources, to ensure that the callback is completed without lagging due to rendering, generally you can try to enable this when the resources are large



## batchDisposeAsset
###### **[batchDisposeAsset](#batchDisposeAsset)**(images : string[],  scenes : number[],  avatars : number[],  standAvatars : number[],  animations? : number[],  uis? : number[],  jsons? : string[],  audios? : string[],  dialogs? : number[]): void :
[Static] Bulk Uninstallation of Advanced Resources
##### Parameters
	images [optional] default=[] set of image paths to be unloaded
	scenes [Optional] Default = [] Set of scenario IDs to be unloaded
	avatars [optional] default=[] avatar IDs set to be uninstalled
	standAvatars [Optional] Default=[] Set of standing avatar IDs to uninstall
	animations [optional] default=[] set of animation IDs to be unloaded
	uis  [Optional] Default=[] Interface set to be uninstalled
	jsons [optional] default=[] JSON set to be offloaded
	audios [Optional] Default=[] Audio set to be loaded
	dialogs [Optional] Default=[] The style of the dialog to be loaded



## disposeScene
###### **[disposeScene](#disposeScene)**(id : number): void :
[static] to release the scene resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
##### Parameters
	id Scene ID



## disposeSceneObject
###### **[disposeSceneObject](#disposeSceneObject)**(so : [SceneObject](?file=007-API-2D网络内核/001-通用/024-SceneObject)): void :
[static] to release the scene object resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
##### Parameters
	so Scene object data



## disposeAvatarAsset
###### **[disposeAvatarAsset](#disposeAvatarAsset)**(id : number): void :
[static] to release Avatar resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
##### Parameters
	id Avatar ID



## disposeStandAvatarAsset
###### **[disposeStandAvatarAsset](#disposeStandAvatarAsset)**(id : number): void :
[static] to release the standing avatar resources, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of the object that will automatically destroy its associated resources)
##### Parameters
	id Standing avatar ID



## disposeUIAsset
###### **[disposeUIAsset](#disposeUIAsset)**(id : number): void :
[static] release interface, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
##### Parameters
	id Interface ID



## disposeAnimationAsset
###### **[disposeAnimationAsset](#disposeAnimationAsset)**(id : number): void :
[static] release animation, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
##### Parameters
	id Animation ID



## disposeCommandPage
###### **[disposeCommandPage](#disposeCommandPage)**(commandPage : [CommandPage](?file=007-API-2D网络内核/001-通用/013-CommandPage)): void :
[static] to release the resources loaded due to the preload event page, each call to this function to reduce the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general, the destruction of objects that will automatically destroy its associated resources)
##### Parameters
	commandPage Event Page



## disposeDialog
###### **[disposeDialog](#disposeDialog)**(id : number): void :
[static] preload the resources related to the style of dialog box, each call to this function reduces the reference count, when the reference count is 0 will destroy the actual resources (please use caution, in general the destruction of the object that will automatically destroy its associated resources)
##### Parameters
	id Dialog box style ID



## loadImage
###### **[loadImage](#loadImage)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean,  prerender? : boolean): void :
[Static] Loading images
##### Parameters
	url Image address
	complete [Optional] Default=null Callback when complete(tex:Texture)
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once
	prerender [Optional] Default=false Whether or not to pre-render the image resources, to ensure that the callback is completed without lagging due to rendering, generally you can try to enable this when the resources are large



## loadTexture
###### **[loadTexture](#loadTexture)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Loading Texture particle images
##### Parameters
	url Image address
	complete [Optional] Default=null Callback when complete(tex:Texture)
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadImages
###### **[loadImages](#loadImages)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean,  prerender? : boolean): void :
[Static] Load the image set, ignore the empty address, always return the loaded callback
##### Parameters
	urls Image address set
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once
	prerender [Optional] Default=false Whether or not to pre-render the image resources, to ensure that the callback is completed without lagging due to rendering, generally you can try to enable this when the resources are large



## loadTextures
###### **[loadTextures](#loadTextures)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Load Texture particle image set, ignore the empty address, always return the loaded callback
##### Parameters
	urls Image address set
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadAudio
###### **[loadAudio](#loadAudio)**(url : string,  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
Static】Load audio files support formats .mp3 .ogg
##### Parameters
	url Audio file address
	complete [Optional] Default=null Callback on load completion
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadAudios
###### **[loadAudios](#loadAudios)**(urls : string[],  complete? : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Load the audio file set, ignore the empty address, always return the loaded callback
##### Parameters
	urls Audio file set
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadJson
###### **[loadJson](#loadJson)**(url : string,  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Loading and parsing JSON files
##### Parameters
	url json file address
	complete complete(jsonObj:any)
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadJsons
###### **[loadJsons](#loadJsons)**(urls : string[],  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Load and parse JSON file set, ignore empty addresses, always return the loaded callback
##### Parameters
	urls json file address set
	complete [Optional] Default=null
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadText
###### **[loadText](#loadText)**(url : string,  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Loading Text files
##### Parameters
	url File path
	complete
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadTexts
###### **[loadTexts](#loadTexts)**(urls : string[],  complete : Callback,  syncCallbackWhenAssetExist? : boolean,  useRef? : boolean): void :
[Static] Loading Text file set
##### Parameters
	urls File path set
	complete
	syncCallbackWhenAssetExist [optional] default=false synchronous callback when resource exists, otherwise need to wait one frame (asynchronous callback)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## loadFileArrayBuffer
###### **[loadFileArrayBuffer](#loadFileArrayBuffer)**(url : string,  complete : Callback,  useRef? : boolean): void :
[Static] Loading File Resources (Binary)
##### Parameters
	url File path set
	complete Callback function when loading is complete complete(arrayBuffer:ArrayBuffer)
	useRef [optional] default=true whether to use reference counting, if so, each call to the function will increase the reference count once



## getImage
###### **[getImage](#getImage)**(url : string): Texture :
[Static] Get mapping resources
##### Parameters
	url Image address

##### Return
[Texture] Mapping resource, or null if it doesn't exist

## getJson
###### **[getJson](#getJson)**(url : string): any :
[Static] Get JSON resources
##### Parameters
	url JSON file address

##### Return
[any] Object：Returns null if it does not exist

## getText
###### **[getText](#getText)**(url : string): string :
[Static] Get text resource
##### Parameters
	url Text Address

##### Return
[string] Text: return null if it does not exist

## getFileArrayBuffer
###### **[getFileArrayBuffer](#getFileArrayBuffer)**(url : string): ArrayBuffer :
[Static] Get file resources (binary)
##### Parameters
	url File Address

##### Return
[ArrayBuffer] Returns null if it does not exist

## disposeImage
###### **[disposeImage](#disposeImage)**(url : string,  force? : boolean): void :
[Static] Unload picture resources: When the reference count is 0, it will be delayed to clean up all the actual resources and all their cutout resources (need to ensure that the cutout resources Graphics external no longer reference)
##### Parameters
	url Image file address
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## disposeImages
###### **[disposeImages](#disposeImages)**(urls : string[],  force? : boolean): void :
[Static] Unload picture resource set: When the reference count is 0, all the actual resources and all their cutout resources will be cleaned up after a delay (need to ensure that the cutout resources Graphics external reference is no longer available)
##### Parameters
	urls Image file address collection
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## disposeAudio
###### **[disposeAudio](#disposeAudio)**(url : string,  force? : boolean): void :
[Static] Unload audio resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
##### Parameters
	url Audio file address
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## disposeJson
###### **[disposeJson](#disposeJson)**(url : string,  force? : boolean): void :
[Static] Unload JSON resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
##### Parameters
	url json file address
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## disposeText
###### **[disposeText](#disposeText)**(url : string,  force? : boolean): void :
[Static] Unload text resources, when the reference count is 0 will be delayed after cleaning up all the actual resources
##### Parameters
	url Text file address
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## disposeFileArrayBuffer
###### **[disposeFileArrayBuffer](#disposeFileArrayBuffer)**(url : string,  force? : boolean): void :
[Static] Unloading File Resources (Binary)
##### Parameters
	url File path set
	force [Optional] Default=false Whether to force uninstall, force uninstall ignores reference count



## getClipImage
###### **[getClipImage](#getClipImage)**(url : string,  x : number,  y : number,  rect : [Rectangle](?file=007-API-2D网络内核/001-通用/020-Rectangle)): Graphics :
[Static] Get the sliced mapping resource according to the image address: the whole resource must have been loaded, when there is no corresponding cut will be temporarily cut once
##### Parameters
	url Posting Address
	x Offset value displayed x
	y Offset value y displayed
	rect Sampling of textures Offset and width and height



## drawToTexture
###### **[drawToTexture](#drawToTexture)**(source : any,  textureWidth : number,  textureHeight : number,  offsetX? : number,  offsetY? : number,  mipmap? : boolean,  minFifter? : number,  magFifter? : number): Texture :
[Static] Screenshot of the display object as a mapping resource (video memory), the size of the mapping is limited by the actual screen size
##### Parameters
	source Source, Sprite or Graphics are available
	textureWidth Mapping width
	textureHeight Mapping height
	offsetX The offset X of source relative to the canvas
	offsetY The offset Y of source relative to the canvas
	mipmap [optional] default=false whether to use mipmap (i.e. find the corresponding mimap layer blend based on the mapping scaling size to solve the mapping jitter problem after scaling)
	minFifter [Optional] Default=0x2600 Sampling method when displaying reduced mapping 0x2600=neighborhood sampling 0x2601=linear sampling
	magFifter [Optional] Default=0x2600 Sampling method when displaying enlarged mapping 0x2600=neighborhood sampling 0x2601=linear sampling

##### Return
[Texture]

## drawToAtlasSprite
###### **[drawToAtlasSprite](#drawToAtlasSprite)**(source : any,  width : number,  height : number,  mipmap? : boolean,  minFifter? : number,  magFifter? : number,  offsetX? : number,  offsetY? : number): Sprite :
[Static] Draw to the container as a collage (collage is required because the device limits the size of the map), you need to call disposeAtlasSprite to actively release these maps on the video memory
##### Parameters
	source Source, Sprite or Graphics are available
	width The width to be intercepted
	height Height to be intercepted
	mipmap [optional] default=false whether to use mipmap (i.e. find the corresponding mimap layer blend based on the mapping scaling size to solve the mapping jitter problem after scaling)
	minFifter [Optional] Default=0x2600 Sampling method when displaying reduced mapping 0x2600=neighborhood sampling 0x2601=linear sampling
	magFifter [Optional] Default=0x2600 Sampling method when displaying enlarged mapping 0x2600=neighborhood sampling 0x2601=linear sampling
	offsetX The offset X of source relative to the canvas
	offsetY The offset Y of source relative to the canvas

##### Return
[Sprite]

## bigTextureToAtlasSprite
###### **[bigTextureToAtlasSprite](#bigTextureToAtlasSprite)**(texture : Texture,  xLoop? : boolean,  yLoop? : boolean,  mapWidth? : number,  mapHeight? : number): Sprite :
[Static] Convert large mapping to jigsaw display object to solve the problem that large mapping cannot be displayed when it exceeds the maximum supported mapping size (os.MAX_TEXTURE_SIZE) of graphics card
##### Parameters
	texture Mapping Resources
	xLoop [optional] default=false x loop
	yLoop [Optional] Default=false y-loop
	mapWidth [Optional] Default = 0 Puzzle width
	mapHeight [Optional] Default = 0 Puzzle height

##### Return
[Sprite] Mapping display object

## disposeAtlasSprite
###### **[disposeAtlasSprite](#disposeAtlasSprite)**(root : Sprite): void :
[Static] Release the tessellated map, i.e., the tessellated map display object generated by drawToAtlasSprite
##### Parameters
	root Collage display object



## prerender
###### **[prerender](#prerender)**(source : any): void :
[Static] Pre-rendering<br>
If the display object contains more resources, the first rendering may cause a lag. In order to make it not lag before rendering, you can go to a pre-rendering in loading or something like that.
##### Parameters
	Show object source Graphics | Sprite



## textureToBase64
###### **[textureToBase64](#textureToBase64)**(texture : Texture): string :
[Static] Mapping to base64 format
##### Parameters
	texture Poster

##### Return
[string] base64 string

## textureToArrayBuffer
###### **[textureToArrayBuffer](#textureToArrayBuffer)**(texture : Texture): ArrayBuffer :
[Static] Mapping to ArrayBuffer format
##### Parameters
	texture Poster

##### Return
[ArrayBuffer] ArrayBuffer byte arrays

## arrayBufferToTexture
###### **[arrayBufferToTexture](#arrayBufferToTexture)**(arrayBuffer : ArrayBuffer,  onFin : Callback): void :
[Static] ArrayBuffer to Mapping
##### Parameters
	arrayBuffer ArrayBuffer byte arrays
	onFin Callback when finished onFin(tex:Texture)

##### Return
[Texture] Poster

## arrayBufferToBase64
###### **[arrayBufferToBase64](#arrayBufferToBase64)**(arrayBuffer : ArrayBuffer): string :
[Static] ArrayBuffer to Base64
##### Parameters
	arrayBuffer ArrayBuffer byte arrays

##### Return
[string] base64 string

## base64ToTexture
###### **[base64ToTexture](#base64ToTexture)**(base64 : string,  onFin : Callback): void :
[Static] ArrayBuffer to Mapping
##### Parameters
	arrayBuffer ArrayBuffer byte arrays
	onFin Callback when finished onFin(tex:Texture)

##### Return
[Texture] Poster

## base64ToArrayBuffer
###### **[base64ToArrayBuffer](#base64ToArrayBuffer)**(base64 : string): ArrayBuffer :
[Static] ArrayBuffer to Base64
##### Parameters
	arrayBuffer ArrayBuffer byte arrays

##### Return
[string] base64 string



