# Trove-AHK-AutoFish
This is an AutoHotKey script for auto fishing in Trove.Since the original developer has not been updated for five years.I make a reference from his script and made the script that works with the current Trove version

Refer to  https://github.com/howar31/Trove-AHK-AutoFish#trove-ahk-autofish-1

### current updated

**v20200915**
*  Completely fixed the Angle of view change during automatic boot drop

**v20200912**
*  Remove the function hiding windows , since fishing script can't work when hided.
*  Optimize the autothrowboot function , it has some bug in v2015.

**v20200911**
* Add a new function that hiding current window advoid some situations when press ALT+TAB.

**v20200909**
*  NOW we can fishing in Plasma
*  Updating all fishing address make sure it works.
*  Solving thie problem that throw boots can't work since inventory UI were change.

### Update record of original developer

**v20150818**
* [New] Long press F10 for FastABT Mode.  _(Thanks to [KylinWu](https://github.com/KylinWu))_
* [New] Configurable settings for FastABT long press delay (The default is to press 0.5s to activate FastABT).  (FastABTDelay)
* [New] Update Info Tooltip for FastABT Mode.

**v20150817**
> * [Update] Optimize ABT to lower the CPU usage.

**v20150816**
> * [Update] Optimize pole check.  _(Thanks to [KylinWu](https://github.com/KylinWu))_

**v20150815**
> * [Update] Optimize Tooltip refreshing.

Older changelog please visit [commit history](https://github.com/howar31/Trove-AHK-AutoFish/commits/master).

## Feature
* Using **Memory Address** to detect biting.
> Very solid compare to image search or audio detect method.

* Toggleable **Auto Fish**
> Press **F11** to toggle Auto Fish on or off.
>
> You can start/stop auto fishing at any time without exiting the whole script.
>
> Auto Fish will cast and reel in automatically with some useful mechanisms:
>
> * Automatically open your backpack to prevent camera rotate by mousemove.  And also for ABT ImageSearch.
>  * Auto Fish will close and re-open your backpack periodically to reset item rotation in backpack.
>  * ABT is a standalone mechanism which you have to activate it individually.
>
> * Sent Anti-AFK signal to prevent disconnection.
>  * This signal is seperated from the Anti-AFK mechanism.  It will be triggered automatically by Auto Fish.  You don't need to activate Anti-AFK manually.
>
> * Auto Fish will wait 15 seconds first then start detecting the biting.  And auto re-cast if nothing happened after 35 seconds.
>  * According to the Wiki, fish will bite between 20 to 30 seconds.  To lower CPU usage, we only need to check bite after 15 seconds.  Also assume there's error if no bite after 35 seconds and automatically re-cast.
>
> Auto fishing can be minimized and run in the background to automatically fishing for you without interfearence your current work.  That is, you can use your computer while Trove is fishing in your taskbar.
>
> Note that Auto Fish contain Anti-AFK functionality.  You do not need to enable Anti-AFK seperately.

* Toggleable **Auto Boot Throw (ABT)** mechanism.
> Press **F10** to toggle ABT on or off.
>
> Automatically discard the _Old Boot_ from your backpack.  Convenient for long-time fishing.
>
> Turning off the ABT mechanism to make sure AHK won't move your mouse.  Sometimes AHK ImageSearch will mis-find the image and accidentally move your mouse.  It's better to turn ABT off if you are currently working on other windows and have Trove minimized in the background.
>
> ABT is always available even when you're not auto fishing.  You may press **F10** at any time to clean up your backpack.
>
> The ImageSearch interval is set to 2 seconds by default.  You may follow the comments to change this value in script.  Set longer interval to save CPU usage, while set shorter interval to throw boot faster.
>
> Long press **F10** to temporarily activate FastABT Mode.  In this mode the script will throw boots in high speed, instead of the originally 2 seconds per boot.  Useful while cleaning backpack manually.

* Toggleable **Anti-AFK**
> Press **F9** to toggle Anti-AFK on or off.
>
> This is an independent Anti-AFK mechanism from Auto Fish.  You do not need to enable Auto Fish to use this feature (and vise versa).
>
> While enable, Anti-AFK will send "END" key to Trove periodically to prevent AFK, and this key will not interrupt Trove gameplay.  That is, you may play Trove with this feature enable and normal gameplay will not be affected.  And also you may minimize Trove to taskbar, the Anti-AFK will still work in the background.
>
> Note that, you have to press **F9** while Trove window is active for AHK to capture the process ID and send the key correct to Trove.
>
> The key send interval is set to 10 seconds by default.  You may follow the comments to change this value in script.

* Toggleable **Information Tooltip**
> Press **F8** to toggle showing or hiding the info tooltip.
>
> This is a always-on-top tooltip which show the script current status and related information.  So you may see the info on desktop even when Trove minimized.
>
> Hotkeys instruction and fishing info are always available in tooltop.
>
> The Tooltip position is set to 80 X-pixel 150 Y-pixel from top left by default.  You may follow the comments to change this value in script.

* Simulated **Natual Action**
> The script will simulate human keypress and pause to present natual action.

* Configurable **Hotkeys**
> All hotkeys are configurable in the script file.  You may follow the comments to edit the hotkeys in script.


## Installation
1. Download and install AutoHotKey from the [official website](http://www.autohotkey.com/).
> AutoHotKey main program is needed to run the .ahk file.  Running .ahk script file other than the compiled .exe file to make sure that the script is cleanp and pure without any unintended modification.

2. Download files from this repo.
> You may find the **Download ZIP** button on the repo page.  Extract the .zip file and you can find the files below.
 * **TroveAutoFish.ahk**
 > This is the main AHK script file.

 * **boot.bmp**
 > This is the image used for ImageSearch by AHK to find the boot in your backpack.  You may make your own screenshot of _Old Boot_ if the auto boot throw is not working.

3. Put the boot.bmp file under C:\  (C:\boot.bmp)
 > This path is currently hard-coded in AHK script.  So if you want to change the path you may modify the script yourself.

## Usage
1. Double click script file **TroveAutoFish.ahk** to execute the script.
> A _green H_ icon will show up when the script is running.  If you can not execute the script, make sure you have AutoHotKey correctlly installed.

2. Open **Trove**, find a pool, and press **F11** to start auto fishing.
> Auto Fish will automatically open your backpack to prevent camera rotate while moving mouse.  And also allow AHK ImageSearch to find the Old Boot in your backpack.
>
> Auto Fish will close and reopen your backpack to reset the item rotation for porper Imagesearch.

3. The default of auto boot throw (ABT) is off at start.  Press **F10** to toggle on.
> Note that you have to keep Trove window active for AHK ImageSearch.  And AHK will use and move your mouse to throw the boot out of your backpack once if found the match image.s

4. Press **F6** to stop and terminate the whole script.

## Troubleshooting

If Auto Boot Throw (ABT) is not working correctly, it should be the ImageSearch problem.  The reasons and solutions:

1. Item rotated
> Item will rotate while mouse hover on them.  You may close and reopen the backpack to reset the item rotation to default.

2. Window resolution and ratio
> Everyone has different graphic setting.  Sometimes the small resolution and ratio will cause the item image deformation.  You may create a new boot.bmp by yourself.  Just simply take a screenshot of the _Old Boot_.  Note that, hover will rotate the item.  You don't want a rotated image which will cause the ImageSearch fail.

3. Ambient lighting
> The items in backpack will be affected by enviornment lighting in Trove.  Different lighting might cause the item images change color.  You may simple move around to change the fishing position to solve this problem.

Basically re-capture the screenshot of Old Boot on your computer will solve most of the ABT problem.s

## Hotkeys

The hotkeys are all configurable in the script file.  You may change the keys by yourself.

Here are the default hotkey settings:

* **F11** - Toggle Auto Fish on or off
* **F10** - Toggle Auto Boot Throw on or off
 * **Hold F10** to activate Fast Auto Boot Throw which will temporarily throw boot at high speed.
* **F9** - Toggle Anti-AFK on or off
* **F8** - Toggle Info tooltips on or off
* **F6** - Terminate and exit the whole script

All hotkeys info are also displayed in tooltip.

--
