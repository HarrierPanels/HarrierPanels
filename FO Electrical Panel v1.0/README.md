********************************************************************************************************************************
FO Electrical Panel v1.0 for SCS Tu-134 v2.0 FS9/FSX
Microsoft Flight Simulator 2004 / Microsoft Flight Simulator X
********************************************************************************************************************************
© 2019 Harrier Panels. All Rights Reserved.
********************************************************************************************************************************
Tupolev Tu-134 FO Electrical Panel Review: https://youtu.be/8ZVsTMpWzw8
********************************************************************************************************************************

     USER MANUAL
	 
********************************************************************************************************************************

    TABLE OF CONTENTS:
	1. Introduction .................................... Page 1
	2. Installation and Removal ........................ Page 1
	3. Technical Information ........................... Page 3
	4. Instructions of Usage ........................... Page 4
	5. CREDITS ......................................... Page 6
	6. LEGAL ........................................... Page 6


--------------------------------------------------------------------------------------------------------------------------------

        1. Introduction:

--------------------------------------------------------------------------------------------------------------------------------

The update will add a photorealistic 2D Tupolev Tu-134 FO Electrical Panel with fully functioning SPU-7B Interphone Mini Panel 
used to listen to VOR / ADF Morse Code signals and select COM-1 or COM-2 radios for ATC communications. It is also ready for 
using Pushback Panel v3.0.

	SCS Tu-134 v2.0 Features
	
	o SPU-7B Interphone Mini Panel
	o Lights Test button
	o STAB Trim switch

The panel also has Pax Sign switches and other Tu-134 buttons and switches.

IMPORTANT: SCS Tu-134 v2.0 is required and should be installed prior to installing the update.

--------------------------------------------------------------------------------------------------------------------------------

        2. Installation and Removal:

--------------------------------------------------------------------------------------------------------------------------------

        Installation

2.1 To install the panel start the program SETUP.exe. Follow the instructions of the installation program.

--------------------------------------------------------------------------------------------------------------------------------
NOTE: If the installation program is unable to detect your flight simulator folder choose it manually.
--------------------------------------------------------------------------------------------------------------------------------

The program will install the necessary gauges and sounds.

2.2 Choose installed SCS Тu-134 v2.0 aircraft with which you will use the panel.

2.3 Configure SCS Тu-134 Panel.cfg as follows:

a. To install FO Electrical Panel add the line in the section [Window Titles] as follows:

Window**=FO Electrical Panel
   
 ** - a sequence number of the panel window installed in the Instrumental Panel menu;
 
--------------------------------------------------------------------------------------------------------------------------------

b. Add the following string to [Window00] section or any other 2D panel to install the icon:
                               
gauge**=HarrierFOEP1.0!Harrier_FOEP1.0_Icon_Eng,  aaa,bbb,12,12

        ** - a sequence number of the gauge, ааа & bbb - are the coordinates for the 2D panel
        Icon on your aircraft's main panel and 16,16 (or 12,12) is the icon size in pixels;

--------------------------------------------------------------------------------------------------------------------------------
NOTE: Installing the icon is optional. You can install the electrical panel with any sequence number from 1 to 9 (for example, 
Window07, see a.) to call it via Shift + (panel number).
--------------------------------------------------------------------------------------------------------------------------------		

c. Add Electrical Panel window section (see a.) after the last default [WindowXX] section of your aircraft as follows:

//--------------------------------------------------------
[Window**]
Background_color=0,0,0
size_mm=350,1166
windowsize_ratio=0.300  
position=8
visible=0
ident=77733330
window_size= 0.180, 0.958
window_pos= 0.815, 0.03

gauge00=HarrierFOEP1.0!Harrier_FOEP1.0_Tu134_Eng,  1,1,349,1150

     ** - a sequence number of the panel;

--------------------------------------------------------------------------------------------------------------------------------

d. In the [Vcockpit01] section the following string:

gauge**=Harrier_FOEP1.0!sound, 2,2,3,3,./Sound/HarrierFOEPSounds/SCS/HarrierFOEP1.0.ini

        ** is a sequence number of the gauge;
	 
--------------------------------------------------------------------------------------------------------------------------------
NOTE: For SCS Tu-134 v2.0 for FSX it is recommended to set an increased button / switch click sound volume of  by replacing the 
name of the HarrierFSAP3.0.ini file with HarrierFSAP3.0_X.ini (see d.).
--------------------------------------------------------------------------------------------------------------------------------

e. Save your Panel.cfg file;

--------------------------------------------------------------------------------------------------------------------------------

2.4 See 4. Instructions of Usage.

--------------------------------------------------------------------------------------------------------------------------------

            REMOVAL
			
--------------------------------------------------------------------------------------------------------------------------------

2.5 Run UninstallFOEP1.0.exe from within the main FS9/FSX folder or from the Programs Menu.

2.6 Open in the notepad Panel.cfg and follow the steps in the section 2.3 of this manual to delete the entries you added during 
the installation.

2.7 Save your Panel.cfg file.

--------------------------------------------------------------------------------------------------------------------------------

        3. Technical Information:
		
--------------------------------------------------------------------------------------------------------------------------------

3.1 The panel is fully compatible with appropriate SCS Tu-134 v2.0 FS9/FSX mods provided that variable names and logic of the 
electrical system and appropriate equipment used in the FS9 model are kept unchanged!

3.2 FO Electrical Panel has the following clickable switches and buttons: 

	a. Pax Sign switches 'Fasten Seat Belts' and 'No Smoking';

	b. Buttons and switches 'Low Pressure', 'Pressure Boost', 'Left Fuel Gauge', 'Right Fuel Gauge', 'Intermittent Alarm', 'Fan', 
	   'Micron Transceiver';

	c. STAB Trim switch;

--------------------------------------------------------------------------------------------------------------------------------
NOTE: It is not recommended to hold the STAB Trim switch in the upper 'APL NOSE DOWN' or lower 'APL NOSE UP' position for more 
than 15 seconds.
--------------------------------------------------------------------------------------------------------------------------------	

	d. Lights Test button;

--------------------------------------------------------------------------------------------------------------------------------	
	
3.3 The SPU-7B Interphone Mini Panel allows you to listen to VOR / ADF Morse Code signals and select COM-1 or COM-2 radios for 
ATC communications:

	a. Network Switch;
	b. Volume knobs;
	c. Radio Selector Knob has 6 positions: 'VHF-2', 'SW', 'VHF-1', 'SR Nav-2C', 'VOR-1 / ADF-1', 'VOR-2 / ADF-2';
	d. Interphone / Radio Switch;
	e. Circular Call Button;

--------------------------------------------------------------------------------------------------------------------------------

        4. Instructions of Usage:
		
--------------------------------------------------------------------------------------------------------------------------------

4.1 To open / close FO Electrical Panel use either the installed icon or the Shift key combination + the panel sequence number 
from 1 to 9 (see section 2.3 of 2. Installation and Removal).

--------------------------------------------------------------------------------------------------------------------------------
NOTE: To close the panel you can use the Master Volume Control Knob located at the top right of the SPU-7B Interphone Mini Panel
(see section 3.3 of 3. Technical information).
--------------------------------------------------------------------------------------------------------------------------------

4.2 Use the Circular Call Button to open Pushback Panel v3.0 (see  section 3.3 of 3. Technical information).

4.3 To use the SPU-7B Interphone Mini Panel:

	a. Turn on the Interphone power switch at the Navigator Electrical panel;

--------------------------------------------------------------------------------------------------------------------------------
NOTE: The Interphone is powered by the 27V DC bus (main or emergency).
--------------------------------------------------------------------------------------------------------------------------------	
	
	b. To communicate via COM-1 radio turn on the COM-1 power switch located at the Cpt Electrical panel. Set the Radio Selector 
	   knob to 'VHF-1' position. Switch the Interphone / Radio switch to 'Radio' position;	

--------------------------------------------------------------------------------------------------------------------------------
NOTE: COM-1 & COM-2 radios are powered by the 27V DC bus (main or emergency).
--------------------------------------------------------------------------------------------------------------------------------	   

	c. To work with COM-2 radio turn on the COM-2 power switch located at the Cpt Electrical panel. Set the Radio Selector knob 
	   to 'VHF-2' position. Switch the Interphone / Radio switch to 'Radio' position;	
	   
	d. To listen to an audio signal of the NDB beacon which frequency is set in ADF-1 set the Radio Selector knob to 'VOR-1 / 
	   ADF-1' position having previously turned on the ADF-1 power at the Navigator Electrical panel. Switch the Interphone / 
	   Radio switch to 'Radio' position. To stop listening for the signal simply move the Radio Selector knob to any other 
	   position or switch the Interphone / Radio switch to 'Interphone' position;		   

--------------------------------------------------------------------------------------------------------------------------------
NOTE: In a real airplane to stop listening to a beacon signal in addition to switching the Interphone / Radio switch to 
'Interphone' position you will also have to turn down the Secondary Signal Volume to minimum by turning counter clockwise the 
knob located at the top left of the SPU-7B Interphone Mini Panel - not implemented in this panel.
--------------------------------------------------------------------------------------------------------------------------------	   
  
	e. To listen to an audio signal of the NDB beacon which frequency is set in ADF-2 set the Radio Selector knob to 'VOR-2 / 
	   ADF-2' position having previously turned on the ADF-2 power at the Navigator Electrical panel. Switch the Interphone / 
	   Radio switch to 'Radio' position. To stop listening for the signal simply move the Radio Selector knob to any other 
	   position or switch the Interphone / Radio switch to 'Interphone' position;	

--------------------------------------------------------------------------------------------------------------------------------
NOTE: Both ADF-1 and ADF-2 are powered by the 27V DC bus and 36V 400 Hz AC bus. ADF-1 could be powered by 27V emergency power bus 
from the batteries and additionally 36V 400 Hz from the PT-200C AGD converter also powered by emergency power bus.
--------------------------------------------------------------------------------------------------------------------------------
	   
	f. To listen to an audio signal of the VOR station which frequency is set in NAV-1 set the Radio Selector knob to 'VOR-1 / 
	   ADF-1' position having previously turned on the NAV-1 power at the Overhead panel. Switch the Interphone / Radio switch to 
	   'Radio' position. To stop listening for the signal simply move the Radio Selector knob to any other position or switch the Interphone / Radio switch to 'Interphone' position;	

--------------------------------------------------------------------------------------------------------------------------------
NOTE: NAV-1 & BAV-2 are powered by the 27V DC bus and 115V 400 Hz AC bus.
--------------------------------------------------------------------------------------------------------------------------------	   
	   
	g. To listen to an audio signal of the VOR station which frequency is set in NAV-2 set the Radio Selector knob to 'VOR-2 / 
	   ADF-2' position having previously turned on the NAV-2 power at the Overhead panel. Switch the Interphone / Radio switch to 
	   'Radio' position. To stop listening for the signal simply move the Radio Selector knob to any other position or switch the Interphone / Radio switch to 'Interphone' position;	   
   
--------------------------------------------------------------------------------------------------------------------------------
NOTE: You can find more information about Tupolev Tu-134 electrical system and equipment in the aircraft Operations Manual that 
can be downloaded here (2 books in Russian, use Google translator):

https://aviasimulator.blogspot.com/2019/07/tu-134-operation-manual-russian.html
--------------------------------------------------------------------------------------------------------------------------------	   
	   
            6. CREDITS:
           
    Doug Dawson
    Rob Barendregt
	  Heretic
	  mjahn
	  lopast56 
	  cot 
	  61701
	  Ariec 71
	  airomsk 
	  Sergey67 
    Harrier Panels

	
********************************************************************************************************************************

            LEGAL:

This product including all files contained within this package is copyright © Harrier
Panels. The information provided within this document and the package is not
intended for real world aviation. All trademarks and/or logos mentioned and/or
displayed within this package are property of their respective holders and are being
used solely with the purpose of simulating reality.

		NOT FOR COMMERCIAL USE
		
********************************************************************************************************************************

Have a nice flight!

Harrier Panels

--------------------------------------------------------------------------------------------------------------------------------
© 2019 Harrier Panels. All Rights Reserved. E-mail: avsim@inbox.ru
--------------------------------------------------------------------------------------------------------------------------------
Harrier Panels YouTube: https://www.youtube.com/channel/UCWmAfnW6k6fibf7gVd-q2Tg
