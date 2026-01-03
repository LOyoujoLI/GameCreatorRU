## Start
### Create Interface

Just create and add **Image Component** and replace the corresponding material.

![](img/In-depth/018/001.png=600-)

### Find the place to execute the command

Usually the loading page appears when the game is opened, so we find **Common Event** -> **System Events** -> **14001-Start the Game**, where we can execute the **Show Interface** command.

Note: To facilitate the subsequent creation of transition effects, I set the property **Opacity 0** in the **Show Interface** command.

![](img/In-depth/018/003.png)

![](img/In-depth/018/002.png=600-)

## Add fade in effect

### Use the Move Interface command to add a fade-in

We can quickly achieve this effect by using the **Move Interface** command.

Note 1: Since I set the Opacity to 0 when I executed the **Show Interface** command, we need to set the Opacity 1.

Note 2: The **Move Interface** command has a property called **Frames**, which is the time we need to achieve the transition effect.

![](img/In-depth/018/004.png)


### Adding a wait to the transition effect

After inserting the **Move Interface** Command, we need to insert the **Wait** Command again to make sure that the set animation effect can be executed completely.

Otherwise, the following Command will be executed before the transition effect is finished.

Note: Generally, the wait time of the **Wait** Command can be the same as the **Frames** property.

![](img/In-depth/018/005.png=600-)

### Test

This way we achieve a fade in effect, next we do the fade out effect.

![](img/In-depth/018/006.gif=600-)

## Add fade out effect

### Use the Move Interface command to add a fade out

The logic is the same as fading in, the difference is that because we are fading out we just need to set the **Opacity 0**.

![](img/In-depth/018/007.png)

### Adding a wait to the transition effect

As with the fade-in, a wait Command needs to be added for us to ensure that the entire transition can be executed properly.

![](img/In-depth/018/008.png=600-)

### Test

In the test we found that the overall fade out and fade in effect is too fast, so next we have to adjust the details.

![](img/In-depth/018/009.gif=600-)

## Adjustment details

The fade in and fade out is too fast, generally speaking the loading page fades in and out slowly after a while, so we need to modify the frame rate of the move interface command and the wait command.

I have written a comment in the picture (in green) to help you understand why I did it.

![](img/In-depth/018/010.png=600-)

## Close the interface

When we finish executing an interface-related command, please make sure if the current interface is no longer needed, and remember to execute the **Close Interface** command if it is not needed.

Otherwise the interface is actually always there even though the Opacity is set to 0.

![](img/In-depth/018/011.png=600-)

## Test

![](img/In-depth/018/012.gif=600-)
