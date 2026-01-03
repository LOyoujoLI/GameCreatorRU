# UIVideo Video display object
>-- Mobile use is not supported<br>Event:<br>EventObject.LOADED Triggered when metadata has been loaded.<br>EventObject.ERROR Dispatch when errors are encountered<br>EventObject.COMPLETE Distribute when play is complete<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2020-12-24

**Inheritance**  →[UIBitmap](?file=007-API-2D网络内核/002-客户端/003-界面/014-UIBitmap)→[UIBase](?file=007-API-2D网络内核/002-客户端/003-界面/013-UIBase)→[GameSprite](?file=007-API-2D网络内核/002-客户端/029-GameSprite)→[Sprite](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/014-Sprite)→[TreeNode](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/017-TreeNode)→[EventDispatcher](?file=007-API-2D网络内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **duration** : number;<br>Read only] Total video time: seconds Return NaN if it does not exist  |
| **[networkState](#networkState)** : number;<br>[Read Only] Network Status  |
| **videoURL** : string;<br>Video Address  |
| **playbackRate** : number;<br>Playback Rate Default = 1 for 100%  |
| **volume** : number;<br>Volume Default=1  |
| **currentTime** : number;<br>Current video time (seconds) Default = 0  |
| **playType** : number;<br>Playback mode 0-play 1-stop playback 2-pause Default=0  |
| **readonlyisPlaying** : boolean;<br>[Read Only] Whether it is playing  |
| **muted** : boolean;<br>silent  |
| **loop** : boolean;<br>Circulation  |

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
[Read Only] Network Status<br>
0 = NETWORK_EMPTY - Audio/video not yet initialized<br>
1 = NETWORK_IDLE - Audio/video is active and has been selected as a source, but does not use the network<br>
2 = NETWORK_LOADING - The browser is downloading data<br>
3 = NETWORK_NO_SOURCE - No audio/video source found


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





