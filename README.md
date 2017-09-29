# Motorcycle-Sound-mod

You can see how it works from the link below:
https://www.youtube.com/watch?v=q3Sr57Ecp1U

I am using TMRpcm sound library to achieve this.
you have to do some modifications in this library,these are the things you have to modify:
Refer
https://github.com/TMRh20/TMRpcm
https://github.com/TMRh20/TMRpcm/wiki

Edits to be done in library files

Open pcmConfig.h in TMRpcm library



put

     unsigned int resolution; 
under public variables:

put 

    timerSt();
    
under public functions:

add

    unsigned int orgsamplerate;
    
under public variables


Open TMRpcm.cpp

comment the following lines

    //SAMPLE_RATE = sFile.read();
 
    /SAMPLE_RATE = sFile.read() << 8 | SAMPLE_RATE;
and add the following

    orgsamplerate = sFile.read();
  
    orgsamplerate = sFile.read() << 8 | orgsamplerate;

I have uploaded the modified files also.



My Arduino Program is increasing the pitch and at the same time volume of bike sound file. This gives us the effect of a motorcycle.

Program is based on Arduino Mega, you can also use this program in other boards ,by doing some modifications.

Here is the link for Motorcycle Audio Files:

