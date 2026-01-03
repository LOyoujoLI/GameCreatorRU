# TransData Transition Data
>Maintenance personnel:**JayLen**  
>Created on 2020-11-17

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **transType** : number;<br>Transition mode: 0-Uniform transition 1-Jogging transition 2-Curve transition Default=0  |
| **loopType** : number;<br>Loop mode: 0-none (once) 1-loop 2-once round trip-transition from the beginning on return 3-once round trip-transition from the end on return 4-loop round trip-transition from the beginning on return 5-loop round trip-transition from the end on return Default=0  |
| **timeType** : number;<br>Time category: 0-none() 1-Frames 2-Seconds 3-Selectable units Default = 0  |
| **timeUnit** : number;<br>Time unit: 0 - number of frames 1 - number of seconds Default value = 1  |
| **totalTime** : number;<br>Total time (number of frames or seconds) Default value = 2  |
| **tweenType** : number;<br>Jogging mode Default = 0  |
| **tweenTypeName** : string;<br>Jogging method name (e.g. backOut) Default value = "bounceIn"  |
| **curveData** : any[];<br>Curve data Default value=[[0, 0, 99, 1, 1, 3], [0, 100, 100]]  |
| **refreshInterval** : number;<br>Refresh time (default 16, means 16 ms, frame by frame refresh) Default=16  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[isLoop](#isLoop)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean<br>[Static] Whether to loop
| **[isUseFrame](#isUseFrame)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean<br>[Static] Whether to use frames
| **[isUseTime](#isUseTime)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean<br>[Static] Whether to use time

## Details



## isLoop
###### **[isLoop](#isLoop)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean :
[Static] Whether to loop



## isUseFrame
###### **[isUseFrame](#isUseFrame)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean :
[Static] Whether to use frames



## isUseTime
###### **[isUseTime](#isUseTime)**(transData : [TransData](?file=006-API-2D单机内核/001-通用/028-TransData)): boolean :
[Static] Whether to use time





