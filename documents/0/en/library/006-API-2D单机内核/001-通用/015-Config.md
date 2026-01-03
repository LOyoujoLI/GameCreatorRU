# Config General configuration
>General configuration of the game, used to get some preset configuration information in the editor<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2018-05-22

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>
## **Public Properties**
|<div style="width:1000px;text-align:left">Properties</div>   |
| ---  |
| **gameSID** : number;<br>[Static] Unique SID of the game project will be generated when creating the project  |
| **[USE_FN](#USE_FN)** : boolean;<br>[Static] Use F1-F12 function keys, turn off this function and also disable the function of this key in the browser environment Default = true  |
| **[EDIT_MODE](#EDIT_MODE)** : boolean;<br>Whether [Static] [Read-only] is in editor mode  |
| **[BEHAVIOR_EDIT_MODE](#BEHAVIOR_EDIT_MODE)** : boolean;<br>[Static] [Read-only] Whether in object behavior editor mode  |
| **RELEASE_GAME** : boolean;<br>[static] [read-only] version of the game after release, used to distinguish whether the official version of the game  |
| **CREATED_GC_VERSION** : number;<br>[Static] [Read-only] GC version number at the time of project creation  |
| **WINDOW_WIDTH** : number;<br>[Static] [Read-only] Default resolution width: The current version is automatically scaled isometrically according to the window size  |
| **WINDOW_HEIGHT** : number;<br>[Static] [Read-only] Default resolution height: The current version is automatically scaled isometrically according to the window size  |
| **SCENE_GRID_SIZE** : number;<br>[Static] [Read-only] Scene grid size, such as 32 pixels or 48 pixels  |
| **ANIMATION_FPS** : number;<br>[Static] [Read-only] Default frame rate of animation: the default frame rate of the newly created animation when no frame rate is set  |
| **[DEFAULT_FONT](#DEFAULT_FONT)** : string;<br>[Static] [Read-only] default font, newly created text will use this default font  |



## Details

### USE_FN
###### USE_FN : boolean;
[Static] Use F1-F12 function keys, turn off this function and also disable the function of this key in the browser environment Default = true<br>
-- F5: Reset the game<br>
-- F11: Full-screening
### EDIT_MODE
###### EDIT_MODE : boolean;
Whether [Static] [Read-only] is in editor mode<br>
The editor also comes with a runtime for real-time preview and reuse of code, so this determination is used in some cases
### BEHAVIOR_EDIT_MODE
###### BEHAVIOR_EDIT_MODE : boolean;
[Static] [Read-only] Whether in object behavior editor mode<br>
The behavior editor runs the user-written code in order to preview the actual effect, so this property can be used to distinguish the running environment.<br>
to allow compatibility issues to be resolved in the game or behavior editor
### DEFAULT_FONT
###### DEFAULT_FONT : string;
[Static] [Read-only] default font, newly created text will use this default font<br>
GC supports the coexistence of different fonts under the same game, which will not affect the fonts that have been set separately for each text in the editor.




