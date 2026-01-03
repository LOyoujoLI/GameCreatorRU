# GameDialog Game Dialog
>Characteristics:<br>-- Currently, once the dialog style is loaded, it is not released but remains cached<br>-- Conversations and options are implemented with this<br>-- Plug-ins for dialog boxes can be written by listening to events, etc., such as making fast-forward, skip, and history dialogs for AVG games<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-01-09

**Inheritance**  →Sprite<br>
**Subcategories**  N/A<br>
## **Public Method**
|<div style="width:1000px;text-align:left">Method</div>   |
| ---  |
| **[EVENT_DIALOG_START](#EVENT_DIALOG_START)** : string;<br>[Static] event: when the dialog box appears before Callback parameters: whether option, text content, option content (if it is an option), name, headshot path  |
| **[EVENT_AFTER_DIALOG_START](#EVENT_AFTER_DIALOG_START)** : string;<br>[Static] Event：When the dialog box appears  |
| **[EVENT_DIALOG_END](#EVENT_DIALOG_END)** : string;<br>[Static] Event: When the dialogue text playback ends  |
| **[EVENT_DIALOG_CLOSE](#EVENT_DIALOG_CLOSE)** : string;<br>[Static] Event: When the dialog box is closed  |
| **[EVENT_DIALOG_WORD_PLAY](#EVENT_DIALOG_WORD_PLAY)** : string;<br>[Static] event: when the text box text is played Callback parameter: current text  |
| **[EVENT_DIALOG_WORD_PLAY_COMPLETE](#EVENT_DIALOG_WORD_PLAY_COMPLETE)** : string;<br>[Static] event: isAuto indicates whether it comes from auto play when text playback is completed  |
| **[EVENT_TS_PLAY_COMPLETE](#EVENT_TS_PLAY_COMPLETE)** : string;<br>[Static] event: dispatched when the voice is finished playing (if the voice of the conversation is not finished, the event will not be thrown if the player manually skips the conversation)  |
| **[EVENT_DIALOG_TEXT_WAIT_TIME](#EVENT_DIALOG_TEXT_WAIT_TIME)** : string;<br>[Static] Event: Thrown when the text is played and the waiting time (frame count) is encountered frameCount=the number of frames waiting  |
| **[EVENT_WAIT_PALYER_OPERATION](#EVENT_WAIT_PALYER_OPERATION)** : string;<br>[Static] event: When the text is played, the event is thrown when the player is waiting for the operation and after the player has finished the operation state=0 means waiting for the player's operation state=1 means the player has finished the operation  |
| **dialogTextShowAllEnabled** : boolean;<br>[Static] Allow user manipulation to quickly display the current text (spacebar/left mouse button click) default=false  |
| **fromCommandID** : string;<br>[Static] Unique identification of the current text corresponding to the command  |
| **isInDialog** : boolean;<br>[Static] [Read-only] Whether to show the dialogue in  |
| **isPlaying** : boolean;<br>[Static] [Read-only] Whether playing  |
| **lastDialog** : GameDialog;<br>[Static] Recently Used Dialogs  |
| **optionList** : UIList;<br>[Read-only] option list  |
| **optionUIs** : UIButton[];<br>Read-only] Get the current option button (requires that the option exists and is being displayed)  |
| **optionTexts** : UIString[];<br>[Read Only] Option Text  |
| **dialogHeadBox** : UIBitmap | UIStandAvatar | UIAnimation | UIRoot;<br>[Read Only] Headshot  |
| **dialogBox** : UIBitmap;<br>[Read-only] Dialog Background Image  |
| **nameText** : UIString;<br>[Read Only] Name Text  |
| **playTextLabels** : UIString[];<br>[Read-only] text text group: multiple paragraphs of text cut according to different colors, line breaks, etc. (split word by word if you have material) Default = []  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[showall](#showall)**(): void<br>[Static] function: immediately display the full text, when in the text playback will be immediately displayed to the full text
| **[skip](#skip)**(): boolean<br>[Static] function: skip the current text immediately
| **[skipWaitPlayerOperation](#skipWaitPlayerOperation)**(): boolean<br>[Static] Function: Skip "Waiting for player action" immediately
| **[stop](#stop)**(): void<br>[Static] Stop the conversation, the trigger line it is in is also in stop after stopping

## Details

### EVENT_DIALOG_START
###### EVENT_DIALOG_START : string;
[Static] event: when the dialog box appears before Callback parameters: whether option, text content, option content (if it is an option), name, headshot path<br>
>// isOption = Whether option<br>
>// content = Text Content<br>
>// options = Option content (if option)<br>
>// name = name<br>
>// head = headshot image path String/Standing avatar ID:number/Animation ID:number<br>
>// expression = Expression ID (if available, expressions can be selected in standing avatar mode)<br>
>// audioURL = Voice string (if any) Format: Audio address,Volume 0-1,Tone 0-2<br>
>// speed = Text Playback Speed 0-5 Very Slow - Show Now<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_START,(isOption:boolean,content:string,options:string[],name:string,head:string|number,expression:number,audioURL:string)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_AFTER_DIALOG_START
###### EVENT_AFTER_DIALOG_START : string;
[Static] Event：When the dialog box appears<br>
onAfterDialogStart(isOption:boolean);
### EVENT_DIALOG_END
###### EVENT_DIALOG_END : string;
[Static] Event: When the dialogue text playback ends<br>
>// gameDialog = Current dialog display object fromAutoPlaySkipSign:boolean = Does it come from [skip this conversation] that appears when text is played<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_END,(gameDialog:GameDialog,fromAutoPlaySkipSign:boolean)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_DIALOG_CLOSE
###### EVENT_DIALOG_CLOSE : string;
[Static] Event: When the dialog box is closed<br>
>// gameDialog = Current dialog display object<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_CLOSE,(gameDialog:GameDialog)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_DIALOG_WORD_PLAY
###### EVENT_DIALOG_WORD_PLAY : string;
[Static] event: when the text box text is played Callback parameter: current text<br>
>// word = Current text<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_WORD_PLAY,(word:string)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_DIALOG_WORD_PLAY_COMPLETE
###### EVENT_DIALOG_WORD_PLAY_COMPLETE : string;
[Static] event: isAuto indicates whether it comes from auto play when text playback is completed<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_WORD_PLAY_COMPLETE,(isAuto:boolean)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_TS_PLAY_COMPLETE
###### EVENT_TS_PLAY_COMPLETE : string;
[Static] event: dispatched when the voice is finished playing (if the voice of the conversation is not finished, the event will not be thrown if the player manually skips the conversation)<br>
>// audioURL = Voice string (if any) Format: Audio address,Volume 0-1,Tone 0-2<br>
>EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_TS_PLAY_COMPLETE,(success:boolean,audioURL:string)=> {<br>
>&nbsp;&nbsp;// to do<br>
>},this);<br>
>


### EVENT_DIALOG_TEXT_WAIT_TIME
###### EVENT_DIALOG_TEXT_WAIT_TIME : string;
[Static] Event: Thrown when the text is played and the waiting time (frame count) is encountered frameCount=the number of frames waiting<br>
EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_DIALOG_TEXT_WAIT_TIME,(frameCount:number)=> {<br>
&nbsp;&nbsp;// to do<br>
},this);
### EVENT_WAIT_PALYER_OPERATION
###### EVENT_WAIT_PALYER_OPERATION : string;
[Static] event: When the text is played, the event is thrown when the player is waiting for the operation and after the player has finished the operation state=0 means waiting for the player's operation state=1 means the player has finished the operation<br>
EventUtils.addEventListenerFunction(GameDialog,GameDialog.EVENT_WAIT_PALYER_OPERATION,(state:number)=> {<br>
&nbsp;&nbsp;// to do<br>
},this);


## showall
###### **[showall](#showall)**(): void :
[Static] function: immediately display the full text, when in the text playback will be immediately displayed to the full text



## skip
###### **[skip](#skip)**(): boolean :
[Static] function: skip the current text immediately

##### Return
[boolean] Successfully skipped

## skipWaitPlayerOperation
###### **[skipWaitPlayerOperation](#skipWaitPlayerOperation)**(): boolean :
[Static] Function: Skip "Waiting for player action" immediately<br>
This function allows you to skip the wait when listening to the EVENT_WAIT_PALYER_OPERATION event

##### Return
[boolean] Successfully skipped

## stop
###### **[stop](#stop)**(): void :
[Static] Stop the conversation, the trigger line it is in is also in stop after stopping





