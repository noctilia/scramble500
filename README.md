Scramble 500

This is a (successful) attempt by jotd to create a 1:1 port of the famous arcade game on Amiga 500 using 100% 68k assembly.

The display is 4:3 so scores, lives, bonuses are on the side rather than on top/botton. The gameplay layout is 1:1 vs
the original, though.

REQUIRES:

- any 68k CPU
- Kickstart 1.3, 1MB memory
- Kickstart 2.0, 1MB memory

FEATURES:

- original visual & sounds
- faithful enemy behaviour & speed & increasing difficulty
- 50 frames per second (PAL) even on a 68000 A500
- all levels
- joystick controlled (port 1) or keyboard controls (arrows + space)
- can run directly from shell or from whdload (fast machines/complex configurations)

CONTROLS:

- joystick directions/arrows: move player
- control/left alt/fire button/second button: start game
- P/second button: pause
- F10 (or quitkey): quit (and save scores)
- two button joystick/joypad: fire to shoot, second button to bomb
- one button joystick: fire to shoot and bomb
- when game is about to start (intro music playing), press any
  direction to change controls. If a cd32 joypad is connected, two button
  mode is selected by default. Also, if keyboard is used to launch bombs,
  it also selects two-button mode.
  If game is started using bomb or second button, two-button mode is also
  selected.

HOW TO PLAY:

- all levels: shoot/bomb everything! don't miss fuel tanks to avoid running out of fuel
- level 1: avoid landscape and flying rockets
- level 2: shoot UFOs
- level 3: avoid fireballs
- level 4: same as 1, just more difficult
- level 5: navigate up and down without hitting the walls
- level 6: destroy base

CREDITS:

- Jean-Francois Fabre (aka jotd): code and gfx/sfx conversion
- hajodick (EAB): game map rips from the arcade
- Andrzej Dobrowolski (aka no9): technical advice on sfx
- Scott Tunstall: brilliant reverse engineering work of the arcade version 
- Frank Wille (aka phx): sfx/module player
- meynaf: random routine
- eab forum: useful advice & support
- 125scratch: sprite rips https://www.spriters-resource.com/arcade/scramble
- konami: original game :)

ISSUES:

- level 4/5 filler is reverted (brick then square) in the bottom section
  or is it the odd/even tile pattern?
- sometimes cannot bomb objects (objects not destroyed): make a test mode
  where bombing just tells when it worked or not but don't destroy target
  stop scrolling and test various bombing positions for the same object
- lockup on CDTV despite the startup code: executable doesn't load on 68000 segment issue
- center the screen
- scrolling is flickering on slow cpus

TODO

- demo mode

BUILDING FROM SOURCES:

Prerequesites:

- Windows
- python
- Amiga NDK
- sox (included)
- vasm 68k (included)
- gnu make

* besides the .bin files created from png by python, the rest of the process could be built on an amiga with phxass
 or some other assembler and sox for the amiga, but you have to be really mad to attempt it in 2021...)
* could be done on Linux, just rebuild vasm

Build process:

- To create the ".bin" files and some palette .s asm files, from "assets" subdir, 
  just run the "convert_sprites.py" python script, then use the "convert_sounds.py"
  python script (audio).
- python and sox must be installed to be able to perform the wav2raw conversions
- get "bitplanelib.py" (asset conversion tool needs it) at https://github.com/jotd666/amiga68ktools.git

Binary assets must be created first, then makefile must be called to create the "mspacman" program


