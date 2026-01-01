# Installation
I have finally purchase Ring Intercom Video and Ring Intercom Audio and decide to implement my research at home. Christmas has a very good discounted price at 70 pounds for video models and 35 for audio models.

# Wiring
Ring Intercom Video has a 14pin flat cable and Ring Intercom Audio has a 12pin flat cable. And in order:
a) C-1 to C-8, for analogue system
b) C13 and C14, for video signals (missing in Audio model)
c) C9 to C-12, for digital system

# Ring Intercom Video
I can confirm that YKP/200 is indeed compatible with the Ring Intercom Video. The wiring is almost the same as I projected, except the absence of C-5 connection.   
![IMG_5869](https://github.com/user-attachments/assets/8eb953f7-da75-4923-9f33-974612c934d6)  

My guess is that Ring have each profile programmed to be able to short circuit any of the grounds (C-1, C-4, C-7) and any of the rest analogue cables, so it can short C-3 and C-4 for me automatically therefore no need to connect C-5.  
![Image_20260101211554_107](https://github.com/user-attachments/assets/264b8fcb-91e6-419e-bc00-9b9091a3951f)  

When connecting the wire, I unscrew anticlockwise 2 rounds and can then insert the cables, fasten again and it works straight away.

It's a shame that since C-5 is not used and it has other grounds, technically it can operate two doors, but think there is no profiles for that and it doesn't allow user to specify either.  

# Ring Intercom Audio
My intercom system has an aux button to control a driveway gate, and I have studied the wiring and determine that Ring should be able to control it.  
On top of the video intercom, I also have a audio only YC/200 + YP1 on ground floor, this enable further work.  
I already know that terminal 5 is ground, terminal 7 is call in, terminal 8 is audio in and terminal 9 is audio out, I can also see there is separate ground connected to the aux button (blue wire). So for the audio model, I selected a profile under Generic, "6 wire (unlock separate ground)"  
![IMG_5878](https://github.com/user-attachments/assets/d9889dce-4a7b-4dce-b84e-81caf12bf24c)  

In fact since both my intercoms are BPT 200 series, C-2, C-3, C-4, C-6 should be having the same wiring terminal as the Video model, and I just need to add C-1 to aux ground, and C-5 to aux activation  
![IMG_5879](https://github.com/user-attachments/assets/3d775dda-77e7-4d29-af3d-63ad86aaebc8)  

Again it works, I am now able to control the gate remotely, what's better, is that you can add a Ring widget in carplay, and you can control the gate from car screen.
