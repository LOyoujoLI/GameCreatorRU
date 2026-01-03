# Ease Retardation function
>Defined the jogging function in order to achieve the jogging effect in [Tween], the code related to using the Tween method can be referred to Tween<br>== Related Codes ==<br>// Get the state value at 50% of 100~1000 in the linear transition<br>var totalTime = 1000;<br>var currentTime = 500; // i.e., it has proceeded to 50%, and the value can also be greater than totalTime, i.e., more than 100%<br>var start = 100;<br>var end = 1000;<br>var v = Ease.linearNone(currentTime,start,end-start,totalTime);<br>alert(v); // 550，即（1000-100）*(500/1000) + 100 = 550<br><br>
>Maintenance personnel:**黑暗之神KDS**  
>Created on 2017-01-01

**Inheritance**  N/A<br>
**Subcategories**  N/A<br>


## Public Method
|<div style="width:1000px;text-align:left" >Method</div>   |
| ---  |
| **[linearNone](#linearNone)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Definition of continuous motion without acceleration.
| **[linearIn](#linearIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Definition of continuous motion without acceleration.
| **[linearInOut](#linearInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Definition of continuous motion without acceleration.
| **[linearOut](#linearOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Definition of continuous motion without acceleration.
| **[bounceIn](#bounceIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[bounceInOut](#bounceInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[bounceOut](#bounceOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[backIn](#backIn)**(t : number,  b : number,  c : number,  d : number,  s? : number): number<br>[Static] Move backward at the beginning, then reverse towards the target.
| **[backInOut](#backInOut)**(t : number,  b : number,  c : number,  d : number,  s? : number): number<br>[Static] Start the movement by tracking backward, then reverse the direction and move toward the target, slightly overshoot the target, then reverse the direction again and come back to move toward the target.
| **[backOut](#backOut)**(t : number,  b : number,  c : number,  d : number,  s? : number): number<br>[Static] Start the movement is moving toward the target, slightly overshoot, and then reverse the direction back toward the target.
| **[elasticIn](#elasticIn)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[elasticInOut](#elasticInOut)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[elasticOut](#elasticOut)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[strongIn](#strongIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at zero rate, and then speed up the motion during execution.
| **[strongInOut](#strongInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[strongOut](#strongOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[sineInOut](#sineInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[sineIn](#sineIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at zero rate, and then speed up the motion during execution.
| **[sineOut](#sineOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[quintIn](#quintIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at zero rate, and then speed up the motion during execution.
| **[quintInOut](#quintInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[quintOut](#quintOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[quartIn](#quartIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[quartInOut](#quartInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[quartOut](#quartOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[cubicIn](#cubicIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[cubicInOut](#cubicInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[cubicOut](#cubicOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[quadIn](#quadIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[quadInOut](#quadInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[quadOut](#quadOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[expoIn](#expoIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[expoInOut](#expoInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[expoOut](#expoOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.
| **[circIn](#circIn)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] method starts the motion at zero rate, and then speeds up the motion during execution.
| **[circInOut](#circInOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.
| **[circOut](#circOut)**(t : number,  b : number,  c : number,  d : number): number<br>[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.

## Details



## linearNone
###### **[linearNone](#linearNone)**(t : number,  b : number,  c : number,  d : number): number :
[static] Define no-acceleration continuous motion. <br> 
@param t Specifies the current time, between 0 and the duration (both inclusive). <br> 
@param b Specifies the initial value of the animation property. <br> 
@param c Specifies the total number of changes to the animation property. <br> 
@param d Specifies the duration of the motion.

##### Return
The value of the interpolation property for the specified time.

## linearIn
###### **[linearIn](#linearIn)**(t : number,  b : number,  c : number,  d : number): number :
[static] Define no-acceleration continuous motion. <br>
 @param t Specifies the current time, between 0 and the duration (both inclusive). <br> 
 @param b Specifies the initial value of the animation property. <br> 
 @param c Specifies the total number of changes to the animation property. <br> 
 @param d Specifies the duration of the motion.

##### Return
The value of the interpolation property for the specified time.

## linearInOut
###### **[linearInOut](#linearInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Definition of continuous motion without acceleration.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## linearOut
###### **[linearOut](#linearOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Definition of continuous motion without acceleration.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## bounceIn
###### **[bounceIn](#bounceIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
Its motion is similar to a ball falling to the floor and then bouncing back up, after several gradually decreasing rebound motion.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## bounceInOut
###### **[bounceInOut](#bounceInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
Its motion is similar to a ball falling to the floor and then bouncing back up, after several gradually decreasing rebound motion.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## bounceOut
###### **[bounceOut](#bounceOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
Its motion is similar to a ball falling to the floor and then bouncing back up, after several gradually decreasing rebound motion.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## backIn
###### **[backIn](#backIn)**(t : number,  b : number,  c : number,  d : number,  s? : number): number :
[Static] Move backward at the beginning, then reverse towards the target.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	s Specify the amount of overshoot; the higher the value here, the greater the overshoot.

##### Return
The value of the interpolation property for the specified time.

## backInOut
###### **[backInOut](#backInOut)**(t : number,  b : number,  c : number,  d : number,  s? : number): number :
[Static] Start the movement by tracking backward, then reverse the direction and move toward the target, slightly overshoot the target, then reverse the direction again and come back to move toward the target.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	s Specify the amount of overshoot; the higher the value here, the greater the overshoot.

##### Return
The value of the interpolation property for the specified time.

## backOut
###### **[backOut](#backOut)**(t : number,  b : number,  c : number,  d : number,  s? : number): number :
[Static] the beginning of the movement is moving toward the target, slightly overshoot, and then reverse the direction back toward the target。<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	s Specify the amount of overshoot; the higher the value here, the greater the overshoot.

##### Return
The value of the interpolation property for the specified time.

## elasticIn
###### **[elasticIn](#elasticIn)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
where the motion is defined by a sinusoidal wave that decays in an exponential manner.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	a Specifies the amplitude of the sine wave.<br>
@param	p Specifies the period of the sine wave.

##### Return
The value of the interpolation property for the specified time.

## elasticInOut
###### **[elasticInOut](#elasticInOut)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
where the motion is defined by a sinusoidal wave that decays in an exponential manner.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	a Specifies the amplitude of the sine wave.<br>
@param	p Specifies the period of the sine wave.

##### Return
The value of the interpolation property for the specified time.

## elasticOut
###### **[elasticOut](#elasticOut)**(t : number,  b : number,  c : number,  d : number,  a? : number,  p? : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
where the motion is defined by a sinusoidal wave that decays in an exponential manner.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.<br>
@param	a Specifies the amplitude of the sine wave.<br>
@param	p Specifies the period of the sine wave.

##### Return
The value of the interpolation property for the specified time.

## strongIn
###### **[strongIn](#strongIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at zero rate, and then speed up the motion during execution.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## strongInOut
###### **[strongInOut](#strongInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## strongOut
###### **[strongOut](#strongOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## sineInOut
###### **[sineInOut](#sineInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The acceleration of motion in the Sine retardation equation is less than the acceleration of motion in the Quad equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## sineIn
###### **[sineIn](#sineIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at zero rate, and then speed up the motion during execution.<br>
The acceleration of motion in the Sine retardation equation is less than the acceleration of motion in the Quad equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## sineOut
###### **[sineOut](#sineOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The acceleration of motion in the Sine retardation equation is less than the acceleration of motion in the Quad equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quintIn
###### **[quintIn](#quintIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at zero rate, and then speed up the motion during execution.<br>
The acceleration of motion for the Quint retardation equation is greater than that for the Quart retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quintInOut
###### **[quintInOut](#quintInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The acceleration of motion for the Quint retardation equation is greater than that for the Quart retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quintOut
###### **[quintOut](#quintOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The acceleration of motion for the Quint retardation equation is greater than that for the Quart retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quartIn
###### **[quartIn](#quartIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
The motion acceleration of the Quart retardation equation is greater than that of the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quartInOut
###### **[quartInOut](#quartInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The motion acceleration of the Quart retardation equation is greater than that of the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quartOut
###### **[quartOut](#quartOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The motion acceleration of the Quart retardation equation is greater than that of the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## cubicIn
###### **[cubicIn](#cubicIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
The Cubic retardation equation has a greater acceleration of motion than the Quad retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## cubicInOut
###### **[cubicInOut](#cubicInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The Cubic retardation equation has a greater acceleration of motion than the Quad retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## cubicOut
###### **[cubicOut](#cubicOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The Cubic retardation equation has a greater acceleration of motion than the Quad retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quadIn
###### **[quadIn](#quadIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
The acceleration of motion in the Quad retardation equation is equal to the acceleration of motion in the time axis complement of 100% retardation and is significantly less than the acceleration of motion in the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quadInOut
###### **[quadInOut](#quadInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The acceleration of motion in the Quad retardation equation is equal to the acceleration of motion in the time axis complement of 100% retardation and is significantly less than the acceleration of motion in the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## quadOut
###### **[quadOut](#quadOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The acceleration of motion in the Quad retardation equation is equal to the acceleration of motion in the time axis complement of 100% retardation and is significantly less than the acceleration of motion in the Cubic retardation equation.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## expoIn
###### **[expoIn](#expoIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
where each time interval is the remaining distance minus a fixed proportional fraction.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## expoInOut
###### **[expoInOut](#expoInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
where each time interval is the remaining distance minus a fixed proportional fraction.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## expoOut
###### **[expoOut](#expoOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
where each time interval is the remaining distance minus a fixed proportional fraction.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## circIn
###### **[circIn](#circIn)**(t : number,  b : number,  c : number,  d : number): number :
[Static] method starts the motion at zero rate, and then speeds up the motion during execution.<br>
The acceleration of motion in the slow-motion equation produces an abrupt rate change.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## circInOut
###### **[circInOut](#circInOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] The rate is zero at the beginning of the movement, and the movement is first accelerated and then decelerated until the rate is zero.<br>
The acceleration of motion in the slow-motion equation produces an abrupt rate change.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.

## circOut
###### **[circOut](#circOut)**(t : number,  b : number,  c : number,  d : number): number :
[Static] Start the motion at a faster speed, then slow down the motion during execution until the rate is zero.<br>
The acceleration of motion in the slow-motion equation produces an abrupt rate change.<br>
@param	t Specifies the current time, between 0 and the duration (including both).<br>
@param	b Specifies the initial value of the animation property.<br>
@param	c Specifies the total number of changes to the animation properties.<br>
@param	d Specifies the duration of the campaign.

##### Return
The value of the interpolation property for the specified time.



