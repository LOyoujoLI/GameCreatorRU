# UIVideo Video display object
>-- Not supported for mobile use<br>Events:<br>EventObject.LOADED Triggered when metadata has been loaded. <br>EventObject.ERROR Dispatched when an error is encountered<br>EventObject.COMPLETE Dispatched when playback is complete<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-12-24

**Inheritance**  →[UIBitmap](?file=006-API-2D单机内核/002-客户端/003-界面/014-UIBitmap)→[UIBase](?file=006-API-2D单机内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=006-API-2D单机内核/002-客户端/027-GameSprite)→[Sprite](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **duration** : number;<br>Read only] Total video time: seconds Return NaN if it does not exist  |
| **[networkState](#networkState)** : number;<br>[Read Only] Network Status  |
| **videoURL** : string;<br>Video Address  |
| **playbackRate** : number;<br>Playback Rate Default = 1 for 100%  |
| **volume** : number;<br>Volume Default =  |
| **currentTime** : number;<br>Current video time (seconds) Default value = 0  |
| **playType** : number;<br>Playback mode 0-play 1-stop playback 2-pause Default=0 |
| **readonlyisPlaying** : boolean;<br>[Read Only] Whether it is playing  |
| **muted** : boolean;<br>silent  |
| **loop** : boolean;<br>Circulation  |
| **[onLoadedFragEvent](#onLoadedFragEvent)** : string;<br>Clip event content: When the video source is loaded  |
| **[onErrorFragEvent](#onErrorFragEvent)** : string;<br>Fragment event content: Handling when an error occurs  |
| **[onCompleteFragEvent](#onCompleteFragEvent)** : string;<br>Clip event content: Handled when playback is complete  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[constructor](#constructor)**(editorCompMode? : boolean)<br>Constructors
| **[play](#play)**(): void<br>Playback
| **[stop](#stop)**(): void<br>Stop Play
| **[pause](#pause)**(): void<br>Pause Play

## Details

### networkState
###### networkState : number;
Read-only] Network Status<br> 
0 = NETWORK_EMPTY - Audio/video has not been initialized<br> 
1 = NETWORK_IDLE - Audio/video is active and the source is selected but not using the network<br> 
2 = NETWORK_LOADING - The browser is downloading data<br> 
3 = NETWORK_NO_SOURCE SOURCE - No audio/video source found
### onLoadedFragEvent
###### onLoadedFragEvent : string;
Fragment event content: When the video source is loaded<br> 
Active call method: CommandPage.startTriggerFragmentEvent
### onErrorFragEvent
###### onErrorFragEvent : string;
Fragment event content: Handle when an error occurs<br> Active call method: CommandPage.startTriggerFragmentEvent
### onCompleteFragEvent
###### onCompleteFragEvent : string;
Fragment event content: Handle when playback is complete<br> Active call method: CommandPage.startTriggerFragmentEvent

## constructor
###### **[constructor](#constructor)**(editorCompMode? : boolean) :
Constructors
##### Parameters
	editorCompMode [Optional] Default = true Show specialized component styles in editor mode instead of the actual video



## play
###### **[play](#play)**(): void :
Playback



## stop
###### **[stop](#stop)**(): void :
Stop Play



## pause
###### **[pause](#pause)**(): void :
Pause Play




