# User Remote Script for Ableton Live and the Behringer DeepMind 12

## How the script works
The way that this script works requires you to configure your DeepMind 12 to use CC messages in whatever protocol you're connected with (MIDI, USB). 

Within Ableton Live, we will also be using a regular old MIDI setup for our DeepMind 12 to complement the User Control Script (because the script does not support notes except for limited numbers of pads, etc. nor does it support MIDI sync. In this way you can use your keyboard as you would any standard MIDI device, but with the addition of this script also use the DeepMind 12's sliders for the fancy 8 automatic/dynamic parameter changes, and 8 volume controls.

## Controller Mappings (all changeable in `UserConfiguration.txt`)
Setting | Value
--------|------
MIDI Channel | 1
Global CTRL | Cc

You can change this easily to whatever sliders you want by just adding a MIDI Monitor device in live and move a slider on your DM12 to find the CC):

Live Controller | DeepMind 12 Slider | CC #
----------------|--------------------|-----
Encoder 1 | POLY: UNISON DETUNE | 28
Encoder 2 | VCF: FREQ | 29
Encoder 3 | VCF: RES | 30
Encoder 4 | VCF: ENV | 31
Encoder 5 | VCF: LFO | 33
Encoder 6 | VCF: KYBD | 34
Encoder 7 | VCA: LEVEL | 36
Encoder 8 | HPF: FREQ | 35
Volume 1 | LFO2: RATE | 18
Volume 2 | LFO2: DELAY TIME | 19
Volume 3 | OSC 1: PITCH MOD | 20
Volume 4 | OSC 1: PWM | 21
Volume 5 | OSC 1&2: PITCH MOD | 23
Volume 6 | OSC 1&2: TONE MOD | 24
Volume 7 | OSC 1&2: PITCH | 25
Volume 8 | OSC 1&2: LEVEL | 26
Master Volume | OSC 1&2: NOISE LEVEL | 27

# Installation

## 0. Exit Ableton Live if it is running
The enumeration of User Remote Scripts seems to take place on Ableton Live startup, make sure you exit before you continue.

##  1. Setup DeepMind 12 to send MIDI CC
I am using a USB cable to connect my DeepMind 12 to my Windows PC, but you should replace USB SETTINGS with MIDI SETTINGS or WIFI SETTINGS in step 2 with your connection mode.

1. Press GLOBAL button repeatedly until **>>CONNECTIVITY** configuration screen is displayed.
2. Navigate to USB SETTINGS and use +/YES button as ENTER to dive into that screen.
3. For USB-CTRL choose Cc
4. Press GLOBAL button repeatedly until you exit
5. DeepMind 12 is now setup to send CCs (Control Change) messages over USB MIDI cable.

## 2. Install the Control Surface Script into your computers file system
https://help.ableton.com/hc/en-us/articles/206240184-Creating-your-own-Control-Surface-script

### After cloning or downloading this GitHub repo:

#### Copy Behringer DeepMind 12 to your `User Remote Scripts` directory.

The `User Remote Scripts` directory varies depending on the type of computer you have:
- Mac: `HD:/Users/[Username]/Library/Preferences/Ableton/Live x.x.x/User Remote Scripts`
- Windows: `C:\Users\[Username]\AppData\Roaming\Ableton\Live x.x.x\Preferences\User Remote Scripts`

## 3. Start Ableton Live and Configure Control Surface

From **Preferences -> Link Tempo Midi -> Control Surface**:

1. Under MIDI section For Control Surface choose `Behringer DeepMind 12`
2. For Input for the DeepMind 12 Control Surface choose `DeepMind12`
3. For Output for the DeepMind 12 Control Surface choose `DeepMind12`

## 4. Configure Keyboard Controller in Live
1. Under MIDI Ports -> In: Behringer DeepMind 12 Input (DeepMind12) -> [ ] Track
2. Check the Track checkbox (this allows your DeepMind 12 to act like a regular MIDI device in addition to the User Remote Script for the fancy sliders)
3. Under MIDI Ports -> Out: Behringer DeepMind 12 Output (DeepMind12) -> [ ] Sync
4. Check the Sync checkbox (this is optional but will let you sync your DM12 ARP to Lives tempo)

# Test
1. Drag a preset from Live Browser in Categories -> Sound onto a MIDI track
2. Observe that the little hand icon exists after the preset name on the device rack
3. Move POLY: UNISON DETUNE slider on DM12
4. Watch Parameter 1 value change on the device rack
