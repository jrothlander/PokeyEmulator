# Pokey Emulator

This is a .Net library and emulator the Atari POKEY sound chip. I have included a Windows desktop dashboard that allows you to create POKEY based sound effects that can be used in .Net application with the library or used to create the necessary settings to generate the sounds in 6502 Assembly. The emulator includes the POKEY emulation and a voice synthesizer. 

I am currently working on cleaning up the code base and setting up repos here on GitHub for them. I have a couple of games I have built that use the library, my own versions of Tempest and Galaga, as well as a couple of demo apps that demonstrate how everything works. 

I really like how easy it is to setup the sound effects in the dashboard and create sound banks that you can easily load into your games or other applications, to add sound effects and retro computer voices. When I build my custom version of Tempest, I struggled with how best to create the sounds and how to deal with the copyright, since Tempest is a commercial product with a defended copyright. That's what drove me to take the time to build the emulator. For my games, the sounds are not sound files. I did not copy them or record them from the original. I generate them from a mathematical model using the same settings as the original. If need be, I can tweak them to generate the same sort of sound, but a different and unique sound that is purely my own. 

I am working through a few videos of how all of this works. Here's a link to the first video: 
https://youtu.be/KVJ0v4fZg3E

## References
> A few references if you are looking for documentation on the Atari POKEY chip. 

https://en.wikipedia.org/wiki/POKEY
http://visual6502.org/images/C012294_Pokey/pokey.pdf

I have added a \doc folder here and included a PDF that I created to document what I have learned along the way. This is work in progress. But I break down the features of the chip that applies to sound effects generation. 
