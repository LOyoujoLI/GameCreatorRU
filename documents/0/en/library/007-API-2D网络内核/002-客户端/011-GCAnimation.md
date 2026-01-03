# GCAnimation Animated display objects
>-- Support for binding targets, with the ability to differentiate between adding animation layers above or below the target layer<br>-- Target effects support stacking<br>Usage:<br>var a = new GCAnimation();<br>a.id = 5;<br>stage.addChild(a);<br>Binding target, since it can be distinguished between adding to the top or bottom of the target layer, requires a lowLayer and a highLayer<br>var a = new GCAnimation();<br>a.id = 5;<br>a.addToGameSprite(target,lowLayer,highLayer);<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>&nbsp;GCAnimation.RENDER  Events dispatched during animation playback<br>&nbsp;GCAnimation.PLAY_START Animation start event<br>&nbsp;GCAnimation.PLAY_STOP Event when animation stops<br>&nbsp;GCAnimation.PLAY_COMPLETED Event on completion of animation play<br>&nbsp;GCAnimation.SIGNAL Signal Events<br>About the mouse event click area: when the mouse event is registered, the system will automatically determine the mouse response area according to the actual sub-display object of the current frame<br><br>
>Maintenance personnel:**黑暗之神KDS、feng**  
>Created on 2019-02-22

**Inheritance**  →GameSprite<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[RENDER](#RENDER)** : string;<br>[Static] Events: Events dispatched when onRender is executed  |
| **[PLAY_START](#PLAY_START)** : string;<br>[Static] Event: Animation playback start event  |
| **[PLAY_STOP](#PLAY_STOP)** : string;<br>[Static] Event: Event when animation stops  |
| **[PLAY_COMPLETED](#PLAY_COMPLETED)** : string;<br>[Static] event: animation play completion event, non-loop animation play finished dispatch  |
| **[SIGNAL](#SIGNAL)** : string;<br>[Static] Events: Signal Events  |
| **id** : number;<br>Animation ID  |
| **[syncLoadWhenAssetExist](#syncLoadWhenAssetExist)** : boolean;<br>Whether to load synchronously or not, when the resource exists, the current frame is displayed immediately  |
| **[prerender](#prerender)** : boolean;<br>Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.  |
| **fps** : number;<br>Frequency, default=Config.ANIMATION_FPS  |
| **silentMode** : boolean;<br>Disable sound mode: Ignore sound effects when playing this animation Default=false  |
| **sceneObject** : ClientSceneObject;<br>Binding a scene object will affect the sound more depending on the distance of the object from the center of the camera  |
| **offsetX** : number;<br>Horizontal offset, or offsetX pixels horizontally if present  |
| **offsetY** : number;<br>Vertical offset, or horizontal offset offsetY pixels if present  |
| **[showHitEffect](#showHitEffect)** : boolean;<br>Whether to show hit effect: The editor allows to check "Show only when hit" for the animation layer, turn this on to show the animation layer that contains only when hit  |
| **currentFrame** : number;<br>Current frame: get and set the current frame  |
| **loop** : boolean;<br>Whether the currently playing animation is looped or not Default=false  |
| **isPlaying** : boolean;<br>[Read Only] Whether it is playing  |
| **isLoading** : boolean;<br>[Read Only] Get whether it is loading or not  |
| **[target](#target)** : GameSprite;<br>Target object: the target object of the target effect of the animation.  |
| **totalFrame** : number;<br>[Read Only] Total frames of animation  |
| **isParticle** : boolean;<br>[Read Only] Whether it is particle animation  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[addToGameSprite](#addToGameSprite)**(target : GameSprite,  lowLayer : Sprite,  highLayer : Sprite): void<br>Add to the display object, while part of the animation layer can be displayed below the target and part of the animation layer above the target, and support target effects
| **[removeFromGameSprite](#removeFromGameSprite)**(): void<br>This function can be used to clean up after removing the animation binding, addToGameSprite
| **[gotoAndPlay](#gotoAndPlay)**(frame? : number): void<br>Jumping a frame for playback, crossing the border will automatically take the mode (e.g. frame length 10, playing 13 is playing 3)
| **[play](#play)**(): void<br>Playback starts at the current frame rate
| **[stop](#stop)**(frame? : number): void<br>Stop animation

## Details

### RENDER
###### RENDER : string;
[Static] Events: Events dispatched when onRender is executed<br>
>var ani = new GCAnimation();<br>
>ani.id = 1;<br>
>ani.on(GCAnimation.RENDER,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### PLAY_START
###### PLAY_START : string;
[Static] Event: Animation playback start event<br>
>var ani = new GCAnimation();<br>
>ani.id = 1;<br>
>ani.on(GCAnimation.PLAY_START,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### PLAY_STOP
###### PLAY_STOP : string;
[Static] Event: Event when animation stops<br>
>var ani = new GCAnimation();<br>
>ani.id = 1;<br>
>ani.on(GCAnimation.PLAY_STOP,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### PLAY_COMPLETED
###### PLAY_COMPLETED : string;
[Static] event: animation play completion event, non-loop animation play finished dispatch<br>
>var ani = new GCAnimation();<br>
>ani.id = 1;<br>
>ani.on(GCAnimation.PLAY_COMPLETED,this,()=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### SIGNAL
###### SIGNAL : string;
[Static] Events: Signal Events<br>
The animation editor allows you to customize the signal and set which keyframe to throw after it passes<br>
>var ani = new GCAnimation();<br>
>ani.id = 1;<br>
>ani.on(GCAnimation.SIGNAL,this,(signalID:number)=>{<br>
>&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>
>});<br>
>


### syncLoadWhenAssetExist
###### syncLoadWhenAssetExist : boolean;
Whether to load synchronously or not, when the resource exists, the current frame is displayed immediately<br>
LOADED event, it is recommended to listen to this event before setting the id
### prerender
###### prerender : boolean;
Pre-render: Enable this to ensure that the screen is rendered once before the EventObject.LOADED is dispatched, so that the screen can be rendered immediately afterwards and will not lag for the first time due to large resources.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Pre-rendering will consume a certain amount of performance, you can choose to use this in the case of larger and more animation resources, turning this on will have additional performance and memory overhead
### showHitEffect
###### showHitEffect : boolean;
Whether to show hit effect: The editor allows to check "Show only when hit" for the animation layer, turn this on to show the animation layer that contains only when hit<br>
Set this before playing the animation
### target
###### target : GameSprite;
Target object: the target object of the target effect of the animation.<br>
If you need part of the animation layer below the target and part of the animation layer above the target, you can use the addToGameSprite method


## addToGameSprite
###### **[addToGameSprite](#addToGameSprite)**(target : GameSprite,  lowLayer : Sprite,  highLayer : Sprite): void :
Add to the display object, while part of the animation layer can be displayed below the target and part of the animation layer above the target, and support target effects
##### Parameters
	target Target audience
	lowLayer Animation base layer (display levels below the target layer in the animation editor are added here)
	highLayer Animation High Level (display levels above the target layer in the animation editor are added here)



## removeFromGameSprite
###### **[removeFromGameSprite](#removeFromGameSprite)**(): void :
This function can be used to clean up after removing the animation binding, addToGameSprite



## gotoAndPlay
###### **[gotoAndPlay](#gotoAndPlay)**(frame? : number): void :
Jumping a frame for playback, crossing the border will automatically take the mode (e.g. frame length 10, playing 13 is playing 3)<br>
@frame [Optional] Default = 1 Jump to the specified number of frames Unit: frames Default Start from the beginning



## play
###### **[play](#play)**(): void :
Playback starts at the current frame rate



## stop
###### **[stop](#stop)**(frame? : number): void :
Stop animation
##### Parameters
	frame [Optional] Default=1 The number of frames to stay in case of frame animation is specified





