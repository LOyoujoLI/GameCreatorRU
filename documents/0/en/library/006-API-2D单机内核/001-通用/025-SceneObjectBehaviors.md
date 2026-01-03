# SceneObjectBehaviors Object Behavior Processor - Base Class
>The framework of the object behavior is implemented, the specific behavior should work with the custom behavior editor and subclasses to achieve the actual effect, you must set the implClass in order to behavior editor support<br>Object behavior layer concept: each added set of behavior that is as a new layer, only the layer is executed before returning to the previous layer to continue to execute the behavior (the behavior of the loop can not return to the previous layer)<br>You need to actively call update to execute the behavior, using this feature you can make logic that, for example, does not execute the default behavior after entering the battle and continues to execute the behavior after leaving the battle<br>Regarding the production of custom behaviors:<br>1.Visualize the production behavior interface: GC Editor - Menu - Custom Editor - Custom Behavior<br>2.The project layer inherits such implementations of specific behaviors: for example, custom behavior #6, which has two parameters<br>&nbsp;&nbsp;private behavior6(a:number,b:number):void{<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Behavior realization<br>&nbsp;&nbsp;}<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-02-20

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **[EVENT_INDEX_CHANGE](#EVENT_INDEX_CHANGE)** : string;<br>[Static] Dispatch when current behavior level index changes EventUtils.happen(this, SceneObjectBehaviors.EVENT_INDEX_CHANGE, [v]);  |
| **implClass** : typeof SceneObjectBehaviors;<br>[static] implementation classes, i.e. subclasses, currently used by the behavior editor to correctly find the implementation classes in order to preview custom behaviors written at the project level in real time  |
| **so** : SceneObjectEntity;<br>Execution actor (may be an execution eventer or trigger eventer or other specified object)  |
| **targetSceneObject** : SceneObjectEntity;<br>Trigger Eventers  |
| **executor** : SceneObjectEntity;<br>The person who performs the event (the person who dispatches the act)  |
| **index** : number;<br>Index of the current behavior, dispatch events when changed SceneObjectBehaviors.EVENT_INDEX_CHANGE  |
| **loop** : boolean;<br>Whether circular  |
| **[ignoreProcess](#ignoreProcess)** : boolean;<br>Whether [for editor preview] ignores the process (means jump directly to the final result without playing the process)  |
## **Protected Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **behaviors** : [Function, any[]][];<br>Behavior Corresponding method Corresponding parameter Default value = []  |
| **behaviorData** : any;<br>Behavior data: Record original behavior data, such as [[Behavior1-ID,Parameter1,Parameter2],[Behavior2-ID,Parameter1,Parameter2],....]  |
| **[logicPause](#logicPause)** : boolean;<br>Pause markers for logic, such as behaviors that do not perform the next action until the end of the campaign (e.g. with the effect of Game.pause)  |
## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[toBehaviorData](#toBehaviorData)**(behaviorStr : string)<br>[Static] Data conversion: convert the data in string format to usable format, usually the behavior data in custom properties need to use this method after conversion
| **[constructor](#constructor)**(so : SceneObjectEntity,  loop : boolean,  targetSceneObject : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  onOver : Callback,  startIndex? : number,  executor? : SceneObjectEntity)<br>Constructors
| **[dispose](#dispose)**(): void<br>Release function, which is called when no longer in use in order to destroy
| **[setBehaviors](#setBehaviors)**(behaviorData : any[],  delayFrame? : number): void<br>Set the behavior data and parse it, which will clear all previous behaviors
| **[reset](#reset)**(defSceneObejct : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject)): void<br>[For Editor Preview]Reset: restore to the most initial state
| **[waitFrame](#waitFrame)**(frame : number): void<br>Wait for the specified number of frames and continue execution
| **[update](#update)**(): boolean<br>Update the behavior, you need to actively call this function to execute the behavior, in general this function is called every frame in order to update the behavior of the object

## Details

### EVENT_INDEX_CHANGE
###### EVENT_INDEX_CHANGE : string;
[Static] Dispatch when current behavior level index changes EventUtils.happen(this, SceneObjectBehaviors.EVENT_INDEX_CHANGE, [v]);<br>
For example, the current behavior group of this object has 5 behaviors, and this event is dispatched after the execution of the 2nd behavior and before starting the execution of the 3rd behavior <br>
>// Behaviors are instances of the SceneObjectBehaviors subclass<br>
>// newIndex is the new index<br>
>EventUtils.addEventListenerFunction(behavior,SceneObjectBehaviors.EVENT_INDEX_CHANGE,(newIndex:number)=>{<br>
>&nbsp;&nbsp;// Logic<br>
>},this);<br>
>


### ignoreProcess
###### ignoreProcess : boolean;
[For Editor Preview]Whether to ignore the process (means jump directly to the final result without playing the process)<br>
For example, the behavior is moving from point A to point B, and since the process is ignored in edit mode in the behavior editor to display the result directly,<br> 
the behavior can be implemented according to ignoreProcess, i.e.<br> 
When ignoreProcess=true, it moves smoothly from point A to point B with play effect. <br> 
When ignoreProcess=false, it appears directly at point B, ignoring the process.

### logicPause
###### logicPause : boolean;
A pause flag for logic, such as an act not performing the next action until the end of the movement (e.g. with the effect of Game.pause)<br> 
Implementation classes can override this property according to specific game rules to be able to correctly pause the execution of the next act<br> 
For example, an object in motion in an RPG can only wait for the execution to finish before continuing:<br>
>// Overloaded as get method<br>
>protected get logicPause(): boolean {<br>
>&nbsp;&nbsp;&nbsp;return this.so.isMoving ? true : false;<br>
>}<br>
>



## toBehaviorData
###### **[toBehaviorData](#toBehaviorData)**(behaviorStr : string) :
[Static] Data conversion: convert the data in string format to usable format, usually the behavior data in custom properties need to use this method after conversion

##### Return
targetSceneObjectIndex 0-Object -2 Player -1 Current Object 0-N Specify the object number<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;behaviorData Behavioral Data<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;loop Whether circular<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cover Whether to cover the behavior<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;forceStopLastBehavior Whether to forcibly stop the act being performed

## constructor
###### **[constructor](#constructor)**(so : SceneObjectEntity,  loop : boolean,  targetSceneObject : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject),  onOver : Callback,  startIndex? : number,  executor? : SceneObjectEntity) :
Constructors
##### Parameters
	so Scene objects for performing actions
	loop Whether circular
	targetSceneObject Event Triggers
	onOver Callback when the behavior is completed onOver(soBehavior:SceneObjectBehaviors)
	startIndex [Optional] Default=0 Start row index
	executor [optional] default=null event executor (also behavior dispatcher)



## dispose
###### **[dispose](#dispose)**(): void :
Release function, which is called when no longer in use in order to destroy



## setBehaviors
###### **[setBehaviors](#setBehaviors)**(behaviorData : any[],  delayFrame? : number): void :
Set the behavior data and parse it, which will clear all previous behaviors<br>
For example, add act #3
##### Parameters
	behaviorData Behavior data [[Behavior1-ID,Parameter1,Parameter2],[Behavior2-ID,Parameter1,Parameter2],....]
	delayFrame [Optional] Default = 0 Number of frames to wait for within the behavior



## reset
###### **[reset](#reset)**(defSceneObejct : [SceneObject](?file=006-API-2D单机内核/001-通用/024-SceneObject)): void :
[For Editor Preview]Reset: restore to the most initial state<br>
Only used in the behavior editor preview, the project layer needs to implement a reset of the behavior so that the effect is displayed correctly in the preview
##### Parameters
	defSceneObejct Default scene object



## waitFrame
###### **[waitFrame](#waitFrame)**(frame : number): void :
Wait for the specified number of frames and continue execution<br>
If you are already waiting for a frame: when the update behavior is called, a frame is advanced
##### Parameters
	frame Number of frames waited for



## update
###### **[update](#update)**(): boolean :
Update the behavior, you need to actively call this function to execute the behavior, in general this function is called every frame in order to update the behavior of the object<br>
This feature can be used to create effects such as:<br>
-- Logic that does not perform the default behavior after entering the battle and continues to perform the behavior after leaving the battle<br>
-- This function is not executed when the global pause is applied in order to stop the advance behavior

##### Return
[boolean] Whether to end playback



