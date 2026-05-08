# Steam Game Close / Closing Failure

## Soulition
### Problem Solved 5/8/2026 5:30 PM EST:

![Bingo...](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref1-firstfail.png "Normal Logs it seems")
<p> Quick notes:

* Steam showing game open and 'green name' even though game is closed.
* No processes showing that anything is wrong.
* Process hang up for APIJobRequestUserStats and GameOverlay: started...
* Tried to Delete GameOverlayRenderer64.dll and logs...
  * Was unable to do so for some reason
  * Figured it was out it was related to a internet browser issue
  * Stopped process on the broswer and was able to re update Steam Client

### How Problem was Resolved:
* Deleteing everything Except steam.exe and steamapps folders:
  * Additional Issue located: Unable to delete all files even though they're not listed as in use.
  * Discovered Google Chrome hang up issue hidden process for Steam WebClientHelper

### Additional Notes:
<p>Apparently, Steam WebHelper Client, if it gets hung up does not inform you that this is happening. While trying to close VRChat, the process wouldn't completed leaving it hung while giving no proper information that was happening. Without having to clean install steam and remove all programs, I was able to fix the issue by searcing for keywords within specific processes that were completing and figuring out this information.
If you leave your browser on constantly:

**You may have issues with games not closing on steam due to webclienthelper not resolving correctly.**

![Bingo...](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref5-normal.png "Normal Logs it seems")

## Found Concerns:

### 5/8/2026 4:12 PM EST
<p> Found an issue relative to the:

* APIJobRequestUserStats
![image here shows the first concern I had](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref2-CAPI.png "CAPI Failure")
* GameOverlay: started...
   
![image here shows the first concern I had](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref3-gameoverlay.png "CAPI Failure")

<p> Seeming to get hung up and not completing something.

### 5/8/2026 5:07 PM EST
<p> Found an issue where GameOverlayRender64.dll was still running in the background of GoogleChrome and wasn't able to be deleted from the steam folder when attempting to delete everything from the steam folder

![image here shows fianlly able to delete the file](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref4-gameoverlayGChrome.png "Deleted GOR finally")


## Theories


### 5/8/2026 4:55 PM EST
<p> Deleteing everything Except steam.exe and steamapps folders:

* Additional Issue located: Unable to delete all files even though they're not listed as in use.
   * Discovered Google Chrome hang up issue hidden process for Steam WebClientHelper

### 5/8/2026 4:45 PM EST
<p> Running Steam as Admin:

* Failures presist with same issue. 

### 5/8/2026 4:31 PM EST
<p> After opening steam's console by utilizing steam://open/console and seeing the printouts,
I was able to see that 'GameOverlay ...gameoverlayui64.exe' failed to 'post' it seems leaving Steam
in a constant feedback loop of trying ot figure out what's going on and eventially just hanging.
No error codes generated either.

<p> Decided to check google for the Steam gameoverlayui64.exe failure and will be testing out some of the options listed here:

> Fixes for the gameoverlayui64.exe error in Steam, which usually causes the overlay to fail or crash, often involve restarting Steam, updating drivers, or repairing Steam files. Common solutions include running Steam as an administrator, disabling third-party overlay software (like Discord or RivaTuner), or refreshing Steam files by deleting everything except steam.exe and the steamapps folder.

### 5/8/2026 4:12 PM EST
<p> I believe there is a proecss getting hung up that I can't seem to lock down on how or why it's getting hung up, will do some further investigation.

### 5/8/2026 1:20 PM EST
<p> Decided to look into an issue regarding Steam nad a game closure failure that is leaving the process hung up with no processes listed.

<p>Known issues as of right now I can organize into a list:

* Unable to close games without closing Steam.
* Games still displayed as "Playing" but not closing.
* Only happening for VRChat

<p>Working on solving the issue starts now, will use pictures to try and figure out the issue.
