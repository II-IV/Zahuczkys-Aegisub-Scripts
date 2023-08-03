# Autoclip

*Automagically* clip out objects obstructing your sign.

## Usage:
- Create a sign.
- Add a rectangular clip to the first line of the sign, that clip is going to be the watched area.
- Anything entering that clip will be clipped out.
- The frame where you stand in the video is going to be used as the "reference frame". Ideally, that should be a frame where your sign is not obstructed at all.
  - The script looks at your reference frame, and clips out the changes compared to that in other frames. 
- Run AutoClip from the Automation menu.
- Fiddle with the sliders.
- Click "Apply clips"

## Installation:
- Install a recent version of [Python](https://www.python.org/downloads/ "Python"). (testing was done on 3.11.3, but should work on any recent 3.X)
- Install [Vapoursynth](https://www.vapoursynth.com/ "Vapoursynth") >= R63.
  - Most recent vs-tools requires R63. You might be able to circumvent this if you want to hold on to an older version, but no support is provided for that.
  - It is advised to install vapoursynth from their site, rather than from pip. The version in pip is usually older. 
- Download the contents of the /autoclip folder of this repo.
- Place` autoclip/include/zah/autoclip/autoclip.vpy` into your `aegisub/automation/include/zah/autoclip/` folder.
- Place `autoclip/zah.autoclip.lua` into  your `aegisub/automation/autoload` folder.
- Place the `requirements.txt` *somewhere*.
- Open a terminal and `cd` to wherever you put the `requirements.txt`.
- Run `pip install -r requirements.txt`.
- Run `vsrepo.py install lsmas`.
- Install `ILL Library` and `PetzkuLib` from DependencyControl in Aegisub.

## TODO
- Handle moving signs/tracking data for those
- Signs with multiple layers? I forgot about that but Im already writing this readme so *shrug*. 
- More sliders (probably bunch of other VS filters to fine-tune the clip area)
- Simplifying the clips to curves and such.  
- depctrl
- Currently only the longest contour gets taken into account. Maybe combine them? Maybe a slider for this?
- Figure out a way to get and combine every plane of the original video. 
