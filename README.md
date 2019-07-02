# Presets
All presets (should be) compatible with firmware 0.4.20  
Discussion thread: https://forum.orthogonaldevices.com/t/a773-presets-unit-files


##### Synth building blocks
* [ad](#ad) - AD envelope
* [ad exp](#ad_exp) - Exponential AD envelope
* [ad exp var](#ad_exp_var) - AD envelope with variable exponential response
* [decay env](#decay_env) - Decay envelope
* [stepped random](#stepped_random)

##### Voices
* [2op-fm](#2op-fm) - Two operator fm voice
* [bass pluck ](#bass_pluck) - Simple plucky bass voice

##### Drums
* [bd1](#bd1) - Decent kick drum
* [bd2](#bd2) - Better kick drum


##### Trigger/gate
* [gated burst](#gates_burst)
* [gate to trigger](#gate_to_trigger)

##### Audio mangling
* [buffer player](#buffer_player)
* [stutter](#stutter)

##### Effects
* [cheap reverb 1](#cheap_reverb_1)
* [cheap reverb 2](#cheap_reverb_2)
* [mono to stereo 1](#mono_to_stereo_1)
* [mono to stereo 2](#mono_to_stereo_2)
* [poor mans reverb 1](#poor_mans_reverb_1)
* [poor mans reverb 2](#poor_mans_reverb_2)
* [tuned resample](#tuned_resample)


## Synth building blocks
### ad <a name="ad"></a>
AD envelope with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 3.3%  
Controls:
* attack (0-5s)
* decay (0-5s)


### ad exp <a name="ad_exp"></a>
AD envelope (exponential response) with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 4.8%  
Controls:
* attack (0-5s)
* decay (0-5s)


### ad exp var<a name="ad_exp_var"></a>
AD envelope (variable exponential response) with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 5.6%  
Controls:
* attack (0-5s)
* decay (0-5s)
* exp (0-1)


### decay env<a name="decay_env"></a>
Very cheap decay envelope with exponential decay. This is just a slew-limiter with feedback (no fancy GUI) to keep it cheap. Adjusting time, might require adjusting the negative gain on the feedback. A bit unstable in a charming way.  
Unit type: slew-limiter  
CPU: 0.24%  
Controls:  
* time: 3ms-786.32s  


### stepped random<a name="stepped_random"></a>
Generte random value on trigger.  
Unit type: mixer-channel  
CPU: 1.95%  
Controls:  
* trigger

## Voices
### 2op-fm<a name="2op-fm"></a>
[![2op-fm demo on instagram](pix/2op-fm.png)](https://www.instagram.com/p/BzLa0WuBjBB)  
Percussive FM voice inspired by [the 2opfm module by Super Synthesis](https://www.supersynthesis.com/products/2opfm?variant=3710980620328)  
Unit type: mixer-channel  
CPU: 8.4%  
Controls:
* v/oct
* ratio (0-1)
* index (0-20)
* release (0-1s)
* gate

### bass pluck<a name="bass_pluck"></a>
Simple plucky bass voice.  
Unit type: mixer-channel  
CPU: 8.4%  
Controls:
* v/oct
* trigger
* release (0-61s)
* feedback (0-1)


## Drums
### bd1<a name="bd1"></a>
No so versatile kick drum.  
Unit type: mixer-channel  
CPU: 8%  
Controls:
* amp rel (amplitude decay time)
* pitch amt (pitch amount)
* pitch rel (amplitude decay time)


### bd2<a name="bd2"></a>
Quite versatile kick drum, with lots of sweet spots.  
Unit type: mixer-channel  
CPU: 10%  
Controls:
* freq 0-1 (frequency env amount)
* decay 0-1s
* feedback 0-1




## Trigger/gate
### gated burst<a name="gated_burst"></a>
![gated burst screenshot](pix/gated_burst.png?raw=true)  
Emits bursts while receiving a gate. The bursts are pulses with intervals of "burst time" and length "burst time/2".  
Unit type: custom-unit  
Controls:  
* burst time: 0-1000 ms  


### gate to trigger<a name="gate_to_trigger"></a>
![gate to trigger screenshot](pix/gate_to_trigger.png?raw=true)  
Converts incomming gates to triggers of selected length.  
Unit type: custom-unit  
Controls:  
* trigger time (1-1000ms)


## Audio mangling
### buffer player<a name="buffer_player"></a>
Grabs audio and play it pitched.  
Unit type: two-bands  
Controls:
* v/oct
* grab
* dry/wet


### stutter<a name="stutter"></a>
Repeats snip of audio on gate high.  
Unit type: custom-unit  
CPU: 7.2%  
Controls:
* clock
* gate
* mult
* div


## Effects
### cheap reverb 1 + 2<a name="cheap_reverb_1"></a><a name="cheap_reverb_2"></a>
[![Cheap reverb demo on instagram](pix/cheap_reverb.jpg?raw=true)](https://www.instagram.com/p/BxetV5FhZKT)  
Unit type: six-bands  
CPU usage: 7.2%  
Room size reverb that doesn't tax the CPU. Works on stereo channel, but is mono in, mono out.  
Controls:
* size (0-1)  


### mono to stereo 1<a name="mono_to_stereo_1"></a>
Delays one channel, very simple/stupid, will flange in mono.  
Unit type: two-bands  
CPU (on stereo channel): 3.2%  
Controls:
* width (0-1)


### mono to stereo 2<a name="mono_to_stereo_2"></a>
More sophisticated (using comb filters), better mono compatibility, but more
expensive on the CPU.  
Unit type: two-bands  
CPU (on stereo channel): 18%  
Controls:
* width (0-1)
* depth (0-1)


### poor mans reverb 1<a name="poor_mans_reverb_1"></a>

[![Poor mans reverb demo on instagram](pix/poor_mans_reverb_1.jpg?raw=true)](https://www.instagram.com/p/BvUDRwlF5Ic)  
Granular reverb based on [Neil Parfitts reverb idea](https://www.youtube.com/watch?v=swXpnqot4-Q), recording with a Dub Looper, with dub controlled by incoming signal.  
Unit type: two-bands  
CPU (mono version on mono channel): ~24%  
CPU (stereo version on stereo channel): ~23%  
Controls:  
* length (10ms-1s): length of grains
* speed (10-500Hz): speed of grains
* scrub (0-1): random scrubbing of playhead
* dry (0-1)
* wet (0-1)


### poor mans reverb 2<a name="poor_mans_reverb_1"></a>
Variation of [poor mans reverb 1](#poor_mans_reverb_1), but recording with a Feedback Looper for a different flavor.  
Unit type: two-bands  
CPU (on stereo channel): ~26%  
Controls:  
* length (0-1s): length of grains
* speed (10-500Hz): speed of grains
* v/oct: pitch of reverb  
* dry (0-1)
* wet (0-1)


### tuned resample<a name="tuned_resample"></a>
Sample rate reduction, with pitch tracking.  
Unit type: Custom Effect  
CPU: 3.6%  
Controls:
* v/oct (0-14400cents)
* offset (0-20000Hz)
