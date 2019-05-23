

# Presets
## Installation
To install presets place them in the corresponding folder under presets (for instance /ER-301/v0.4/presets/custom-unit/ for the Custom presets).  

All presets are compatible with firmware 0.4.11
 
* [ad.unit](#ad)
* [ad ext.unit](#ad_exp)
* [ad exp var.unit](#ad_exp_var)
* [gated burst.unit](#gates_burst)
* [gate to trigger.unit](#gate_to_trigger)
* [mono to stereo 1.unit](#mono_to_stereo_1)
* [mono to stereo 2.unit](#mono_to_stereo_2)
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

## 6 Bands
### cheap reverb 1.unit + cheap reverb 2.unit<a name="cheap_reverb_1"></a><a name="cheap_reverb_2"></a>
[![Cheap reverb demo on instagram](pix/cheap_reverb.jpg?raw=true)](https://www.instagram.com/p/BxetV5FhZKT)  
CPU usage: 7.2%  
Room size reverb that doesn't tax the CPU. Works on stereo channel, but is mono in, mono out...
Controls:  
* size (0-1)
