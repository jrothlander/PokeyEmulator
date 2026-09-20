# Pokey Emulator

This is a .Net library and emulator for the Atari POKEY sound chip. 

Currently, I only have some documentation of the chip and my emulator, as well as a link to some videos that demonstrate how to use it. I also have several 8-bit songs in another repo, linked below, that demonstrate the type of songs you can generate. I will include sound effects at some point as well. 

I will include a Windows desktop dashboard here that allows you to create POKEY-based sound effects that can be used in a .Net application with the library or used to create the necessary settings to generate the sounds in 6502 Assembly. The emulator includes the POKEY emulation and a voice synthesizer. 

I am currently working on cleaning up the codebase and setting up repos here on GitHub for them. I have a couple of games I have built that use the library, my own versions of Tempest and Galaga, as well as a couple of demo apps that demonstrate how everything works. I have also created a Digital Music Production application that uses the POKEY Chip Emulator to create 8-bit music for games.

I really like how easy it is to set up the sound effects in the dashboard and create sound banks that you can easily load into your games or other applications to add sound effects and retro computer voices. When I built my custom version of Tempest, I struggled with how best to create the sounds and how to deal with the copyright, since Tempest is a commercial product with a defended copyright. That's what drove me to take the time to build the emulator. For my games, the sounds are not sound files. I did not copy them or record them from the original. I generate them from a mathematical model using the same settings as the original. If need be, I can tweak them to generate the same sort of sound, but a different and unique sound that is purely my own. 

I am working through a few videos of how all of this works. Here's a link to the first rough cuts of the video. I will work to improve them. 
https://youtu.be/KVJ0v4fZg3E

## References
> A few references if you are looking for documentation on the Atari POKEY chip. 

https://en.wikipedia.org/wiki/POKEY
http://visual6502.org/images/C012294_Pokey/pokey.pdf

I have added a \doc folder here and included a PDF that I created to document what I have learned along the way. This is work in progress. But I break down the features of the chip that apply to sound effects generation. 

## DAW Application that uses the POKEY Chip Emulator
> This is a custom application that I use to create 8-bit music. 

<img width="1486" height="913" alt="image" src="https://github.com/user-attachments/assets/cf85aa4f-410e-4eab-b468-c46f95c65b8f" />

## POKEY Chip Emulator Workbench and Dashboard
> With this application, you can create any of the sounds the Atari POKEY Chip created using the same settings as the original Atari games. I also use this to create the 8-bit songs for games and robotic voices.

<img width="1542" height="972" alt="image" src="https://github.com/user-attachments/assets/9c336020-7f53-4029-a03a-bbe05aef6a2c" />

