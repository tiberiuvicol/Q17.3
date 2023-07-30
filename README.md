# Q17.3 - more than an audiophile approach to perfect sound


Q17 is a class B amplifier based on current dumping principle.<br>
Please refer to <a href="https://github.com/tiberiuvicol/Q17-audiophile-amplifier/blob/main/Project%20description.pdf">Project description.pdf</a> for project description.<br>
Use KiCad 6, or later, to open and edit source files.  KiCad 6 can be downloaded from CERN, https://www.kicad.org<br>
<b>LTSpice</b> - contain simulation asc file<br>
<b>Q17.7z</b> - <a href="https://forum.kicad.info/t/simulation-examples-for-kicad-eeschema-ngspice/34443">ngspice simulation</a> files for Q17. This will run directly in KiCad. Thank you, Holger Vogt !<br>
<b>KiCad source PS</b> - active rectification power supply KiCad source files<br>
<b>KiCad source</b> - Q17 amplifier KiCad source files<br>
<b>Q17_2final</b> - Q17 amplifier KiCad source files for dual output stage<br>
<b>Q17.pdf</b> - detailed presentation - bill of materials included<br>
<b>gerber-ps.zip</b> - production gerber for PCB active rectification power supply<br>
<b>Q17-Gerber.zip</b> - production gerber for Q17 amplifier with single output pair<br>
<a href="https://github.com/tiberiuvicol/Q17-audiophile-amplifier/blob/main/Q17-gerber-2pair.zip"><b>Q17-gerber-2pair.zip</b></a> - production gerber files for Q17 with dual output pair stage<br>
<b>Q17_dimensions.pdf</b> - PDf file with most important PCB dimensions<br>
Important ! - Amplifier is more stable with R32=0ohm

![image](https://user-images.githubusercontent.com/22703498/204741124-c71b839e-7155-4760-a948-c88b66c404e3.png)

<br>
Click & Order your Q17 with dual output pair PCB @ <a href="https://www.pcbway.com/project/shareproject/Q17__a_QUAD405_audiophile_approach.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a><br>
Purchase parts (for one channel) with one click from mouser ->> https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=1f37a45393 <br>
For STEREO or MULTICHANNEL multiply the order with the same parts. <br>
<br>
<br>
<b>Q&A collected from mail</b><br>
<br>
Q: Why no dc blocking input capacitor?<br>
A: <i>Please consider that Q17 first stage make use of an operational that have a C7=1uF capacitor in negative loop. <br>
This already make a dc block and we have a non polar capacitor C2&C22 in dc servo as well.<br>
On other hand, if there is any dc at amplifier input, you should look on your audio source and eliminate it. Do not try to “solve” previous stage problems by "playing safe" at the amplifier input.</i><br>
<br>
<br>
Q: Why no voltage/ESD input protection ?<br>
A: <i>A voltage/ESD can be made by using zener or reverse polarised diodes. The issue with this approach is that any reverse polarised p/n junction (diode etc) will have high parasitic capacitance modulated by voltage and this highly degrade amplifier performance. How to work around this ? Use a good R-2R Volume Controller with constant output impedance.</i><br>
<br>
<br>
Q: Any amplifier need input LPF, otherwise EMI will affect SNR.  Q17 do not have one, therefore it is poorly designed. Why Q17 do not have input LPF?<br>
A: <i>Please do not generalise. The world is not black and white.The role of LPF is to block any unwanted frequencies to enter in amplifier. <br>
A LPF must be designed such way that will not be affected by input impedance. This is not the case with a potentiometer. Does not matter how good this potentiometer is, his attenuation will affect LPF and therefore amplifier bandwidth. This is very audible at low level volume.<br>
The classic way on how a potentiometer is implemented, is that he offer constant input impedance and variable output impedance toward amplifier input. The down side is that, even you go for a high input impedance, at low audio levels input LPF will reach audio band affecting amplifier bandwidth. This is translated in poor audio performance at low audio levels.<br>
This issue was addressed in Maya volume controller that make use of an R-2R resistive network allowing constant output impedance with high input variable impedance.<br>
Beside this, input cable parasitic capacitance together with high amplifier impedance is enough to form a HF-LPF. Output operational LPF at ~125KHz will clean any noise further.</i><br>
<br>
<br>
Q: Could you please recommend me a potentiometer ?<br>
A: <i>Best attenuator will be a R-2R one with constant output impedance. If you want to go cheap please use a 50K log ALPS.</i>
<br>
<br>
Q: Why there is no super diode ?<br>
A: <i>A super diode is usually made with a BJT, where his Vbe variation with temperatures is used to adjust output stage bias. Unfortunately this is highly nonlinear and will modulate, with Vcb voltage (again reverse polarised p/n junction), output stage bias. While this is very efficient, will highly degrade audio performance. My preference is to have plain and simple resistors, with no capacitor decoupling between output mosfet gates.</i><br>
<br>
<br>
Q: What about transitory power ON/OFF ? <br>
A: <i>For this there are Q13&Q14. These have double role.<br>
One is to ensure soft start and soft power off using RC made with R29C13 and R30C14. <br>
This can be seen at amplifier turn on, D1 & D4 will light after ~1s.<br>
Second role for Q13&Q14 is to act as super-capacitors, ensuring smooth power supply for class A and input stage.</i><br>
<br>
<br>
Q: Why no protection zeners on all mosfets ?<br>
A: <i>Some mosfets need Vgs protection while other do not need.<br>
Let’s start with ones that do not need and later the ones that may need.<br>
Q1 and Q4 are part of regulators and Vgs is already limited by 18V zeners.<br>
Q8 is part of cascode and his Vgs is already limited by positive zener regulator to 18V. You may say it is high, but Q8 source is already lifted above ground by Q7.<br>
Q9 and Q11 are part of current mirror. Q9’s Vgs is limited by Q10 + Vbe and Q10 by Q9 Vgs + VR3. This will not exceed 4V.<br>
Q5 Vgs is also limited by Q9 Vds + VR3. Where Q9 Vds = Q10 Vgs. Therefore, mirror with Q9&Q10 act as Vgs limiter for Q5.<br>
Q6 may need a zener to limit his Vgs due during a transitory turn on his Vgs may be higher, but for a soft turn on there are Q13&Q14.<br>
Q13&Q14 obviously need Vgs limiters because at power on, while C13&C14 are charging, Vgs will be above 45V. For such reason there are zener D4&D5, limiting Vgs to a value that keep Q13&Q14 on safe side.<br>
Q15&Q16&Q17&Q18 are output transistors that may need protection zener. These are high transconductance mosfets that indeed will deliver very high transitory currents. Here the man advantage is that we are running these in class B with very low bias current. Turn on/off transitory is also softened by Q13&Q14 trough class A stage made with Q5&Q6.<br>
On other hand, I prefer to run output stage without protection zener, due any zener internal parasitic capacitance is modulated with voltage. Any reverse biased diode act like a varicap. This is translated in muddy highs.</i><br>
<br>
<br>
Q: Why no output inductor ?<br>
A: <i>This is a highly debatable question.<br>
I’m a nerd audiophile. I like good sound more than “playing safe”.<br>
However, your speaker cables have already an important inductance and parasitic capacitance that must considered. <br>
In some particular cases adding an output inductor may be needed, but these are very … few particular ones.<br>
To be short, Q17 with no coil sound better.</i><br>
<br>
<br>
Q: May I use Lateral MOSFET's in ouput stage ?<br>
A: <i>No, you do not, the PCB was designed for Vertical MOSFET. Lateral mosfet transistor's have different piout than Vertical MOSFET.<br>
  PCB need to be redesigned to accomodate Lateral's, for both Class A and output Class B stage.
  Laterals have lower Vgsth than Verticals, hence for laterals, R11 and R12 must be between 9.1 and 10 ohm.</i><br>
<br>
<br>
Q: Why no embedded protection in your schematic ?<br>
A: <i>This again due sound quality. There is always a trade between playing safe and having best sound.<br>
I like to have best sound even I do not play safe and currently market offer a wide range of speaker protection modules.<br>
Simplest protection would be to use a fast fuse (3A-5A) at amplifier output.</i><br>
<br>
<br>
Q: How much capacitance I may put in power supply ?<br>
A: <i>This is related to your power transformer. A huge capacitance must be charged to be efficient.  For a transformer with 3A in secondary, I would say 20mF per rail is enough.</i><br>
<br>
<br>
Q: Is there any sound difference between a normal bridge and Saligny synchronous rectifiers ?<br>
A: <i>Yes, Saligny rectifiers are far superior and bring important sonic improvement.</i>
<br>
<br>
Q: It is Q17 quiet ?<br>
A: <i>Yes it is. No fass no buzz, even with high SPL speakers >95dBm.</i><br>
<br>
<br>
Q: May you recommend a transformer ?<br>
A: <i>Any well made 300VA transformer, with 2 separate secondaries at min.36Vac - max.42Vac.</i><br>
<i>For my projects I order at https://petra-toroid.ro/?lang=en they ship worldwide.</i><br>
<i>How to order:</i><br>
<i>- go to https://petra-toroid.ro/contact/?lang=en use form or email</i><br>
<i>- mention that you want to order one or two 300VA trafo</i><br>
<i>- primary 115Vac or 230Vac, depending on the mains voltage in your region</i><br>
<i>- 2 separate 36Vac secondaries</i><br>
<i>- optional magnetic shielding</i><br>
<i>- mention that application will be for audio</i><br>
<i>Other sources are: https://www.audiophonics.fr/en/toroidal-transformers/toroidal-transformer-300va-2x38v-p-5548.html</i><br>
<i>Toroidy https://sklep.toroidy.pl/en_US/c/Toroidal-transformers-SUPREME-AUDIO-GRADE-V2/99</i><br>
<i>Trafco http://www.trafco.rs/torusni-en.php</i><br>
<br>
<br>
Q: Can Q17 drive ESL speakers ?<br>
A: <i>Yes, will drive ESL speakers very well. Thanks to high transconductance mosfet’s, Q17 will offer excellent performance on ESl speakers.</i><br>
<br>
<br>
Q: What make Q17 special ?<br>
A: <i>His topology, class B operation, PCB with embedded coil and innovative active power supply. </i><br>
<br>
<br>
Q: Is Q17 power eficient ?<br>
A: <i>Yes, it is. Thanks to class B operation and Saligny synchronous rectification, Q17 is a modern amplifier with low power consumption.</i><br>
<br>
<br>
Q: My left channel is warmer, ~5Celsius, than the right channel. How I can match them ?<br>
A: <i>Is this a really issue ? No.
Left/Right channel temperature difference is mainly due slightly different "bias" in output stage. Even Q17 is running in class B, each mosfet have different Vgs treshold and this is translated in more or less Ids current. You may start by matching Q12 to have very appropiate Vbe's, than make sure R11, R12, R13 are matching R11, R12, R13 from other channel. Finnaly, match output Q15 .. Q18 mosfets between channels.</i><br>
<br>
<br>
Q: Voltage over R3 should be around 0.6Vdc, but mine is way off, how may I adjust this ?<br>
A: <i>In order to have 0.6Vdc over R3, Q9 and Q11 must be matched (same Vgth), only then voltage over R3 is given only by Q10Vbe. Therefore please match Q9 and Q11 to have same Vgsth=Voltage gate to source threshold. </i><br>
<br>
<br>
Q: Where you you place this amplifier in term of value ?<br>
A: <i>A well executed Q17, will be better or at least on pair with some $5 digit amplifiers.</i><br>
<br>
<br>
Thank you for reading ! <br>
If you have built this amplifier I would love to see your Q17 implementation. :-) <br>
<br>
Many thanks to those who built Q17 and shared their experience. Here is the builders feedback:<br>
https://www.diyaudio.com/community/threads/q17-a-quad-405-audiophile-approach-to-perfect-sound.374507/page-72#post-7179645
<br>
