# BPT function of each terminal
<img width="269" height="697" alt="image" src="https://github.com/user-attachments/assets/7d356674-e19f-423d-8ef0-b34e97113d87" />

# Ring function of each wire (audio)
From a Ring [official article](https://ring.com/gb/en/support/articles/4f7mk/wiring-differences-2022-2024-intercom?srsltid=AfmBOopXsGDY_prO8N8ybd3RTSOSgj1yXhDqdVhIvNeraoLANBqL1j0a), we know below wire function for Ring Intercom (2024, so audio model):  
C-1	UNLOCK RETURN (GROUND)  
C-2	AIN  
C-3	AOUT  
C-4	AUDIO RETURN (MAIN GROUND)  
C-5	UNLOCK  
C-6	DOORBELL  
C-7	DOORBELL RETURN (GROUND)  
C-8	DOORBELL2  
C-9 BUS1  
C-10 BUS2  
C-11 BUS_PWR  
C-12 BUS_SWITCH  

C-1 to C-8 is for analog systems, C-9 to C-12 is for digital systems.  

# Ring function of each wire (video)  
But counting the wiring of Ring Intercom Video product, obviously there are 14 wires, so it's slightly different.  
This Amazon review gave some good color:  
<img width="1005" height="624" alt="image" src="https://github.com/user-attachments/assets/603b8984-e66b-4e48-a14d-edbe0783571f" />  

This is a Fermax 3315, by checking around, found a Fermax 3310 [manual](manuals/Fermax%203310%20manual.pdf) (very hard to find), and it shows the functionality of terminals:  
1,2,3,6 common audio  
4 call wire  
V: live co-axial  
M: shield co-axial  

We can decuce then the 14 wires of Ring Intercom Video:  
C-1 to C-8, green wire, lavender wire, C-9 to C-12

# Color and wire code match
According to a early 2025 youtube video installing Ring Audio to an old TEGUI intercom, it provides the below wiring colors:
<img width="510" height="523" alt="image" src="https://github.com/user-attachments/assets/22fa0542-3d63-49da-a8ae-0539ab301a72" />  
As a bi-product, it's then possible to deduce audio port function for Fermax 3315:
1 for UNLOCK, 2 for AOUT, 3 for GROUND, 6 for AIN

# How the door unlock signal is sent in BPT systems
I have noticed that many intercom system has a terminal for unlock, but BPT system does not have one. A [trouble shoot document](manuals/BPT%20trouble%20shooting%20guide.pdf) from intercomsrus provides some color:  
<img width="558" height="152" alt="image" src="https://github.com/user-attachments/assets/18461918-44b4-4745-a41a-491dcdb0128d" />  

So terminal 5 and terminal 9 voltage will turn to 0V when unlock button is pressed, terminal 5 (marked -) is GROUND/COMMON (this is also supported by [BPT YC200 manual](manuals/BPT%20YC200%20manual.pdf), YC200 is an audio only unit in Lynea 200 series).  
So the door unlock signal is sent by short circuiting terminal 9 to ground.

# How the door unlock signal is sent in Ring Intercom system
[AV forums article](https://www.avforums.com/threads/ring-intercom-to-unlock-an-electric-lock-without-an-intercom-system.2434428/) and [Reddit article](https://www.reddit.com/r/Ring/comments/12twr93/ring_intercom_official_pinout/) points to the door unlock signal is sent via short circuiting A1 and A5 (so it's old Ring 2022), meaning short UNLOCK to GROUND.  
So for Ring Intercom Video 2025, door unlock signal is sent via: short circuiting UNLOCK (C-5) to GROUND (C-4).

# Wiring of Ring Intercom Video to YKP/200
Now the wiring of Ring wire to BPT terminal is becoming clear, and one may work out required wiring on their own:
| Ring Code  | Ring Color  | Ring Func  | BPT Terminal  | BPT Func  |
|---|---|---|---|---|
| C-2  | Brown  | AIN  | 8  | Audio to monitor  |
| C-3  | Black  | AOUT  | 9  | Audio to panel  |
| C-4  | White  | GROUND  | 5  | Ground/Common/-  |
| C-5  | Grey  | UNLOCK  | 9  | Audio to panel  |
| C-6  | Purple  | DOORBELL  | 7  | Call input  |
| ?  | Green  | VIDEO  | 3  | Video signal (co-axial) |
| ?  | Lavendar  | VIDEO SHIELD  | 4  | Video signal shield (co-axial)  |

Now I feel confident enough to commit the puchase.

# Sources:
https://www.intercomsrus.com/
https://ring.com/gb/en/support/articles/4f7mk/wiring-differences-2022-2024-intercom?srsltid=AfmBOopXsGDY_prO8N8ybd3RTSOSgj1yXhDqdVhIvNeraoLANBqL1j0a
https://community.home-assistant.io/t/fermax-door-opener-mini-smart-switch/731319
https://www.youtube.com/watch?app=desktop&v=wnpwoko1Ll4
https://www.avforums.com/threads/ring-intercom-to-unlock-an-electric-lock-without-an-intercom-system.2434428/
https://www.reddit.com/r/Ring/comments/12twr93/ring_intercom_official_pinout/
