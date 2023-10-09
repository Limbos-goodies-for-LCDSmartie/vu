# vu
A plugin to create VU meter son your LCD Screen for the master volume output

### Instructions
Copy the vu.dll and CoreAudioApi.dll to LCD Smartie plugins folder.
Set dll check interval to a value lower than 100 milliseconds. 
Use `$Bar` command to create VU bars to your screen.

### Examples
Left channel with length of 18 clocks and **dynamic** bar response `$Bar($dll(vu,2,,x),100,18)`
Left channel with length of 18 clocks and **dynamic** bar response `$Bar($dll(vu,3,,x),100,18)`
Master channel with length of 40 clocks and **smooth** bar response `$Bar($dll(vu,1,,),100,18)`

### Actions
The two actions below can be used to auto switch to Theme 2 when master ooutput is active (e.g. sound playing)
```
Action01Variable=$dll(vu,19,,)
Action01Condition=2
Action01ConditionValue=1
Action01Action=GotoTheme(2)
Action01Enabled=True
```

```
Action01Variable=$dll(vu,19,,)
Action01Condition=2
Action01ConditionValue=0
Action01Action=GotoTheme(1)
Action01Enabled=True
```
You have to add your screen with the VU meters to Theme 2 
TIP: Set a screen display time around 3-5 seconds to keep the screen active between the music pauses.

