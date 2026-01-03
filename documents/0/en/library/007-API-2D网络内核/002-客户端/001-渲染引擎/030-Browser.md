# Browser Browser Status
>is a browser proxy class. It encapsulates some of the functionality provided by the browser and native js.<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **userAgent** : string;<br>[Static] Browser Information  |
| **onIOS** : boolean;<br>[Static] Whether in ios device  |
| **onMobile** : boolean;<br>[Static] Whether in mobile devices  |
| **onIPhone** : boolean;<br>[Static] Whether in iphone device  |
| **onIPad** : boolean;<br>[Static] Whether in ipad device  |
| **onAndriod** : boolean;<br>[Static] Whether in andriod device  |
| **onAndroid** : boolean;<br>[Static] Whether in andriod device  |
| **onWP** : boolean;<br>[Static] Whether in Windows Phone devices  |
| **onQQBrowser** : boolean;<br>[Static] Whether in QQ browser  |
| **onMQQBrowser** : boolean;<br>[Static] Whether in mobile QQ or QQ browser  |
| **onSafari** : boolean;<br>[Static] Whether in Mobile Safari  |
| **onIE** : boolean;<br>[Static] Whether in IE browser  |
| **onWeiXin** : boolean;<br>[Static] Inside WeChat  |
| **onPC** : boolean;<br>[Static] Whether on the PC side  |
| **onMac** : boolean;<br>[Static] Whether on the PC side  |
| **httpProtocol** : boolean;<br>[Static] means whether it is HTTP protocol or not  |
| **webAudioEnabled** : boolean;<br>[Static] Audio enabled or not  |
| **soundType** : string;<br>[Static] Audio Playback Category  |
| **enableTouch** : boolean;<br>[Static] Whether to turn on touch  |
| **[clientWidth](#clientWidth)** : number;<br>[Static] [Read-only] The visible width of the browser window.  |
| **[clientHeight](#clientHeight)** : number;<br>[Static] [Read-only] The visible height of the browser window.  |
| **width** : number;<br>[Static] [Read-only] The physical width of the browser window. The device pixel ratio is considered.  |
| **height** : number;<br>[Static] [Read-only] The physical height of the browser window. The device pixel ratio is considered.  |
| **pixelRatio** : number;<br>[Static] [Read-only] Device pixel ratio.  |
| **container** : any;<br>[Static] Canvas container, a container used to hold the canvas. Convenient for canvas control  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[now](#now)**(): number<br>[Static] Get the current timestamp of the browser in milliseconds.

## Details

### clientWidth
###### clientWidth : number;
[Static] [Read-only] The visible width of the browser window.<br>
Obtained by analyzing browser information. The priority of multiple browser property values is: window.innerWidth(contains scrollbar width) > document.body.clientWidth(does not contain scrollbar width), if the former is 0 or empty, the latter is selected.
### clientHeight
###### clientHeight : number;
[Static] [Read-only] The visible height of the browser window.<br>
Obtained by analyzing browser information. The priority of multiple browser property values is: window.innerHeight(contains scrollbar height) > document.body.clientHeight(does not contain scrollbar height) > document.documentElement.clientHeight(does not contain scrollbar height), if the former is 0 or empty, the latter is selected.


## now
###### **[now](#now)**(): number :
[Static] Get the current timestamp of the browser in milliseconds.





