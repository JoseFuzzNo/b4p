#B4P

B4P is a PureData abstraction library that emulates the behavior of modular synthesizers. B4P is made with [Pd-L2Ork](https://github.com/pd-l2ork/pd) distribution of PureData.

INSTALL
-------
Download the project or clone with git:
    
    git clone https://github.com/JoseFuzzNo/b4p
    
Add the folder to the path in *File > Path...* and restart Pd-L2Ork.

USAGE
-----
The abstractions on B4P are emulations of certain modules. All the basic modules are implemented (VCO, VCF, VCA, ADSR...). The next module is a Voltage Controlled Oscillator. It has four CV inputs, a PWM input and a sync input:

![[b4p_vco]](https://s9.postimg.org/yn0yda8cv/vco.png)


All modules work with audio signals from -5 to 5 "volts". Control signals are usually from 0 to 5 "volts". As in modular synthesizers, control signals can be used to make sound and biceversa.

The next example shows an LFO controlling a VCO:

![LFO controlling VCO](https://s13.postimg.org/hgytctvk7/lfo_vco.png)

And of course, a VCO can control another VCO in order to make FM synthesis:

![FM synthesis](https://s13.postimg.org/ug0e5z2mv/image.png)

DAISY CHAIN
-----------
Some of the modules have the capability to control other modules of his type. This makes easy to make polyphonic synthesizers.

![Daisy chaining modules](https://s17.postimg.org/wv32jycj3/daisy_chain.png)

Only the modules with the dot input/output have this capability.

PRESETS
-------
It is possible to save the state of all B4P object in a patch with the [b4p_preset] object:

![Presets](https://s17.postimg.org/ozq54vvzj/preset.png)

*NOTE:* It is necesary to connect this object to a [preset_hub b4p] object.

EXAMPLES
--------
There are two examples in the *b4p/examples* folder.
- **sequencer**: is a simple example that make use of the [b4p_sequencer] object and adds the output to an LFO. This signal is used to control a monophonic voice.
- **polyphonic_synth**: is an example of a polyphonic synth with four simple voices and a state saving mechanism made with a [b4p_preset] object.