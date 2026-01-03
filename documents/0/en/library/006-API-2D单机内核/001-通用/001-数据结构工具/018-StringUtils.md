# StringUtils String Tools Class
>GC internal wrapped string processing tool class<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2019-01-02

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[getRealLength](#getRealLength)**(str : string): number<br>[Static] Get the real length of characters, will calculate the Chinese characters
| **[clearHtmlTag](#clearHtmlTag)**(str : string): string<br>[Static] Clear HTML formatting
| **[getMiddleDiff](#getMiddleDiff)**(str1 : string,  str2 : string): [number, number]<br>[Static] Get the information in the middle of two strings that are not the same

## Details



## getRealLength
###### **[getRealLength](#getRealLength)**(str : string): number :
[Static] Get the real length of the character, will calculate the Chinese character
##### Parameters
	str String

##### Return
The real length of the string str

## clearHtmlTag
###### **[clearHtmlTag](#clearHtmlTag)**(str : string): string :
[Static] Clear HTML formatting
##### Parameters
	str Possible strings with HTML format

##### Return
[string] Clear the string after HTML formatting

## getMiddleDiff
###### **[getMiddleDiff](#getMiddleDiff)**(str1 : string,  str2 : string): [number, number] :
[Static] Get the information in the middle of two strings that are not the same
##### Parameters
	str1 String 1
	str2 String 2

##### Return
[The number of characters in the first string is the same, the number of characters in the last string is the same]



