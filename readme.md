A8DS
--------------------------------------------------------------------------------
A8DS is an Atari 8-bit computer emulator for the Nintendo DS/DSi.  Specifically, it targets the 
800XL / 130XE systems and various hardware extensions to increase the memory. 
The stock 800XL had 64KB of RAM. The default A8DS configuration is an
XL/XE machine with 128KB of RAM which will run most of the 8-bit library.
A8DS goes beyond the normal XL/XE 128K machine and provides three alternative 
configurations: the 320K (RAMBO) and 1088K for a few large games and demos 
plus an Atari 800 (non-XL) 48K machine for backwards compatibility with some older 
games that don't play nice with a more "modern" XL/XE setup. As such, it's 
really grown to be a full-featured 8-bit emulator to run nearly the entire 
8-bit line up of games on their Nintendo DS/DSi handhelds.

The emulator comes "equipped" with the ability to run executable images or disk 
images which are the two most popular types. Recent versions add support for 
cart types (CAR or ROM files). The goal here is to make this as simple as 
possible - point to the executable 8-bit Atari image you want to run and off it goes!

![A8DS](https://github.com/wavemotion-dave/A8DS/blob/main/arm9/gfx/bgTop.png)


Optional BIOS Roms
----------------------------------------------------------------------------------
There is a built-in Altirra BIOS (thanks to Avery Lee) which is reasonably compatibile
with many games. However, a few games will require the original ATARI BIOS - and,
unfortunately, there were many variations of those BIOS over the years to support
various Atari computer models released over a span of a decade.

A8DS supports 3 optional (but highly recommended) Atari BIOS and BASIC files as follows:

*  atarixl.rom   - this is the 16k XL/XE version of the Atari BIOS for XL/XE Machines
*  atariosb.rom  - this is the 12k Atari 800 OS-B revision BIOS for older games
*  ataribas.rom  - this is the 8k Atari BASIC cartridge (recommend Rev C)

You can install zero, one or more of these files and if you want to use these real ROMs
they must reside in the same folder as the A8DS.NDS emulator or you can place your
BIOS files in /roms/bios or /data/bios) and these files must be exactly
so named as shown above. These files are loaded into memory when the emulator starts 
and remain available for the entire emulation session. Again, if you don't have a real BIOS, 
a generic but excellent one is provided from the good folks who made Altirra (Avery Lee) 
which is released as open-source software.  Also optional is ataribas.rom for the 8K basic 
program (Rev C is recommended). If not supplied, the built-in Altirra BASIC 1.55 is supplied.

I've not done exhaustive testing, but in many cases I find the Altirra BIOS does a
great job compared to the original Atari BIOS. I generally stick with the open source
Altirra BIOS if it works but you can switch it on a per-game basis in the Options menu.

Do not ask me about rom files, you will be promptly ignored. A search with Google will certainly 
help you. 

Copyright:
--------------------------------------------------------------------------------
A8DS - Atari 8-bit Emulator designed to run on the Nintendo DS/DSi is
Copyright (c) 2021-2023 Dave Bernazzani (wavemotion-dave)

Copying and distribution of this emulator, its source code and associated 
readme files, with or without modification, are permitted in any medium without 
royalty provided this full copyright notice (including the Atari800 one below) 
is used and wavemotion-dave, alekmaul (original port), Atari800 team (for the
original source) and Avery Lee (Altirra OS) are credited and thanked profusely.

The A8DS emulator is offered as-is, without any warranty.

Since much of the original codebase came from the Atari800 project, and since
that project is released under the GPL V2, this program and source must also
be distributed using that same licensing model. See COPYING for the full license
but the original Atari800 copyright notice is retained below:

Atari800 is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

Atari800 is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with Atari800; if not, write to the Free Software
Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA


Credits:
--------------------------------------------------------------------------------
* Atari800 team for source code (http://atari800.sourceforge.net/)
* Altirra and Avery Lee for a kick-ass substitute BIOS, the Altirra Hardware Manual (a must read) and generally being awesome.
* Wintermute for devkitpro and libnds (http://www.devkitpro.org).
* Alekmaul for porting the original A5200DS of which this is heavily based.
* Darryl Hirschler for the awesome Atari 8-bit Keyboard Graphics.
* The good folks over on GBATemp and AtariAge for their support.


Features :
----------------------------------------------------------------------------------
Most things you should expect from an emulator. Games generally run full-speed
with just a handful of exceptions. If you load a game and it doesn't load properly,
just load it again or hit the RESET button which will re-initialize the A8DS machine.
If a game crashes, you will get a message at the bottom of the screen after loading - 
a crash usually means that the game requires the BASIC cart to be inserted and you can
toggle that when loading a game (or using the GEAR icon). Not every game runs with this 
emulator - but 90% will.  I'll try to improve compatibilty as time permits.

The emulator supports multi-disk games. When you need to load a subsequent disk for
a game, just use the Y button to disable Boot-Load which will simply insert the new
disk and you can continue to run. Not all games will utilize a 2nd disk drive but D2: is 
available for those games that do. It's handy to have a few blank 90K single-sided disks 
available on your setup which you can find easily online - these can be used as save disks.

The .ATR disk support handles up to 360K disks (it will probably work with larger disks, but has not 
been extensively tested beyond 360K). 

The emulator has the built-in Altirra BASIC 1.55 which is a drop-in replacement for the
Atari Basic Rev C (only more full-featured). Normally you can leave this disabled but
a few games require the BASIC cart to be present and you can toggle this with the START button
when you load a game. If you try to load a game and it crashes, most likely you need
to have BASIC enabled. Most games don't want it enabled so that's the default. 
If you want to play around with BASIC, enable the BASIC cart and pick a DOS 
disk of some kind to get drive support and you can have fun writing programs. Be aware
that the Altirra BASIC is faster than normal ATARI BASIC and so games might run at the
wrong speed unless you're using the actual ATARI REV C rom.

Cartridge support was added with A8DS 3.1 and later. You can load .CAR and .ROM 
files (using the XEX button).

The following cartridge layouts are supported:
* Standard 8 KB and 16KB
* OSS two chip 16KB
* Williams 32K and 64K
* XEGS/SwXEGS 32K up to 1MB
* MegaCart 16K up to 1MB
* Atarimax 128K and 1MB
* SpartaDOS X 64K and 128K
* Atrax 128K
* Diamond 64K
* Express 64K

If you're using cartridge files, it is suggested you use .CAR files which contain type information to properly load up the cartirdge. Bare .ROM files 
have ambiguities that are not always auto-detected by the emulator and as such will not always load.

Missing :
----------------------------------------------------------------------------------
The .ATX support is included but not fully tested so compatibility may be lower. In order to 
get proper speed on the older DS-LITE and DS-PHAT hardware, there is a Frame Skip option that 
defaults to ON for the older hardware (and OFF for the DSi or above). This is not perfect - some 
games will not be happy to have frames skipped as collisions are skipped in those frames. 
Notably: Caverns of Mars, Jumpman and Buried Bucks will not run right with Frame Skip ON. But 
this does render most games playable on older hardware. If a game is particularlly struggling 
to keep up on older hardawre, there is an experimental 'Agressive' frameskip which should help... but use with caution. 

Remember, emulation is rarely perfect. Further, this is a portable implementation of an Atari 8-bit 
emulator on a limited resource system (67MHz CPU and 4MB of memory) so it won't match the amazing output 
of something like Altirra. If you're looking for the best in emulation accuracy - Altirra is going to 
be what you're after. But if you want to enjoy a wide variety of classic 8-bit gaming on your DS/DSi 
handheld - A8DS will work nicely.

Known Issues :
----------------------------------------------------------------------------------
* Jim Slide XL has some graphical glitching: horizontal lines on the intro screens. Cause unknown.
* Space Harrier cart audio sounds "chip-monkish". Likely cause is frame timing being used vs. cycle-accurate timing.
* Atari Blast! has one column of letters missing on the main title screen. Cause unknown.
* Cropky (music problems in game) - cause unknown.
* Gun Fright (the game doesn't start when you press "3" key) - cause unknown.
* Intellidiscs (no discs sounds in game) - cause unknown.
* TL Cars has graphical glitches - likely separate ANTIC and CPU memory not working right.
* AD:6502 (Arsantica 2) has graphical glitches - likely separate ANTIC and CPU memory not working right.
* Scorch final has issues - cause unknown.
* Rewind demo seems to be missing a sound channel. Cause unknown.
* Bubbleshooter has title screen glitches and garbled graphics on map-side of gameplay. Cause unknown.
* Alley Dog 1MB demo has screen cut-off (bottom) on final part of the demo. Cause unknown.

Troubleshooting :
----------------------------------------------------------------------------------
Most games run as-is. Pick game, load game, play game, enjoy game.

If a game crashes (crash message shows at bottom of screen or game does not otherwise run properly), check these in the order they are shown:

1. Try turning BASIC ON - some games (even a handful of well-known commercial games) require the BASIC cartridge be enabled. 
   If the game runs but is too fast with BASIC on, use the Atari Rev C Basic (slower but should run at proper speed).
2. If BASIC ON didn't do the trick, turn it back off and switch from the ALTIRRA OS to the real ATARI XL OS (you will need 
   atarixl.rom in the same directory as the emulator). Some games don't play nice unless you have the original Atari BIOS.
3. Next try switching from NTSC to PAL or vice-versa and restart the game.
4. A few older games require the older Atari 800 48k machine and Atari OS-B. If you have atariosb.rom where your emulator is located, 
   you can try selecting this as the OS of choice.
5. Lastly, try switching the DISKS SPEEDUP option to OFF to slow down I/O. Some games check this as a form of basic copy-protection 
   to ensure you're running from a legit disk.

With those tips, you should be able to get most games running. There are still a few odd games will not run with the emulator - such is life!

Installation :
----------------------------------------------------------------------------------
* To run this on your DS or DSi (or 2DS/3DS) requires that you have the ability to launch homebrews. For the older DS units, this is usually accomplished via a FlashCart such as the R4 or one of the many clones. These tend to run about US$25. If you have a DSi or above, you can skip the R4 and instead soft-mod your unit and run something like Twilight Menu++ or Unlaunch which will run homebrew software on the DS. The DSi has a convienent SD card slot on the side that saw very little use back in the day but is a great way to enjoy homebrews. See https://dsi.cfw.guide/ to get started on how to soft-mod your unit.
* You will the optional BIOS Files. See BIOS section above.
* You will also need the emulator itself. You can get this from the GitHub page - the only file you need here is A8DS.nds (the .nds is a Nintendo executable file). You can put this anywhere - most people put the .nds file into the root of the SD card.
* You will need games or applications in .XEX or .ATR format. Don't ask me for such files - you will be ignored.

DS vs DSi vs DSi XL/LL :
----------------------------------------------------------------------------------
The original DS-Lite or DS-Phat require an R4 card to run homebrews. With this setup you will be running in DS compatibility mode and emulator will default to a moderate level of frameskip. For the DSi or DSi XL/LL we can run just about everything full speed without frameskip. The XL/LL has a slightly slower decay on the LCD and it more closely mimics the phosphor fade of a TV. This helps with games that use small bullets - something like Centipede can be a little harder to see on the original DSi as the thin pixel shot fades quickly as it moves. You can somewhat compensate for this by increasing your screen brightness. For the DSi, I find a screen brightness of 4 to offer reasonably good visibility. The XL/LL will generally operate just as well with a brigtness of 2 or 3. 

Screen resolution on a DS/DSi/XL/LL is always fixed at 256x192 pixels. The Atari 8-bit resolution tends to be larger - usually 320 horizontally and they often utilize a few more pixels vertically depending on the game. Use the Left/Right shoulder buttons along with the D-Pad to shift/scale the screen to your liking. Once you get the screen where you want - go into the GEAR icon and press START to save the options (including the screen position/scaling) on a per-game basis.

Configuration :
----------------------------------------------------------------------------------
* TV TYPE - Select PAL vs NTSC for 50/60Hz operation.
* MACHINE TYPE - select XL/XE 128K, 320K, 1088K or the compatibility-mode Atari 800 48K (a few older games need this).
* OS Type - Select the built in Altirra OS or, if you have the OS ROMs available, the Atari OS.
* BASIC - Select if BASIC is enabled and what flavor of BASIC to run.
* SKIP FRAMES - On the DSi you can keep this OFF for most games, but for the DS you may need a moderate-to-agressive frameskip.
* PALETTE - Set to Bright or Muted to suit your preferences
* FPS SETTING - Normally OFF but you might want to see the frames-per-second counter and you can set 'TURBO' mode to run full-speed (unthrottled) to check performance.
* ARTIFACTING - Normally OFF but a few games utilize this high-rez mode trick that brings in a new set of colors to the output.
* BLENDING - Since the DS screen is 256x192 and the Atari A8 output is 320x192 (and often more than 192 pixels utilizing overscan area), the blur will help show fractional pixels. Set to the value that looks most pleasing (and it will likely be a different value for different games).
* DISK SPEEDUP - the SIO access is normally sped-up but a few games on disk (ATR/ATX) won't run properly with disk-speedup so you can disable on a per-game basis.
* KEY CLICK - if you want the mechanical key-click when using the virtual 800 keyboards.
* EMULATOR TEXT - if you want a clean main screen with just the disk-drives shown, you can disable text.
* KEYBOARD STYLE - select the style of virtual keyboard that you prefer.

Controller Mapping :
----------------------------------------------------------------------------------

 * D-pad  : the joystick ... can be set to be Joystick 1 or Joystick 2
 * A      : Fire button
 * B      : Alternate Fire button
 * X      : Space Bar (R+X for RETURN and L+X for ESCAPE) - useful to start a few games
 * R+Dpad : Shift Screen UP or DOWN (necessary to center screen)
 * L+Dpad : Scale Screen UP or DOWN (generally try not to shrink the screen too much as pixel rows disappear)
 * L+R+A  : Swap Screens (swap the upper and lower screens... touch screen is still always the bottom)
 * Y      : OPTION console button
 * START  : START console button
 * SELECT : SELECT console button
 
Tap the XEX icon or the Disk Drive to load a new game or the Door/Exit button to quit the emulator.

Compile Instructions :
-----------------------
I'm using the following:
* devkitpro-pacman version 6.0.1-2
* gcc (Ubuntu 11.3.0-1ubuntu1~22.04) 11.3.0
* libnds 1.8.2-1

I use Ubuntu and the Pacman repositories (devkitpro-pacman version 6.0.1-2).  I'm told it should also build under 
Windows but I've never done it and don't know how.

If you try to build on a newer gcc, you will likely find it bloats the code a bit and you'll run out of ITCM_CODE memory.
If this happens, first try pulling some of the ITCM_CODE declarations in and around the Antic.c module (try to leave
the one in CPU as it has a big impact on performance).  

--------------------------------------------------------------------------------
History :
--------------------------------------------------------------------------------
V3.2 : 13-May-2023 by wavemotion-dave
  * Enhanced configuration - unfortunately your old config save will be wiped to make way for the new method.
  * Global options - use the GEAR icon before a game is loaded and you can save out defaults for newly loaded games.
  * Key maps - set any of the DS keys to map into various joystick, console buttons, keyboard keys, etc. 
  * Screenshot capability - press and hold L+R for ~1 second to take a .bmp snapshot (saved to a time-date.bmp file)
  * New Smooth Scroll handling so you can set your scale/offset and then map any button to shift vertical/horizontal pixels (set keys to VERTICAL++, HORIZONTAL--, etc). The game will automatically smooth-scroll back into place when you let go of the pixel-shift button.
  * Improved cart banking so that it's as fast as normal memory swaps. This should eliminate slowdown in Cart-based games.
  * A few bug fixes as time permitted.

V3.1 : 08-May-2023 by wavemotion-dave
  * Added CAR and ROM support for the more popular cartridge types up to 1MB.
  * Added Real-Time Clock support for things like SpartaDOS X
  * Added new D-Pad options to support joystick 2 (for games like Wizard of Wor) and diagonals (Q-Bert like games).
  * Improved keyboard handling so CTRL key is now sticky.
  * Improved menu transitions to reduce audio 'pops' as much as possible.
  * Auto-rename of XEGS-DS.DAT to A8DS.DAT to match new branding.
  * Squeezed as much into fast ITCM_CODE as possible with almost no bytes left to spare.
  * Other cleanups and minor bug fixes as time allowed.

V3.0 : 05-May-2023 by wavemotion-dave
  * Rebranding to A8DS with new 800XL stylized keyboard and minor cleanups across the board.
  
V2.9 : 12-Dec-2021 by wavemotion-dave
  * Reverted back to ARM7 SoundLib (a few games missing key sounds)
  
V2.8 : 30-Nov-2021 by wavemotion-dave
  * Switched to maxmod audio library for improved sound.
  * Try to start in /roms or /roms/a800 if possible

V2.7 : 04-Nov-2021 by wavemotion-dave
  * New sound output processing to eliminate Zingers!
  * bios files can now optionally be in /roms/bios or /data/bios
  * Left/Right now selects the next/previous option (rather than A button to only cycle forward).
  * Other cleanups as time permitted.

V2.6 : 11-Jul-2021 by wavemotion-dave
  * Reduced down to one screen buffer - this cleans up ghosting visible sometimes on dark backgrounds.
  * If atarixl.rom exists, it is used by default (previously had still been defaulting to Altirra rom)
  * Minor cleanups as time permitted.

V2.5 : 08-Apr-2021 by wavemotion-dave
  * Major cleanup of unused code to get down to a small but efficient code base.
  * Added LCD swap using L+R+A (hold for half second to toggle screens)
  * Cleanup of text-on-screen handling and other minor bug fixes.

V2.4 : 02-Apr-2021 by wavemotion-dave
  * New bank switching handling that is much faster (in some cases 10x faster)
    to support all of the larger 128K, 320K and even the 1088K games (AtariBlast!)
  * ATX format now supported for copy protected disk images.

V2.3 : 31-Mar-2021 by wavemotion-dave
  * Added Atari 800 (48K) mode with OS-B for compatiblity with older games.
  * L+X and R+X shortcuts for keys '1' and '2' which are useful to start some games.
  * Cleanup of options and main screen for better display of current emulator settings.

V2.2 : 25-Mar-2021 by wavemotion-dave
  * Added simplified keyboard option for easy use on Text Adventures, etc.

V2.1 : 21-Mar-2021 by wavemotion-dave
  * Cleanup of the big 2.0 release... 
  * Allow .XEX and D1 to both be loaded for XEX games that allow save/restore.
  * Fixed long-standing file select offset bug.

V2.0 : 19-Mar-2021 by wavemotion-dave
  * Major overhaul of UI.
  * Added second disk drive.

V1.9 : 06-Mar-2021 by wavemotion-dave
  * New options for B button = DOWN and Key Click Off.
  * Improved handling for key clicks so that press and hold will auto-repeat.

V1.8 : 25-Feb-2021 by wavemotion-dave
  * Added option for slower I/O (disk reads) as a few games will detect that
    the game is not running at the right speed and not play (copy protection 
    of a sort ... 1980s style). So you can now slow down the I/O to get those
    games running.
  * Reverted to "Old NTSC Artifacting" after discovering at least one game
    does not play nicely with the new artificating. Still investigating but
    this cures the problem for now (the game was Stellar Shuttle).
  * Added the R-TIME8 module for time/date on some versions of DOS.
  * Other minor cleanups as time permitted.

V1.7 : 18-Feb-2021 by wavemotion-dave
  * Added saving of configuration for 1800+ games. Press L+R to snap out config
    for any game (or use the START key handling in the Options Menu).
  * Autofire now has 4 options (OFF, Slow, Medium and Fast).
  * Improved pallete handling.
  * Improved sound quality slightly.
  * Other cleanups as time permitted.

V1.6 : 13-Feb-2021 by wavemotion-dave
  * Added 320KB RAMBO memory expanstion emulation for the really big games!
  * Added Artifacting modes that are used by some high-res games.
  * Improved option selection - added brief help description to each.
  * Improved video rendering to display high-res graphics cleaner.
  * Fixed directory/file selection so it can handle directories > 29 length.

V1.5 : 10-Feb-2021 by wavemotion-dave
  * Added Frame Skip option - enabled by default on DS-LITE/PHAT to gain speed.
  * Minor cleanups and code refactor.

V1.4 : 08-Feb-2021 by wavemotion-dave
  * Fixed Crash on DS-LITE and DS-PHAT
  * Improved speed of file listing
  * Added option for X button to be SPACE or RETURN 

V1.3 : 08-Feb-2021 by wavemotion-dave
  * Fixed ICON
  * Major overhaul to bring the SIO and Disk Loading up to Atari800 4.2 standards.
  * New options menu with a variety of options accessed via the GEAR icon.

V1.2 : 06-Feb-2021 by wavemotion-dave
  * Altirra BASIC 1.55 is now baked into the software (thanks to Avery Lee).
  * Fixed PAL sound and framerate.
  * Cleanups and optmizations as time permitted.
  * Tap lower right corner of touch screen to toggle A=UP (to allow the A key
    to work like the UP direction which is useful for games that have a lot
    of jumping via UP (+Left or +Right). It makes playing Alley Cat and similar
    games much more enjoyable on a D-Pad.

V1.1 : 03-Feb-2021 by wavemotion-dave
  * Fixed BRK on keyboard.
  * If game crashes, message is shown and emulator no longer auto-quits.
  * Improved loading of games so first load doesn't fail.
  * Drive activity light, file read activity for large directories, etc.
  
V1.0 : 02-Feb-2021 by wavemotion-dave
  * Improved keyboard support. 
  * PAL/NTSC toggle (in game select). 
  * Ability to load multiple disks for multi-disk games (in game select).
  * Other cleanups as time permits...

V0.9 : 31-Jan-2021 by wavemotion-dave
  * Added keyboard support. Cleaned up on-screen graphics. Added button support.

V0.8 : 30-Jan-2021 by wavemotion-dave
  * Alpha release with support for .XEX and .ATR and generally runs well enough.
 



