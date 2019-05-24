

# Presets
## Installation
To install presets place them in the corresponding folder under presets (for instance /ER-301/v0.4/presets/custom-unit/ for the Custom presets).  

All presets are compatible with firmware 0.4.11
 
* [ad.unit](#ad)
* [ad ext.unit](#ad_exp)
* [ad exp var.unit](#ad_exp_var)
* [gated burst.unit](#gates_burst)
* [gate to trigger.unit](#gate_to_trigger)
* [buffer player.unit](#buffer_player)
* [mono to stereo 1.unit](#mono_to_stereo_1)
* [mono to stereo 2.unit](#mono_to_stereo_2)
* [poor mans reverb 1.unit](#poor_mans_reverb_1)
* [poor mans reverb 2.unit](#poor_mans_reverb_2)
* [cheap reverb 1.unit](#cheap_reverb_1)
* [cheap reverb 2.unit](#cheap_reverb_2)


## Custom
### ad.unit <a name="ad"></a>
AD envelope with variable attack and decay, works with short triggers as input.  
CPU: 3.3%  
Controls:
* attack (0-5s)
* decay (0-5s)

### ad exp.unit <a name="ad_exp"></a>
AD envelope with variable attac
AD envelope (exponential response) with variable attack and decay, works with short triggers as input.  
CPU: 4.8%  
Controls:
* attack (0-5s)
* decay (0-5s)

### ad exp var.unit<a name="ad_exp_var"></a>
AD envelope with variable attac
AD envelope (variable exponential response) with variable attack and decay, works with short triggers as input.  
CPU: 5.6%  
Controls:
* attack (0-5s)
* decay (0-5s)
* exp (0-1)

### gated burst.unit<a name="gated_burst"></a>
![gated burst screenshot](pix/gated_burst.png?raw=true)  
Emits bursts while receiving a gate. The bursts are pulses with intervals of "burst time" and length "burst time/2".

Controls:  
* burst time: 0-1000 ms  


### gate to trigger.unit<a name="gate_to_trigger"></a>
![gate to trigger screenshot](pix/gate_to_trigger.png?raw=true)  
Converts incomming gates to triggers of selected length

Controls:  
* trigger time (1-1000ms)

## 2 Bands
### buffer player.unit<a name="buffer_player"></a>
Grabs audio and play it pitched
Controls:
* v/oct
* grab
* dry/wet

### mono to stereo 1.unit<a name="mono_to_stereo_1"></a>
Delays one channel, very simple/stupid, will flange in mono  
CPU (on stereo channel): 3.2%  
Controls:
* width (0-1)

### mono to stereo 2.unit<a name="mono_to_stereo_2"></a>
More sophisticated (using comb filters), better mono compatibility, but more
expensive on the CPU  
CPU (on stereo channel): 18%  
Controls:
* width (0-1)
* depth (0-1)

### poor mans reverb 1.unit<a name="poor_mans_reverb_1"></a>
[![Poor mans reverb demo on instagram](pix/poor_mans_reverb_1.jpg?raw=true)](https://www.instagram.com/p/BvUDRwlF5Ic)  
Granular reverb based on [Neil Parfitts reverb idea](https://www.youtube.com/watch?v=swXpnqot4-Q), recording with a Dub Looper, with dub controlled by incoming signal.  
CPU (mono version on mono channel): ~24%  
CPU (stereo version on stereo channel): ~23%  
Controls:  
* length (10ms-1s): length of grains
* speed (10-500Hz): speed of grains
* scrub (0-1): random scrubbing of playhead
* dry (0-1)
* wet (0-1)

### poor mans reverb 2.unit<a name="poor_mans_reverb_1"></a>
Variation of [poor mans reverb 1.unit](#poor_mans_reverb_1), but recording with a Feedback Looper for a different flavor.  
CPU (mono version on mono channel): ~20%  
CPU (stereo version on stereo channel): ~26%  
Controls:  
* length (0-1s): length of grains
* speed (10-500Hz): speed of grains
* dry (0-1)
* wet (0-1)


## 6 Bands
### cheap reverb 1.unit + cheap reverb 2.unit<a name="cheap_reverb_1"></a><a name="cheap_reverb_2"></a>
[![Cheap reverb demo on instagram](pix/cheap_reverb.jpg?raw=true)](https://www.instagram.com/p/BxetV5FhZKT)  
CPU usage: 7.2%  
Room size reverb that doesn't tax the CPU. Works on stereo channel, but is mono in, mono out...
Controls:  
* size (0-1)
