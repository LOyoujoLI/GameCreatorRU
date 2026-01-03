# FileUtils File manipulation tools
>Generally used for text files such as JSON/XML and other storage data formats<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-06-22

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **hasFileOperationJurisdiction** : boolean;<br>[Static] [Read-only] Whether to have file system permissions: such as writing files, getting a list of all files in a directory, etc.  |

## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[exists](#exists)**(localURL : string,  onFin : Callback): void<br>[Static] Whether the file (folder) exists
| **[getDirectoryListing](#getDirectoryListing)**(directoryLocalPath : string,  onFin : Callback): void<br>[Static] [Valid for PC games only] Get all files or folders in the specified directory (not including files in subfolders)
| **[getAllChildFiles](#getAllChildFiles)**(directoryLocalPath : string,  onFin : Callback): void<br>[Static] [Valid only for PC games] Get all files or folders in the specified directory (including files in subfolders)
| **[loadJsonFile](#loadJsonFile)**(localURL : string,  onFin : Callback): void<br>[Static] Loading JSON files
| **[loadFile](#loadFile)**(localURL : string,  onFin : Callback): void<br>[Static] Loading files (text format)
| **[save](#save)**(dataObject : any,  localURL : string,  onFin : Callback,  format? : boolean): void<br>[Static] Save file
| **[deleteFile](#deleteFile)**(localURL : string,  onFin? : Callback): void<br>[Static] Delete files
| **[createDirectoryForce](#createDirectoryForce)**(localURL : string,  onFin : Callback): void<br>[Static] [Valid for PC games only] Creating a folder will create a directory that does not exist
| **[cloneFile](#cloneFile)**(fromLocalURL : string,  toLocalURL : string,  onFin : Callback,  onProgress? : Callback): void<br>[Static] [Valid for PC game only] Copy and paste the file

## Details



## exists
###### **[exists](#exists)**(localURL : string,  onFin : Callback): void :
[Static] Whether the file (folder) exists<br>
-- Need to meet FileUtils.hasFileOperationJurisdiction
##### Parameters
	localURL Relative paths, such as asset/json/xxx.json
	onFin When the inspection is complete onFin(isExists:boolean)



## getDirectoryListing
###### **[getDirectoryListing](#getDirectoryListing)**(directoryLocalPath : string,  onFin : Callback): void :
[Static] [Valid for PC games only] Get all files or folders in the specified directory (not including files in subfolders)<br>
-- Need to meet FileUtils.hasFileOperationJurisdiction
##### Parameters
	directoryLocalPath File directory address e.g. asset/xxx
	onFin Callback on completion onFin(fos:{localPath:string,fileName:string,isDirectory:boolean}[])  For example, if fileName=xxx.png localPath=asset/xxx.png, if fos is empty, it means fetching failed



## getAllChildFiles
###### **[getAllChildFiles](#getAllChildFiles)**(directoryLocalPath : string,  onFin : Callback): void :
[Static] [Valid only for PC games] Get all files or folders in the specified directory (including files in subfolders)<br>
-- Need to meet FileUtils.hasFileOperationJurisdiction
##### Parameters
	directoryLocalPath File directory address e.g. asset/xxx
	onFin Callback on completion onFin(fos:{localPath:string,fileName:string,isDirectory:boolean}[])  For example, if fileName=xxx.png localPath=asset/xxx.png, if fos is empty, it means fetching failed



## loadJsonFile
###### **[loadJsonFile](#loadJsonFile)**(localURL : string,  onFin : Callback): void :
[Static] Loading JSON files
##### Parameters
	localURL Address of the loaded file
	onFin Callback on completion or failure of loading (failure:obj=null) onFin(jsonObj:any)



## loadFile
###### **[loadFile](#loadFile)**(localURL : string,  onFin : Callback): void :
[Static] Loading files (text format)
##### Parameters
	localURL Address of the loaded file
	onFin Callback on load completion or failure (failure:text=null) onFin(text:any)



## save
###### **[save](#save)**(dataObject : any,  localURL : string,  onFin : Callback,  format? : boolean): void :
[Static] Saving files<br> 
-- PC version saves local files<br> 
-- WEB version uses LocalStorage/IndexedDB storage
##### Parameters
	dataObject Object
	localURL Relative address of the file , e.g. asset/xxx.json
	onFin Callback when save is complete
	format [Optional] Default = true Whether to format (JSON formatting)



## deleteFile
###### **[deleteFile](#deleteFile)**(localURL : string,  onFin? : Callback): void :
[Static] Delete files<br> 
-- PC version deletes local files<br> 
-- WEB version cleans up the corresponding LocalStorage/IndexedDB
##### Parameters
	localURL Relative address of the file , e.g. asset/xxx.json
	onFin [Optional] Default=null Whether the deletion was successful onFin(success:boolean, localURL:string)



## createDirectoryForce
###### **[createDirectoryForce](#createDirectoryForce)**(localURL : string,  onFin : Callback): void :
[Static] [Valid for PC games only] Creating a folder will create a directory that does not exist<br>
-- Need to meet FileUtils.hasFileOperationJurisdiction
##### Parameters
	localURL Folder relative addresses Format: e.g. asset/dir1/dir2/dir3
	onFin When finished is the callback onFin(success:boolean,localURL:string)



## cloneFile
###### **[cloneFile](#cloneFile)**(fromLocalURL : string,  toLocalURL : string,  onFin : Callback,  onProgress? : Callback): void :
[Static] [Valid for PC game only] Copy and paste the file<br>
-- Need to meet FileUtils.hasFileOperationJurisdiction
##### Parameters
	fromLocalURL Relative address of the file source Format: e.g. asset/file1.txt
	toLocalURL Relative address to paste to Format: e.g. asset/file2.txt
	onFin Callback on completion  onFin(success:boolean,fromLocalURL:string,toLocalURL:string)
	onProgress [Optional] Default=null Copy procedure function onProgress(currentNum:number,totalNum:number);





