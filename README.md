# Presets
## Custom
### gated burst.unit
![gated burst screenshot](pix/gated_burst.png?raw=true)  
Emits bursts while receiving a gate. The bursts are pulses with intervals of "burst time" and length "burst time/2".

Controls:  
* burst time: 0-1000 ms  


### gate to trigger.unit
![gate to trigger screenshot](pix/gate_to_trigger.png?raw=true)  
Converts incomming gates to triggers of selected length

Controls:  
* trigger time (1-1000ms)

## 2 Bands
### mono to stereo 1.unit
Delays one channel, very simple/stupid, will flange in mono  
CPU (on stereo channel): 3.2%  


### mono to stereo 2.unit
More sophisticated (using comb filters), better mono compatibility, but more
expensive on the CPU  
CPU (on stereo channel): 18%  

## 6 Bands
### cheap reverb 1.unit + cheap reverb 2.unit
[![Cheap reverb demo on instagram](pix/cheap_reverb.jpg?raw=true)](https://www.instagram.com/p/BxetV5FhZKT)  
CPU usage: 7.2%  
Room size reverb that doesn't tax the CPU. Works on stereo channel, but is mono in, mono out...
Controls:  
* size (0-1)
