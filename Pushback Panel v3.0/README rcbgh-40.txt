###############################################################################
#                                                                      #
# RCBgh-40.zip:  Groundhandling gauges for FS2004 aircraft             #
#                                                                      #
#                        By Rob Barendregt                25 may 2005  #
#                                                         Release 4.0  #
########################################################################


PLEASE, READ THIS MANUAL CAREFULLY BEFORE INSTALLING & USING THESE GAUGES.

NOTE: THIS VERSION NO LONGER SUPPORTS FS2002 !!!

This archive contains a set of groundhandling gauges which you can add to the
panel of any FS2004 aircraft, such as a Pushback gauge and a Taxispeed gauge.

Especially for existing users of these gauges:
- I suggest to read the whole document again, although most of it will sound
  familiar.
- For changes w.r.t. V3.2(-A), see section History.
- When installing this set in a panel.cfg, remove the old definitions.
- This gauge set is incompatible with V3.2, so DON'T mix the gauge definitions
  in one panel.cfg; all gauges and files have new, unique names so they shouldn't
  overwrite anything during installation. It also means that, should you wish,
  you can have V3.2 in one panel and V4.0 in another.

*******************************************************************************
* This gaugeset is dedicated to Bill Morad, the author of the original FS2002 * 
* XMLsound gauge. Without him, I would probably never have created the        *
* Pushback gauge. Unfortunately Bill died from heart problems on 23 dec. 2002 *
*******************************************************************************


0. Contents
===========
1.     Introduction
2.     Installation
3.     Gauge operation
3.1    Obsolete.
3.2    Pushback operation
3.2.1  Pushback timer/counters, buttons and phases
3.2.2  Pushback Operation and Ground-Cockpit conversation
3.3    Taxispeed operation
3.3.1  Taxispeed indicators and dials
3.3.2  How the Taxispeed control works
3.4    ARM-L: Activate Taxispeed control after landing
3.5    Parking Brakes gauge
3.6    Brakes Pressure gauge
3.7    Brakes Sound gauge
4.     Copyrights and Disclaimer
5.     Credits
6.     History and known problems
7.     Closure

Appendix-1: Gauge positioning in aircraft panels
Appendix-2: Used Sound files.
Appendix-3: The "brakes" problem in FS2004.



1. Introduction
===============
Do you recognise this ??
- I push Shift-P to start Pushback, press 1 or 2 for a Left c.q. Right
  turn, but the aircraft doesn't make the turn ....
- I want to see the Pushback from SpotPlane View mode ....
- I want to Pushback my aircraft from the gate onto the taxiway,
  but I don't know when to start the Left or Right Turn ....
- When my aircraft is taxiing, I can't control the speed properly ....
- Are my toebrakes working correctly, what's the applied brake pressure ? ...

These gauges will solve these problems  !!
And add some nice Pushback conversation sounds, and click/warning sounds too.

These gauges can be installed in any panel for any aircraft, as an overlay
window activated by an (included) window toggle icon in your main panel window.

What they offer:
- A Pushback gauge:
  - The Pushback sequence can be performed automatically, by setting the 
    time it should be pushed straight back, plus the desired turn angle.
  - It uses the standard FS2004 Pushback mechanisme, so you can hear the 
    engine/environment sounds during Pushback.
  - During Pushback, you can change the views or even PAUSE the system
    without disturbing the Pushback. 
  - To support Pushback operation, the cockpit-ground conversation is made
    audible.
- A Taxispeed gauge:
  Controls the groundspeed of the aircraft while taxiing, by manipulating the
  throttles AND the brakes if needed.
- A AutoTaxiAfterLanding switch:
  This switch allows you to arm the Taxispeed controller.
  After the aircraft has landed, and the speed has decreased to below 40 Knots
  the Taxispeed controller is automatically activated. If applicable, it also
  retracts flaps/spoiler and deactivates reverse-thrust and the autobrakes.
- A ParkingBrake switch:
  This switch shows the position of the Parking Brakes, and lets you
  (de-)activate them.
- BrakePressure gauge:
  This gauge displays the braking pressure you apply with the toebrakes.
- BrakeSound gauge.
  This gauge makes the sound of braking audible.


2. Installation
===============

1. Extract all files to the MAIN FS2004 folder, using the "Use folder names"
option. This will place each file in it's correct location. 
Overwrite older files when asked.

2. Add the gauges to the panel of your aircraft(s).

Placing the gauges in your panel is done by adding some lines to the panel.cfg
file of your aircraft, located in the ...\Flight Simulator 9\Aircraft\"your
aircraft"\Panel\ folder. The simplest way of doing that is by using Notepad.
*** MAKE A BACKUP OF YOUR panel.cfg FIRST ***

- In the [Window Titles] section, add the line:

Window**=Groundhandling

where '**' is the next free number.


- Under [Window00] (which usually is the main panel window), add:

gauge**=rcb_groundhandling4!Icon_Pushback, aaa,bbb,12,12

where '**' is the next free number, 'aaa'and 'bbb' are the coordinates for the
groundhandling Icon on your panel and 12,12 is the size in pixels.
See also Appendix-1.

For the default FS2004 Boeing 747_400 ONLY !!:
       gauge58=rcb_groundhandling4!Icon_Pushback, 128,111,12,12

- After the last [Window..] section, add the lines (use copy/paste to avoid
  typing errors):

[Window**]
size_mm=239,65                 // The relative window size in pixels.
ident=10005                    // The ident used by Icon_Pushback.
visible=0                      // 0: hidden when aircraft is loaded.
window_size= 0.30,0.11         // Window screen size: 30 % Hor., 11 % Vert.
position=0                     // 0: opens in top-left of screen.
background_color=16,16,16
gauge00=rcb_Groundhandling4!PushbackDisplay,         2,2,74,61
//gauge01=rcb_Groundhandling4!TaxispeedToeBrakes,      79,2,64,61 //If you have ToeBrakes
gauge01=rcb_Groundhandling4!TaxispeedNoToeBrakes,    79,2,64,61 //If you have NO ToeBrakes
gauge02=rcb_Groundhandling4!BrakePressure,           146,2,44,61
gauge03=rcb_Groundhandling4!ParkingBrakeSwitch,      193,2,44,30
gauge04=rcb_Groundhandling4!AutoTaxiAfterLanding,    193,33,44,30
gauge05=rcb_Groundhandling4!PushbackStates, 0,0
gauge06=rcb_Groundhandling4!BrakeSound, 0,0
gauge07=GH_Sound!dsd_xml_sound3, 0,0,,, ./sound/Groundhandling/Sound.ini

where '**' is the same number you used in the [Window Titles]

You can open the Groundhandling window by clicking the icon (the DownArrow) in
your main panel, or via menu Views - Instrument Panel.

NOTES:
1. IMPORTANT--IMPORTANT--IMPORTANT--IMPORTANT--IMPORTANT--IMPORTANT--IMPORTANT
   Due to differences in the Brakes implementation in FS2004 with respect to the
   use of Toebrakes pedals, you must select the appropriate version:
   You can use another version by removing/inserting "//" in front of a line.
   !! MAKE SURE YOU HAVE ONLY 1 VERSION ACTIVE !!
   For a detailed explanation, see Appendix-3.
2. You can change the "window_size= " if you prefer a smaller window.
3. If you like the window to appear on another default location, change the
   "position= " to a value 1 to 8 (with 8 being the bottom-right corner).
4. If you find the pushback conversation sounds too loud, you can change
   them in the sound.ini file; individually per sound.
   Just open the sound.ini file with Notepad, search for the GH_****.wav
   file, and edit the volume number in that line:
   - 100 is max. (default) volume.
   - 70 is the min. volume (makes the sound almost inaudible)
   For an explanation of the used sound files: see Appendix-2.


3. Gauge operation
==================
A few general remarks first:
- All gauges have Tooltips on their clickable area's, describing their function
  Make sure you have the Tooltips enabled in FS2004.
- The lighted pushbuttons of all gauges have three main states, colored as
  follows:
  - RED:   Function Blocked (when clicked, the ProcedureError sound is played)
  - Off:   Function Inactive, click to activate.
  - GREEN: Function Active, click to de-activate.
- To set dials, you can also use the mouse scrollwheel instead of clicking.


3.1 Obsolete (SOUND On/Off gauge is no longer needed) 
============

3.2 Pushback operation
======================
3.2.1 Pushback timer/counters, buttons and phases
=================================================

The gauge consists of 4 clickable areas:
- A pushbutton, to activate Pushback.
  This button has an indicator light, giving the phase of pushback:
  - RED: Pushback cannot be activated; make sure your Parking Brakes are set, 
         and the aircraft is standing still.
  - OFF: Click button to activate Pushback procedure.
  - Flashing GREEN: Waiting for release of the Parking Brakes,
    which starts the Pushback.
  - GREEN: Pushing back.
  - Flashing YELLOW: Pushback finished, set your Parking Brakes.
  - YELLOW: Pushback procedure terminating.
- A StraightBack counter.
  This counter (0 - 999 meters, the right 3 digits) is started when  you
  release the Parking Brakes and determines how long the aircraft is pushed
  straight back before the turn sequence (if selected) starts.
  Click to increment or decrement the value.
- A Turn selector.
  Toggles between pushing straight back, or left/right turn (after the set 
  straight back distance). When Left or Right turn is selected, the Turn
  counter is set to 90 degrees.
- A Turn Counter.
  This counter (0 - 90 degrees, the left two digits) determines the angle of
  the Turn that you want the aircraft to make.
  Click to increment or decrement the value.

A few notes: 
1. "Turning Left" means: the aircraft turns clockwise in TopView c.q. the
   heading increases while turning. As the standard FS pushback does.
2. When Pushback is active (GREEN light), you cannot change the Timer/Counter
   values anymore.
3. When Pushback is active (GREEN light), you can terminate the Pushback
   at anytime by setting the Pushback switch again.
4. After setting up the Timer/Counters, and activating the Pushback by clicking
   the button, you can change the view mode at any time.
   E.g.: Go to SpotPlane view, release the Parking Brakes and observe the full
   Pushback in this view. The Pushback conversation will even be audible in
   SpotPlane view mode. You can even PAUSE FS2004 during the Pushback session.
5. After the StraightBack counter becomes 0 (so before it makes the actual turn),
   the aircraft goes straight back another full length.
   This "full length" period depends on the aircraft:
   - For a Cessna 172: 3 seconds.
   - For a Boeing 747-400: 19 seconds.
6. You can use Pushback either with Engines off, or with engines running.
   You can also start your engines during Pushback operation.
7. Manipulating the Parking Brakes during the entire pushback procedure is inhibited,
   except where the procedure requires setting resp. releasing the Parking Brakes.
8. During the entire pushback procedure, the throttles forced to Idle position.



3.2.2 Pushback Operation and Ground-Cockpit conversation
========================================================
- Set the Parking Brakes.
  The RED light goes off.
- Set the Straightback counter: number of meters before a turn.
- Select the Turn type: None, Left or Right.
- If Left/Right, adjust the turnangle if needed,
- Activate the Pushback procedure by clicking the Pushback button.
  The GREEN light starts flashing.

Cockpit: "Ground from cockpit"
Ground:  "Go ahead"
Cockpit: "Ready for pushback"
Ground:  "OK. Steering pin inserted, release brakes"

- The gauge now waits untill you release the Parking Brakes; a ticker sound is
  played in the mean time, to indicate that the gauge awaits a Parking Brakes
  operation.

Cockpit: "Brakes are released"
Ground (if engine1 is running): "OK. Pushing back"
Ground (if engine1 NOT running: "OK. Pushing back. All engines cleared for
                                 startup"

The following Pushback sequence is performed:
- The light goes solid GREEN. 
- If the StraightBack Timer was set, it counts down to 0 while the aircraft is
  pushed straight back.
- If the LeftTurn or RightTurn Counter was set, the aircraft is pushed straight
  back ANOTHER FULL LENGTH, and then turns the angle dialed into the Counter.
  During the turn the Counter indicates the remaining turn angle, and therefore
  counts down to 0.
- After the turn is completed, the aircraft is pushed straight back again for
  the new time you dialed into the StraightBack Timer (default: 2 second).
While a Pushback is active, an aircraft "rolling" sound is played; this sound
is especially noticeable when the engines are off during the pushback.

Ground: "Set parking brakes"

- The AMBER light start flashing.
  The gauge waits untill you set the Parking Brakes; the ticker sound is played
  again.

- The light goes solid AMBER.

Cockpit: "Parking brakes are set. Prepare aircraft for taxi and give 
          handsignal on left side"
Ground:  "OK. Towing system removed. Wait for handsignal on left-hand side"

- Now the pushback is terminated, and the light goes off.

 

3.3 Taxispeed operation.
========================
3.3.1 Taxispeed indicators and dials
====================================
The gauge consists of 3 clickable areas:
- A pushbutton, to activate/deactivate the gauge.
  This button has an indicator light, colored as follows:
  - RED: Gauge cannot be activated.
    The gauge can only be activated when:
    - the Parking Brakes are released.
    - the aircraft is on the ground.
    - the engines are running.
    - pushback is inactive.
  - OFF: Click button to activate the gauge.
  - GREEN: The Taxispeed control is Active.
- The Target Taxispeed (the Left two digits). Default: 15 knots.
  Click to increment or decrement the value.
  You can change the target speed at any time, even if the gauge is active.
- The Actual Groundspeed (the Right two digits).


3.3.2.How the Taxispeed control works
=====================================
When Active, the Taxispeed gauge controls the groundspeed of the aircraft while
taxiing, by manipulating the throttles according to an adaptive algorithm.
  - When activated, it disables the AP's AutoThrottle and SpeedHold functions. 
  - The target taxispeed can be adjusted from 3 - 40 knots.
  - The actual taxispeed is kept constant within 1 knot of the set target
    speed when the aircraft is taxiing straight-ahead; the speed may deviate 
    a bit more after initial acceleration, heavy braking or sharp turns.
  - The gauge automatically deactivates when:
    - The Parking Brakes are set.
    - The throttle are manually set to > 70% (usually to start takeoff).
    When this happens, an attention sound is played. 
  - When Brakes are applied by the user, the gauge temporarily sets the 
    throttles to idle, untill they are released again.
  - When the actual groundspeed - targetspeed is more than 4 knots, the Brakes
    are applied automatically. This happens in the following cases:
    - If you activate the gauge after a landing, when the groundspeed is still
      much larger than the set target speed
    - If you subtantially decrease the target speed while the gauge is already
      active.
    - Occasionally with heavy aircraft, after a long sharp turn (caused by the 
      weight of the plane, combined with the engine spooldown time).
    - When your aircraft accellerates even with throttles set to idle, e.g. 
      if there is a very strong tailwind while taxiing. Moreover, some aircraft
      in FS have the tendancy to start rolling even with throttles at idle.

A few notes:
1. The control is based on actual groundspeed, so it will also work with wind
   enabled.
2. The adaptive control algorithm is obviously a compromise between accuracy
   (overshoot, undershoot, reaction time), and is strongly influenced by
   aircraft characteristics like weight and spoolup/spooldown times. But you
   will find that it works rather smooth, without constant "jumping" throttles,
   and for most types of aircraft.
3. When the Taxispeed gauge is activated, make sure that your physical throttle
   axis is in the idle position, to avoid interferance with the control (due to
   axis "jitter"). If your throttle controller still jitters in idle (you will
   have problems with Reverse Thrust too !), create a small deadzone by
   increasing the Nullzone for the Throttle axis via menu
   Options-Controls-Sensitivities.
4. This Taxispeed gauge only work for the aircraft YOU are flying, NOT for your
   AI aircraft; that's another utility :-)


3.4 ARM-L: Activate Taxispeed control after landing
=====================================================
This pushbutton switch allows you to Arm the Taxispeed controller, and is
colored as follows:
- RED:   Gauge cannot be activated.
         The gauge can only be activated when the aircraft is in the air.
- Off:   Click to arm the Taxispeed controller.
- GREEN: The Taxispeed controller is armed. Click to disarm.

When active, the aircraft has landed AND the groundspeed has decreased to below
40 Knots:
  - The Taxispeed controller is automatically activated.
  - Spoilers and Flaps are retracted.
  - Autobrakes are set Off.
  - Reverse Thrusters are deactivated.


3.5 Parking Brakes gauge
========================
This pushbutton switch shows the position of the Parking Brakes, and is colored
as follows:
- Off:   Parking Brakes are released. Click to set.
- GREEN: Parking Brakes are set. Click to release.



3.6 Brake Pressure gauge
========================
This gauge displays the braking pressure (0 - 100 %) you apply with the
Left/Right toebrakes, indicated by two green bars. Note that when the Parking
Brakes are set, both bars always indicate max. pressure.


3.7 Brake Sound gauge
========================
This gauge will trigger a brakes sound when the aircraft is on the ground, 
the brake pressure is > 30% and groundspeed is > 5 knots.


4. Copyrights and Disclaimer
============================
This gaugeset is freeware, and is available for your personal use.

Without my explicite permission, it may NOT be sold, re-distributed and/or 
uploaded to another website or bulletin board (in ANY shape or form).

If you want to bundle (part of) this gaugeset with your (freeware !!) panel, 
you may ONLY do so AFTER my explicite permission and inclusion of this
README file AS-IS.

And obviously, installing & using this gauges is at your own risk !!
However, if you execute the Installation instructions properly, this gaugeset
will NOT crash you PC or FS, nor will it have substantial impact on performance


5. Credits
==========
- Arne Bartels, for his great introduction on how-to-make XML gauges.
- Ron Beal, for his re-recorded Pushback conversation sounds.
  I just modified them a bit to add the stereo effect.
- The FPDA group, for their original implementation of the pushback gauge
- Doug Dawson, for his great XMLsound sound playing gauge.

6. History
==========
Changes in V4.0:
- Sound mechanism now uses Doug Dawsons dsd_xml_sound3 gauge, with advantages:
  - More robust implementation, no more sound problems :-)
  - You can adjust the sound volume for each sound individually in the sound.ini
  - No more use of the ADF1 frequency for soundplaying
- This version NO LONGER works for FS2002.
- Reworked bitmaps and code.
- More meaningfull (state-dependant) tooltips.
- In the Pushback gauge:
  - You can now set the "Straightbacktime" in meters instead of seconds.
  - Left/Right angle selection replaced by 1 counter plus direction selector.
  - You can abort the Pushback at anytime by clicking the main switch.

7. Closure
==========
I hope you enjoy using these gauges; I know many people did with the previous
FS2002 versions. And I'm always open to questions, or suggestions for
improvement (no guarantee that I will make them though).
But PLEASE PLEASE, before asking me questions or report "bugs", make sure that
the answer can't be found in this README file; I have spent considerable time
in making this README, just to avoid wasting both YOUR time and MINE with
trivial questions and "issues" :-)

Rob Barendregt, The Netherlands
Email: rc.barendregt@planet.nl

               **************************************




Appendix-1 Gauge positioning in aircraft panels
===============================================
The Main panel usually consists of a bitmap (a .bmp file) on which the gauges
are positioned through coordinates.
Like: gauge**=rcb_groundhandling!Icon_Pushback, aaa,bbb,12,12 ,
 where 'aaa' is the horizontal, and 'bbb' the vertical positon on the panel.
The bitmap is a file xxxxx.bmp in the same folder as panel.cfg, and is
referenced in the panel.cfg by something like:

[Window00]
File=xxxxx.bmp

The coordinates 'aaa','bbb' are relative to this panel bitmap, and specify the
top-left corner of the gauge. Coordinates 0,0 indicate the top-left position of
the panel.

Most main panel bitmaps cover the entire screen, but some (like the default
747) only cover the lower part of the screen. Moreover, the coordinates (and
gauge size) also depend on the bitmap resolution.
So, in a 1024*768 pixel bitmap, coordinates 1024,768 specify the bottom-right
corner of the panel.
With this info, look at the coordinates of existing gauges in the [Window00]
section of the panel.cfg file. E.g. another Icon, and check whether their
coordinates corresponds with the postition you would expect on the panel.

To get the correct coordinates for the Groundhandling panel window Icon:
- Observe the main panel in FS2K2, and find a free spot.
- Look for a gauge nearby (e.g. another Icon), find this gauge in the panel.cfg
  file, and use nearby coordinates for the Groundhandling Icon.
Remember:
- 'aaa','bbb' specifies the top-left corner of the Icon.
- Increasing 'aaa' will shift the Icon to the right.
- Increasing 'bbb' will shift the Icon downwards.
- 12,12 (in my example) defines the size of the Icon in pixels, so using 24,24
  makes it twice as large. 
  12,12 is the normal Icon size for panels with a bitmap 640*480 resolution;
  and 16,16 for panels with a 1024*768 pixels.
- Make sure the Icon does not overlap with an existing gauge.

Note: after you edit and saved the panel.cfg file, just reselect the same
aircraft again.


Appendix-2: Used sounds
=======================
The following soundfiles are being used in this package:
- GH01_Conversation1: "Ground from cockpit ....."
- GH02_Conversation2: "Brakes are released. OK pushing back"
- GH03_Conversation3: "Set Parking Brakes"
- GH04_Conversation4: "Parking Brakes are set, prepare aircraft ...."
- GH05_Conversation5: "Brakes are released. OK pushing back. All engines ...."
- GH06_SoftClick:     Click sound, when a pushbutton switch is clicked.
- GH07_Error:         Procedure error sound, when clicking Red-lighted button.
- GH08_PushbackRoll:  Groundroll sound during Pushback.
- GH09_Warning:       Warning sound, when the Taxispeed controller goes from 
                      Armed to Active, or when it is deactivated automatically.
- GH10_Attention:     Attention sound, when Pushback awaits ParkingBrakes action.
- GH11_Brakes:        Brakes sound.



Appendix-3: The "brakes" problem in FS2004
==========================================

For its normal brakes, FS uses a diffential, proportional braking system: 
left and right brakes, pressure dependant.
There are three ways to operate the normal brakes:
- Via the keyboard (or joystick buttons):
  Commands BRAKES (works on left AND right brakes), BRAKES_LEFT, BRAKES_RIGHT.
  As in the default keys: "." "F11" "F12" ; I call them non-proportional.
  When giving these commands repetitively, 100% brake pressure is applied.
- Via toebrake pedals, seperate for Left/Right brakes and proportional with 
  the pedal pressure.
- Controlled from a gauge, either via proportional or non-proportional brake
  commands.

In FS2004 it is possible to define in the aircraft.cfg how the aircraft reacts
to a certain toebrakes pressure, and whether it has Parking brakes or not. Via:
[brakes]
toe_brakes_scale=1.4  //1.4: scalar; 0: brakes don't have any effect.
parking_brake=1       //1: parking brakes available.

The FS2004 brakes problem: 
If FS2004 detects that proportional brakes are used, either from toebrake 
pedals or controlled from a gauge (like my TaxispeedToeBrakes), it disables the
non-proportinal brake commands, meaning that ".", "F11" and "F12" no longer 
work. This is not a problem if you have toebrake pedals, but if you don't,
you're stuck :-)

Note that if you have the registered version of FSUIPC installed, with toebrake 
calibration set in FSUIPC, the problems above are mostly not there; because
FSUIPC interacts with the sim engine directly, implementing it's own way
of emulating "proportional" brakes (the same way it allready did for FS2000).

Hence there are two versions of the Taxispeed gauge:
- TaxispeedToeBrakes: uses the proportional FS brake commands.
  Use this when you use a proportional toebrakes controller.
- TaxispeedNoToeBrakes: uses the non-proportinal (old) brake commands. Use this
  when  you use FS2004 WITHOUT toebrake pedals.

**************************** End Of Document **********************************
