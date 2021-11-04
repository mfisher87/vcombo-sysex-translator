# V-Combo SysEx Translator

Frustrated that your brand new keyboard doesn't work as a MIDI controller the way you'd expect it to? Use this plugin to translate MIDI SysEx messages output by Roland V-Combo keyboards to MIDI CC messages that are usable for controlling other plugins.

Tested on VR-730, but should work on VR-09 or VR-09B. If you've tested this plugin with any other devices and have found it works, please open a pull request to update the compatibility list.


# Installing

Load the plugin file in Reaper or a standalone JSFX runtime of your choice. [Read more on JSFX!](https://www.cockos.com/jsfx/)

Use this plugin on a track listening to the MIDI output from your keyboard.


# Using with a VR-730

I recommend setting up your keyboard with a new registration in which both an Organ and a Piano instrument are active in layered mode (press Organ + Piano buttons at the same time), and the "level" for both instruments is set to 0. This enables you to use the Rhythm feature on the V-Combo. Note that the expression pedal will control the volume of the Rhythm feature, and I haven't found a way around this.


## Why Organ and Piano at the same time?

If you are in Organ mode, drawbars will output the messages we need in values from 0-8 (scaled by this plugin to 0-127), but all note velocities will be sent as 127. 

If you are in Piano or Synth mode, only _some_ drawbars work (the ones that operate as synth controls, e.g. cutoff and resonance) and will output the full 0-127 range of values for the working faders. But in Piano or Synth mode, you _do_ get correct note velocity!

To sum up: to get _both_ correct note velocity _and_ all drawbar controls (at the expense of full 0-127 fader resolution), you need to be in Organ and Piano mode at the same time. 😅


# MIDI Mapping

* 9 Drawbars: MIDI CC 12-20
* 5 Knobs ("Reverb" not working yet):
    * "Overdrive": MIDI CC 75
    * "Tone": MIDI CC 76
    * "Compressor": MIDI CC 77
    * "MFX": MIDI CC 78
    * "Delay": MIDI CC 79
