****************************************************************************************************
Pushback Panel v3.0
Microsoft Flight Simulator 2004 / Microsoft Flight Simulator X / Lockheed Martin Prepar3D
****************************************************************************************************
© 2019 Harrier Panels. All Rights Reserved.
****************************************************************************************************
SEE THE PANEL REVIEW: https://youtu.be/_DCAzLg-w2k
****************************************************************************************************
     USER MANUAL
****************************************************************************************************

    TABLE OF CONTENTS:
    1. Introduction ..................................... Page 1
    2. Installation and Removal ......................... Page 1
    3. Technical Information ............................ Page 7
    4. Instructions of Usage ............................ Page 7
    5. Changelog ........................................ Page 8
    6. CREDITS .......................................... Page 9
    7. LEGAL ...................................... Back Cover 1


--------------------------------------------------------------------------------------------------------------------------------
        1. Introduction:

--------------------------------------------------------------------------------------------------------------------------------

Planning an international flight to Eastern Europe or Russia? Version 3.0 has Pushback Truck Switch Panel that
makes it possible to choose between English and Russian groundcrew to use both in one flight. You can still use
a standalone panel either English or Russian like in versions v1.0 and v2.0. Includes Brake Sound FX. Supports FS9, 
FSX, and all versions of P3D including v4.0 and later. Based on Groundhandling gauges by Rob Barendregt and Doug 
Dawson's XML Sound Gauge. The panel is intended for aircraft Pushback procedures. NOTE: Before installing the 
version v3.0 it's recommended to remove all previous versions of the Pushback Panel

--------------------------------------------------------------------------------------------------------------------------------

        2. Installation and Removal:

--------------------------------------------------------------------------------------------------------------------------------
        Installation
--------------------------------------------------------------------------------------------------------------------------------
NOTE: Before installing Pushback Panel v3.0 uninstall all previous versions of the Pushback Panel
--------------------------------------------------------------------------------------------------------------------------------

2.1 To install the panel start the program SETUP.exe. Choose either option FS9/FSX/P3D2/P3D3 or P3D4 (and later). 
Follow the instructions of the installation program

--------------------------------------------------------------------------------------------------------------------------------
NOTE: If the installation program is unable to detect your flight simulator folder choose it manually
--------------------------------------------------------------------------------------------------------------------------------

The program will install the necessary gauges and sounds

--------------------------------------------------------------------------------------------------------------------------------
NOTE: If you want to use a standalone panel (no switch panel) skip to 2.4
--------------------------------------------------------------------------------------------------------------------------------

2.2 Choose an aircraft this panel will be used with

2.3 Configure the panel.cfg of your aircraft as follows:

a. In the section [Window Titles] add the 3 lines

Window**=Pushback Truck Panel v3.0
Window**=Pushback Panel v3.0
Window**=Pushback Panel v3.0 Rus
   
 ** - a sequence number of the panels installed in the Instrumental Panel menu
--------------------------------------------------------------------------------------------------------------------------------

b. Add the following string to [Window00] section:
                               
gauge**=Harrier_pushback3!HarrierIcon_pb,  aaa,bbb,12,12

        ** - a sequence number of the gauge, ааа & bbb - are the coordinates for the Pushback Truck Switch Panel
        Icon on your aircraft's main panel and 16,16 (or 12,12) is the icon size in pixels
--------------------------------------------------------------------------------------------------------------------------------
For P3D4 Airbus A319 by Aerosoft:

// Aerosoft Airbus A319 - the icon is placed at the MCDU panel
[Window01]
file=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/MCDUIMG.bmp
file_1024_night=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/MCDUIMG_NIGHT.bmp
Background_color=0,0,0
size_mm=430,726
visible=0
ident=10021
window_size= 0.290, 0.750
window_pos= 0.000, 0.250

gauge00=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/DLLs/FMGS!FMGS1,  66,44,299,291, 2
gauge01=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK2L,  7,136,32,16,25
gauge02=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK3L,  5,173,33,18,25
gauge03=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK4L,  7,210,32,18,24
gauge04=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK1L,  7,98,32,18
gauge05=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!CLR,  349,671,33,32
gauge06=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!A,  173,454,32,32
gauge07=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!B,  217,455,33,31
gauge08=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!C,  260,455,32,31
gauge09=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!D,  305,456,31,30
gauge10=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!E,  348,455,32,32
gauge11=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!F,  172,498,34,32
gauge12=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!H,  260,498,34,32
gauge13=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!I,  305,497,32,32
gauge14=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!J,  349,  497 ,32,32
gauge15=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!K,  173,542,32,30
gauge16=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!L,  217,541,32,30
gauge17=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!M,  261,542,32,30
gauge18=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!N,  305,541,30,30
gauge19=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!O,  348,542,34,32
gauge20=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!P,  174,585,30,31
gauge21=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!Q,  218,583,30,31
gauge22=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!R,  262,586,29,30
gauge23=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!S,  305,585,31,32
gauge24=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!T,  349,586,33,29
gauge25=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!U,  173,628,32,31
gauge26=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!V,  217,628,33,32
gauge27=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!W,  261,628,31,30
gauge28=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!X,  305,627,31,31
gauge29=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!Y,  349,627,32,33
gauge30=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!Z,  173,671,33,32
gauge31=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!G,  216,497,33,32
gauge32=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!SP,  261,673,32,29
gauge33=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK5L,  6,243,33,21
gauge34=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK6L,  6,283,31,19
gauge35=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK1R,  392,99,33,20
gauge36=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK2R,  392,136,32,16
gauge37=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK3R,  392,172,31,16
gauge38=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK4R,  392,209,30,17
gauge39=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK5R,  392,244,31,19
gauge40=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!LSK6R,  392,284,30,17
gauge41=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!0,  89,676,27,25
gauge42=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!1,  49,564,25,27
gauge43=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!2,  89,563,25,27
gauge44=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!3,  130,563,25,26
gauge45=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!4,  48,601,27,27
gauge46=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!5,  89,601,26,27
gauge47=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!6,  130,601,25,25
gauge48=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!7,  49,638,25,28
gauge49=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!8,  90,637,24,27
gauge50=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!9,  129,637,27,27
gauge51=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!SL,  218,672,29,30
gauge52=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!ST,  48,674,27,28
gauge53=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!SGN,  129,675,27,27
gauge54=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!RAD,  102,401,40,30
gauge55=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!BRT,  361,369,31,25
gauge56=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!DIM,  361,405,31,23
gauge57=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!MENU_key,  304,402,41,30
gauge58=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!ARPRT_key,  52,438,39,28
gauge59=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!DATA_key,  254,364,39,32
gauge60=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!INIT_key,  203,364,39,31
gauge61=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!PERF_key,  153,364,41,31
gauge62=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!PROG_key,  102,366,40,27
gauge63=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!DIR_key,  51,365,41,29
gauge64=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!SPLN_key,  202,402,41,28
gauge65=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!FUEL_key,  152,402,41,28
gauge66=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!FPLN_key,  52,401,39,29
gauge67=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!arrowdn,  102,514,41,29
gauge68=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!arrowleft,  52,477,39,27
gauge69=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!arrowright,  52,514,40,27
gauge70=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!arrowup,  102,476,41,28
gauge71=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!ATC_key,  253,401,41,29
gauge72=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!KBD,  17,500,16,102
gauge73=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!TOGGLE,  394,499,16,103
gauge74=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!OVFY,  305,671,33,32
gauge75=../../Aerosoft A318-A319 Professional Base/Panel_Fallback/KeysSEL!TOGGLE,  377,6,24,24
gauge76=Harrier_pushback3!HarrierIcon_pb,  410,70,12,12

--------------------------------------------------------------------------------------------------------------------------------   
c. Add new window sections (see a.) after the last default [WindowXX] section of your aircraft:

//--------------------------------------------------------
[Window**]
Background_color=16,16,16
size_mm=82,70
windowsize_ratio=1.000 
position=7
visible=0
ident=7777777
window_size= 0.052, 0.070
window_pos= 0.070, 0.231

gauge00=Harrier_pushback3!Harrier_PB3.0,  0,0
gauge01=Harrier_Sound_PBTruck3.0!sound,  2,2,3,3,./Sound/HarrierPushback3/PBTtruck/Sound.ini
gauge02=Harrier_pushback3!BrakeSound, 0,0

//--------------------------------------------------------
[Window**]
Background_color=16,16,16
size_mm=82,103
windowsize_ratio=1.000 
position=7
visible=0
ident=77777771
window_size= 0.052, 0.093
window_pos= 0.070, 0.300

gauge00=Harrier_pushback3!Harrier_pb,  0,0
gauge01=Harrier_pushback3!Harrier_pb_Switch,  50,5,28,32
gauge02=Harrier_pushback3!PushbackDisplay,  4,39,74,61
gauge03=Harrier_pushback3!PushbackStates,  0,0
gauge04=Harrier_Sound!sound,  2,2,3,3,./Sound/HarrierPushback3/ENG/Sound.ini

//--------------------------------------------------------
[Window**]
Background_color=16,16,16
size_mm=82,103
windowsize_ratio=1.000 
position=7
visible=0
ident=77777772
window_size= 0.052, 0.093
window_pos= 0.070, 0.300

gauge00=Harrier_pushback3!Harrier_pb_Ru,  0,0
gauge01=Harrier_pushback3!Harrier_pb_Switch_Ru_En,  50,5,28,32
gauge02=Harrier_pushback3!PushbackDisplay_Ru_En,  4,39,74,61
gauge03=Harrier_pushback3!PushbackStates_Ru,  0,0
gauge04=Harrier_Sound_Ru!sound,  2,2,3,3,./Sound/HarrierPushback3/RUS/Sound.ini

     ** - a sequence number of the panels
     
--------------------------------------------------------------------------------------------------------------------------------
NOTE: If you are using the Pushback Panel together with FS Announcement Panel v3.0 or FSPassengers you may wish to disable
the Brake Sound FX as these programs have their own to avoid overlapping the sounds. If needed do it like this:

//gauge02=Harrier_pushback3!BrakeSound, 0,0

--------------------------------------------------------------------------------------------------------------------------------
   
d. Save your panel.cfg file

2.4 To use a standalone panel (no switch panel) choose an aircraft this panel will be used with

2.5 Configure the panel.cfg of your aircraft as follows:

a. In the section [Window Titles] add the line:

Window**=Pushback Panel v3.0
   
 ** - a sequence number of the panels installed in the Instrumental Panel menu
--------------------------------------------------------------------------------------------------------------------------------

b. Add the following string to [Window00] section:
                               
gauge**=Harrier_pushback3!HarrierIcon_pb_En,  aaa,bbb,12,12

        ** - a sequence number of the gauge, ааа & bbb - are the coordinates for the Pushback Panel Icon on your
        aircraft's main panel and 16,16 (or 12,12) is the icon size in pixels
--------------------------------------------------------------------------------------------------------------------------------   
c. Add new window sections (see 2.5.a.) after the last default [WindowXX] section of your aircraft:

//--------------------------------------------------------
[Window**]
Background_color=16,16,16
size_mm=82,103
windowsize_ratio=1.000 
position=7
visible=0
ident=7777777
window_size= 0.052, 0.093
window_pos= 0.070, 0.300

gauge00=Harrier_pushback3!Harrier_pb,  0,0
gauge01=Harrier_pushback3!Harrier_pb_Switch_En,  50,5,28,32
gauge02=Harrier_pushback3!PushbackDisplay,  4,39,74,61
gauge03=Harrier_pushback3!PushbackStates,  0,0
gauge04=Harrier_Sound!sound,  2,2,3,3,./Sound/HarrierPushback3/ENG/Sound.ini
gauge05=Harrier_Sound_PBTruck3.0!sound,  2,2,3,3,./Sound/HarrierPushback3/PBTtruck/Sound.ini
gauge06=Harrier_pushback3!BrakeSound, 0,0

     ** - a sequence number of the panel
     
--------------------------------------------------------------------------------------------------------------------------------
NOTE: If needed you can disable the Brake Sound FX like this:

//gauge06=Harrier_pushback3!BrakeSound, 0,0

--------------------------------------------------------------------------------------------------------------------------------

d. Save your panel.cfg file

2.6 See 4. Instructions of Usage

--------------------------------------------------------------------------------------------------------------------------------
            REMOVAL
--------------------------------------------------------------------------------------------------------------------------------
2.7 Run UninstallPB30.exe or UninstallPB30P3D4.exe from within the main FS9/FSX/P3D folder or from the Programs Menu

2.8 Open in the notepad the panel.cfg file of the aircraft you used Pushback Panel v3.0 with

a. Follow the steps in the 2.3 or 2.4 section of this manual to delete the entries you added during the installation

b. Save your Panel.cfg file

--------------------------------------------------------------------------------------------------------------------------------
        3. Technical Information:
--------------------------------------------------------------------------------------------------------------------------------
3.1 Pushback Truck Switch Panel by Harrier Panels

a. Allows to choose between English and Russian groundcrew and use both in one flight
b. Has an OFF button to switch the panel off after the pushback is started

3.2 Pushback Gauges of the by Rob Barendregt (Groundhandling v4.0)

a. Include advanced setup of the desired distance (in meters) for pushing straight back and the angle of turn (in degrees)

--------------------------------------------------------------------------------------------------------------------------------
NOTE: In P3D4 it has been noticed the 'Pushback truck' uses a bigger radius to turn the aircraft so it's recommended to shorten
the desired distance
--------------------------------------------------------------------------------------------------------------------------------
 
b. Use a standard FS9/FSX Pushback mechanism so you can hear the engine/environment sounds
c. It's possible to change views or PAUSE the simulator during Pushback
d. Control cockpit/groundcrew dialogs. The Pushback is done either with engines off or running. The engines could be also started 
during the Pushback
e. Brake Sound FX gauge will trigger a sound when the aircraft is on the ground, the brake pressure is more than 20% and the
ground speed is over 5 knots
--------------------------------------------------------------------------------------------------------------------------------
        4. Instructions of Usage:
--------------------------------------------------------------------------------------------------------------------------------

a. Before starting Pushback make sure that the parking Brake is set

b. To display/hide the Pushback Truck / Pushback Panel window click on the icon installed on your aircraft's main panel

c. Choose English or Russian groundcrew by clicking on the switch button (En / Ru) then click on the Pushback Truck image to open 
the Pushback Panel. After the Pushback is started you can turn the panels OFF by clicking on OFF buttons (see 3.)

d. Set the desired Distance (in meters). Click to increment or decrement the value. When the Parking Brake is released the counter
(0 - 999 meters, the right 3 digits) starts counting down until 0 followed by making a turn clockwise/counter clockwise (if selected)

--------------------------------------------------------------------------------------------------------------------------------
NOTE: When the Pushback is active (GREEN light) the Counter values can't be changed however the Pushback can be aborted any time
--------------------------------------------------------------------------------------------------------------------------------

e. Set the Angle of Turn

- Turn selector
Toggles between pushing straight back and left or right turn. When the Left or Right turn is selected, the Turn counter is set 
to 90 degrees
- Turn Counter
The counter (0 - 90 degrees, left two digits) determines the angle of the Turn. Click to increment or decrement the value

--------------------------------------------------------------------------------------------------------------------------------
NOTE: 'Turning Left or Right' means turning the tail Left or Right
--------------------------------------------------------------------------------------------------------------------------------
f. Activate the Pushback procedure by clicking the Pushback button. The GREEN light starts flashing. Once the pushback is done 
the light goes off

PUSHBACK: The button has an indicator that changes the backlight depending on the situation
RED: Pushback cannot be started; make sure the Parking Brake is set and the aircraft is not moving
NO LIGHT: Click to start the Pushback
FLASHING GREEN: Waiting for the Parking Brake to be released
GREEN: Pushback started
FLASHING YELLOW: Waiting for the Parking Brake to be set
YELLOW: End of the Pushback

g. To switch the Pushback Panel off press the OFF button on the panel. To switch the Pushback Truck Switch Panel OFF press the OFF
button on the panel or click on the Pushback Icon on your aircraft's main panel

--------------------------------------------------------------------------------------------------------------------------------
        5. Changelog:
--------------------------------------------------------------------------------------------------------------------------------

[3.0] - Jan 2019
Added
- Pushback Truck Switch Panel
- Missing sounds
- New bitmaps

Updated
- Doug Dawson's XML Sound Gauge
- Rob Barendregt's Pushback gauges to enable using both English and Russian ground crewpacks in one flight
- Sounds (added delays in dialogs) and other FX
- Manual

Changed
- English ground crewpack (new one is by Alain Capt)

[2.0] - Dec 2005
Changed
- Pushback mechanism

Added
- English ground crewpack (English version)
- Brake Sound FX

[1.0] - Oct 2005
Updated
- Manual

[1.0] - Oct 2005
Released
- Russian version

******************************************************************************************************************************
            6. CREDITS:
           
    Rob Barendregt
    Doug Dawson
    Alain Capt
	  FPDA Group
    Harrier Panels

******************************************************************************************************************************

            LEGAL:

This product including all files contained within this package is copyright © Harrier
Panels. The information provided within this document and the package is not
intended for real world aviation. All trademarks and/or logos mentioned and/or
displayed within this package are property of their respective holders and are being
used solely with the purpose of simulating reality

		NOT FOR COMMERCIAL USE
		
******************************************************************************************************************************

Have a nice flight!

Harrier Panels

--------------------------------------------------------------------------------------------------------------------------------
© 2019 Harrier Panels. All Rights Reserved. E-mail: avsim@inbox.ru
--------------------------------------------------------------------------------------------------------------------------------
Harrier Panels YouTube: https://www.youtube.com/channel/UCWmAfnW6k6fibf7gVd-q2Tg
