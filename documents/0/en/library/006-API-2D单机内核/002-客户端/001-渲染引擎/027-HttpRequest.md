# HttpRequest Request
>Provides full access to the HTTP protocol by wrapping the HTML XMLHttpRequest object, including the ability to make POST and HEAD requests as well as normal GET requests.<br>Only provides the response back to the web server in an asynchronous form and can return the content in text or binary form.<br>Note: It is recommended to use a new HttpRequest object for each request, because each time the send method of this object is called, the previously set data is cleared and the state of the HTTP request is reset.<br>This causes requests that have not yet returned a response to be reset, so that the response to the previous request is not available.<br>Support Events<br>EventObject.COMPLETE Load Completion Event onComplete(content:any)<br>EventObject.PROGRESS Load process events (generally available only for large files) onProgress(progress:number)<br>EventObject.ERROR Loading error events<br>// Code example:<br>var ur = new HttpRequest();<br>ur.send("http://www.gamecreator.com.cn");<br>ur.on(EventObject.COMPLETE, this, (content:string) => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>});<br>ur.on(EventObject.PROGRESS, this, (progress:number) => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Progress 0~1<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;trace("进度=",progress)<br>});<br>ur.on(EventObject.ERROR, this, (error:string) => {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// to do<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;trace(error);<br>});<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  →[EventDispatcher](?file=006-API-2D单机内核/002-客户端/001-渲染引擎/019-EventDispatcher)<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **url** : string;<br>[Read-only] The address of the request.  |
| **data** : any;<br>[Read-only] The returned data.  |
| **http** : XMLHttpRequest;<br>[Read-only] The native XMLHttpRequest reference encapsulated by this object.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[send](#send)**(url : string,  data? : any,  method? : string,  responseType? : string,  headers? : Array<any>): void<br>Sends an HTTP request.

## Details



## send
###### **[send](#send)**(url : string,  data? : any,  method? : string,  responseType? : string,  headers? : Array<any>): void :
Sends an HTTP request.<br>
@param	url				The address of the request. Most browsers implement a same-origin security policy and require that the URL has the same hostname and port as the text containing the script.<br>
@param	data			The data sent by (default = null). For example "{ mode: 6, act: 5 }" or "act=5&mode=6"<br>
@param	method			(default = "get") The HTTP method used for the request. Values include "get", "post", and "head".<br>
@param	responseType	(default = "text") The response type of the web server, which can be set to "text", "json", "xml", "arraybuffer".<br>
@param	headers			(default = null) The header information of the HTTP request. The parameters are shaped like a key-value array: key is the name of the header and should not include whitespace, colons or newlines; value is the value of the header and should not include newlines. For example ["Content-Type", "application/json"].





