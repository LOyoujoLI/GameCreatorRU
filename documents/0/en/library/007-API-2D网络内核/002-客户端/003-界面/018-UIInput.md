# UIInput Enterable text components
>Enterable text is a component that allows the user to enter text<br>Related events:<br>EventObject.ENTER When the ENTER key is pressed<br>EventObject.INPUT When entering text<br>EventObject.CHANGE When the text changes<br>EventObject.FOCUS When generating focus<br>EventObject.BLUR When you lose focus<br>Usage:<br>var a = new UIInput();<br>a.color = "#FF0000"<br>a.text = "Please enter"<br>stage.addChild(a);<br>// Event Listening Example<br>a.on(EventObject.ENTER,this,this.onInput);<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-04-14

**Inheritance**  →UIString<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **inputMode** : number;<br>Text input mode 0-Text mode 1-Password mode 2-Numeric mode 3-Multi-line text Default=0  |
| **restrict** : string;<br>Restrict input to strings such as 0-9A-Za-z which means only numbers and letters can be entered (regular expressions)  |
| **focus** : boolean;<br>For creating focus or losing focus  |
| **maxChars** : number;<br>Maximum number of characters that can be entered  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[select](#select)**(): void<br>Select all text
| **[setSelection](#setSelection)**(startIndex : number,  endIndex : number): void<br>Selects the text in the specified index interval

## Details



## select
###### **[select](#select)**(): void :
Select all text



## setSelection
###### **[setSelection](#setSelection)**(startIndex : number,  endIndex : number): void :
Selects the text in the specified index interval
##### Parameters
	startIndex Start Index
	endIndex End Index





