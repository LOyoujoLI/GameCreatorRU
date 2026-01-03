# GameAudio Audio
>Smooth transition volume support<br>Tone support (playback rate)<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-07-27

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **bgmVolume** : number;<br>[Static] Global background music volume size 0~1 Default=1  |
| **bgsVolume** : number;<br>[Static] Global Ambient Sound Volume Level 0~1 Default=1  |
| **seVolume** : number;<br>[Static] Global sound volume size 0~1 Default=1  |
| **tsVolume** : number;<br>[Static] Global Voice Volume Level 0~1 Default=1  |
| **lastBgmURL** : string;<br>[Static] Record the address of the last played background music  |
| **lastBgmSoundChannel** : SoundChannel;<br>[Static] Record the last played background music sound channel object  |
| **lastBGMPitch** : number;<br>[Static] Record the last played background music tones  |
| **lastBGMVolume** : number;<br>[Static] Record the sound level of the last played background music  |
| **lastBgsURL** : string;<br>[Static] Record the last played scene sound address  |
| **lastBGSPitch** : number;<br>[Static] Record the last played scene sound tones  |
| **lastBGSVolume** : number;<br>[Static] Record the sound size of the last played scene sound effects  |
| **lastBgsSoundChannel** : SoundChannel;<br>[Static] Record the last played scene sound sound channel object  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[playBGM](#playBGM)**(url : string,  volume? : number,  loop? : number,  isGradient? : boolean,  gradientTime? : number,  pitch? : number): SoundChannel<br>[Static] Play background music: Address is not equal before replaying, but the volume will change (if you need to replay, you can stop the BGM and then play)
| **[stopBGM](#stopBGM)**(isGradient? : boolean,  gradientTime? : number): void<br>[Static] Stop playing background music
| **[playBGS](#playBGS)**(url : string,  volume? : number,  loop? : number,  isGradient? : boolean,  gradientTime? : number,  pitch? : number): SoundChannel<br>[Static] Play ambient sound : Address is not equal before replaying, but the volume will change (if you need to replay, you can stop the BGM and then play)
| **[stopBGS](#stopBGS)**(isGradient? : boolean,  gradientTime? : number): void<br>[Static] Stop playing ambient sound effects
| **[playSE](#playSE)**(url : string,  volume? : number,  pitch? : number,  soc? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): SoundChannel<br>[Static] Play sound effects, play on the scene object is based on the current scene of the camera and the distance to the target to change the sound size
| **[stopSE](#stopSE)**(channels? : any): void<br>[Static] Stop SE
| **[playTS](#playTS)**(url : string,  volume? : number,  pitch? : number,  soc? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): SoundChannel<br>[Static] Play the voice, when playing on the scene object, then change the sound size according to the distance between the camera and the target of the current scene
| **[stopTS](#stopTS)**(channels? : any): void<br>【Static】Stop voice
| **[setBlurStopMusic](#setBlurStopMusic)**(isStop : boolean): void<br>[Static] Set whether to stop music when focus is lost

## Details



## playBGM
###### **[playBGM](#playBGM)**(url : string,  volume? : number,  loop? : number,  isGradient? : boolean,  gradientTime? : number,  pitch? : number): SoundChannel :
[Static] Play background music: Address is not equal before replaying, but the volume will change (if you need to replay, you can stop the BGM and then play)<br>
Only one background music can be played at the same time globally, if you need to overlay the audio, please use playSE<br>
The same address but with a different pitch will also replay
##### Parameters
	url Background music address
	volume Sound volume size 0~1
	loop [Optional] Number of cycles Default = 9999
	isGradient [Optional] Whether to fade in or not Default=false
	gradientTime [Optional] Fade in time (milliseconds) Default = 1000
	pitch [Optional] Playback Rate (Pitch) Default = 1 Range 0-2



## stopBGM
###### **[stopBGM](#stopBGM)**(isGradient? : boolean,  gradientTime? : number): void :
[Static] Stop playing background music
##### Parameters
	isGradient [Optional] Default=false Whether to fade out
	gradientTime [Optional] Default = 1000 Fade out time (milliseconds)



## playBGS
###### **[playBGS](#playBGS)**(url : string,  volume? : number,  loop? : number,  isGradient? : boolean,  gradientTime? : number,  pitch? : number): SoundChannel :
[Static] Play ambient sound : Address is not equal before replaying, but the volume will change (if you need to replay, you can stop the BGM and then play)<br>
Only one ambient sound can be played at the same time globally, if you need to overlay the audio, please use playSE<br>
The same address but with a different pitch will also replay
##### Parameters
	url Ambient sound address
	volume Sound volume size 0~1
	loop [Optional] Number of cycles Default = 9999
	isGradient [Optional] Whether to fade in or not Default=false
	gradientTime [Optional] Fade in time (milliseconds) Default = 1000
	pitch [Optional] Playback Rate Default = 1 Range 0-2



## stopBGS
###### **[stopBGS](#stopBGS)**(isGradient? : boolean,  gradientTime? : number): void :
[Static] Stop playing ambient sound effects
##### Parameters
	isGradient [Optional] Default=false Whether to fade out
	gradientTime [Optional] Default = 1000 Fade out time (milliseconds)



## playSE
###### **[playSE](#playSE)**(url : string,  volume? : number,  pitch? : number,  soc? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): SoundChannel :
[Static] Play sound effects, play on the scene object is based on the current scene of the camera and the distance to the target to change the sound size
##### Parameters
	url Audio Address
	volume [Optional] Default value=1 Volume 0~1
	pitch [Optional] Playback Rate Default = 1 Range 0-2
	soc [optional] default=null Audio binding on scene object



## stopSE
###### **[stopSE](#stopSE)**(channels? : any): void :
[Static] Stop SE
##### Parameters
	channels [Optional] If you pass in, only the sound of the incoming group is stopped, otherwise it is all the current sound SoundChannel | SoundChannel[]



## playTS
###### **[playTS](#playTS)**(url : string,  volume? : number,  pitch? : number,  soc? : [ClientSceneObject](?file=007-API-2D网络内核/002-客户端/019-ClientSceneObject)): SoundChannel :
[Static] Play the voice, when playing on the scene object, then change the sound size according to the distance between the camera and the target of the current scene
##### Parameters
	url Voice Sound Address
	volume [Optional] Default value=1 Volume 0~1
	pitch [Optional] Playback Rate Default = 1 Range 0-2
	soc [optional] default=null Audio binding on scene object



## stopTS
###### **[stopTS](#stopTS)**(channels? : any): void :
【Static】Stop voice
##### Parameters
	channels [optional] default=null if passed in means that only the sound of the incoming group is stopped, otherwise it is all the current sound SoundChannel | SoundChannel[]



## setBlurStopMusic
###### **[setBlurStopMusic](#setBlurStopMusic)**(isStop : boolean): void :
[Static] Set whether to stop music when focus is lost
##### Parameters
	isStop Whether to stop





