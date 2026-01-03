# SoundChannel sound track
>Used to control the sounds in the program. Each sound is assigned to a channel that<br>And applications can have multiple channels mixed together.<br>Contains methods for controlling the play, pause, stop, and volume of sound<br>and a method to obtain information about the sound's playing status, total time, current playing time, total number of cycles, playing address, etc.<br>Support events:EventObject.COMPLETE<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **url** : string;<br>Sound address.  |
| **loops** : number;<br>Number of cycles.  |
| **startTime** : number;<br>Start time.  |
| **isStopped** : boolean;<br>Indicates whether the sound has been paused.  |
| **volume** : number;<br>The volume range is from 0 (mute) to 1 (maximum volume).  |
| **position** : number;<br>[Read-only] Get the current playback time.  |
| **duration** : number;<br>[Read-only] Get the total time.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[play](#play)**(): void<br>Playback.
| **[stop](#stop)**(): void<br>Stop.
| **[pause](#pause)**(): void<br>Suspension.
| **[resume](#resume)**(): void<br>Continue playing.

## Details



## play
###### **[play](#play)**(): void :
Playback.



## stop
###### **[stop](#stop)**(): void :
Stop.



## pause
###### **[pause](#pause)**(): void :
Suspension.



## resume
###### **[resume](#resume)**(): void :
Continue playing.





