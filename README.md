# Steam Game Close / Closing Failure

### 5/8/2026 1:20 PM EST
<p> Decided to look into an issue regarding Steam nad a game closure failure that is leaving the process hung up with no processes listed.</p>

<p>Known issues as of right now I can organize into a list:</p>


* Unable to close games without closing Steam.
* Games still displayed as "Playing" but not closing.
* Only happening for VRChat

<p>Working on solving the issue starts now, will use pictures to try and figure out the issue.</p>

## Soulition
<p>This is a place older section until the fix is found.</p>

## Found Concerns:

### 5/8/2026 4:12 PM EST
<p> Found an issue relative to the:</p>

* APIJobRequestUserStats
![image here shows the first concern I had](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref2-CAPI.png "CAPI Failure")
* GameOverlay: started... 
![image here shows the first concern I had](https://github.com/CHarris-VR/steam-gameclose-failure/blob/main/refs/ref3-gameoverlay.png "CAPI Failure")

<p> Seeming to get hung up and not completing something.</p>

## Theories

### 5/8/2026 4:12 PM EST
<p> I believe there is a proecss getting hung up that I can't seem to lock down on how or why it's getting hung up, will do some further investigation.</p>

### 5/8/2026 4:31 PM EST
<p> After opening steam's console by utilizing steam://open/console and seeing the printouts,
I was able to see that 'GameOverlay ...gameoverlayui64.exe' failed to 'post' it seems leaving Steam
in a constant feedback loop of trying ot figure out what's going on and eventially just hanging.
No error codes generated either.</p>

<p> Decided to check google for the Steam gameoverlayui64.exe failure and will be testing out some of the options listed here: </p>

> Fixes for the gameoverlayui64.exe error in Steam, which usually causes the overlay to fail or crash, often involve restarting Steam, updating drivers, or repairing Steam files. Common solutions include running Steam as an administrator, disabling third-party overlay software (like Discord or RivaTuner), or refreshing Steam files by deleting everything except steam.exe and the steamapps folder.
