# UIAnimation Animation Components
>Encapsulated animated interface components<br>Related Events<br>&nbsp;EventObject.LOADED Event when resource loading is complete<br>&nbsp;GCAnimation.RENDER  Events dispatched during animation playback<br>&nbsp;GCAnimation.PLAY_START Animation start event<br>&nbsp;GCAnimation.PLAY_STOP Event when animation stops<br>&nbsp;GCAnimation.PLAY_COMPLETED Event on completion of animation play<br>&nbsp;GCAnimation.SIGNAL Signal Events<br>Usage:<br>var a = new UIAnimation();<br>a.animationID =5;<br>a.playType = 1;<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.LOADED,this,this.onLoaded);<br>a.on(GCAnimation.PLAY_COMPLETED,this,this.onLoaded);<br>About the mouse event click area: when the mouse event is registered, the system will automatically determine the mouse response area according to the actual sub-display object of the current frame<br><br>
>Maintenance personnel:**黑暗之神KDS、feng**  
>Created on 2019-04-03

**Inheritance**  →UIBase<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **animationID** : number;<br>Animation number used  |
| **playType** : number;<br>Playback Type 0-No Play 1-Play once 2-Loop Default=0  |
| **scaleNumberX** : number;<br>Horizontal Scaling 1 for 100% Default = 1  |
| **scaleNumberY** : number;<br>Vertical Scaling 1 for 100% Default = 1  |
| **silentMode** : boolean;<br>Disable sound mode: Ignore sound effects when playing this animation Default=false  |
| **[showHitEffect](#showHitEffect)** : boolean;<br>Whether to show hit effect: The editor allows to check "Show only when hit" for the animation layer, turn this on to show the animation layer that contains only when hit  |
| **playFps** : number;<br>Frequency: Default value=Config.ANIMATION_FPS  |
| **aniFrame** : number;<br>Start frame: Playback starts from this frame Default = 1  |
| **animation** : GCAnimation;<br>[Read-only] Get the animation element  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(showCircleWhenInEditor? : boolean)<br>Constructors

## Details

### showHitEffect
###### showHitEffect : boolean;
Whether to show hit effect: The editor allows to check "Show only when hit" for the animation layer, turn this on to show the animation layer that contains only when hit<br>
Set this before playing the animation Default=false


## constructor
###### **[constructor](#constructor)**(showCircleWhenInEditor? : boolean) :
Constructors
##### Parameters
	showCircleWhenInEditor [Optional] Default=true Whether to show dots when displayed in the editor





