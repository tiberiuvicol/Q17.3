# Q17.3 - more than an audiophile approach to perfect sound

Q17.3 is a continuation of the <a href="https://github.com/tiberiuvicol/Q17-audiophile-amplifier">Q17 class B amplifier</a> based on current dumping principle.<br>
Use KiCad 7, or later, to open and edit source files.  KiCad 7 can be downloaded from CERN, https://www.kicad.org<br>
<b>LTSpice</b> - contain simulation asc file<br>


![Q17 3](https://github.com/tiberiuvicol/Q17.3/assets/22703498/20012061-849b-4d76-9197-8cabab17cdc0)


<br>
Click & Order your Q17.3 parts @ digikey https://www.digikey.co.uk/en/mylists/list/O9YXGXU6LF <br>
For STEREO or MULTICHANNEL multiply the order with the same parts. <br>
You may order your PCB at 
<a href="https://www.pcbway.com/project/shareproject/Q17_3_more_than_an_audiophile_approach_5a49a5dd.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>
<br>
What is new ? <br>
Operational was changed to OPA828. This is one of the few SiGe devices on the market, with terrific performance and most important, sound quality is exceptional.
Current mirror was replaced with NDC7003P or PJS6839. This have 2 matched p-mos transistors on same substrate with same thermal Vgs deviation.<br>
Furthermore, by adding Q7, current mirror was upgraded to a Wilson one. This improve mirror stability and class A stage operation at high frequncy.
In an atempt to make the amplifier more "popular", I have adopted well known parts as 2N4401/2N4403 and 2N5551/2N5401. These are widely available from various manufacturers.
First stage after OPA828 is now a modified Borbely cascode, made with a well known jfet LSK170B and a depletion mosfet DN2535/DN2540. 
In addition, R10 and R13 have been reduced to 9R1.<br>
With this modifications, Q17 performence was considerably improved, both in measurement and listening.
<br>
If you have built this amplifier I would love to see your Q17 implementation. :-) <br>
<br>
Many thanks to Stéphane <a href="https://github.com/stefaweb/Q17-Amplifier">@stefaweb</a>, for taking the time to build and test Q17.3 <br>
Enjoy and thank you for reading !
