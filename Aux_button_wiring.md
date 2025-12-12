# Backgound  
My intercom YKP/200 has also an aux button (auxiliary function, the one with two dots) that opens a drive way gate.  
<img width="346" height="486" alt="image" src="https://github.com/user-attachments/assets/ad09e88c-3b4e-4732-b79d-434ec2c23ca9" /> <img width="362" height="334" alt="image" src="https://github.com/user-attachments/assets/bad0f281-ff81-418d-8e20-34916416baa3" />  


I wonder if Ring Intercom has a way to open that gate instead, therefore it's necessary to investigate its wiring.  
We know from [YKP 200 manual](manuals/BPT%20YKP200%20manual.pdf), that terminal 10 and 11 is responsible for auxiliary button, but it doesn't specify the wiring.  
<img width="359" height="395" alt="image" src="https://github.com/user-attachments/assets/9ab93bcd-0246-4580-942e-0242b1dfa82e" /> <img width="363" height="407" alt="image" src="https://github.com/user-attachments/assets/b991d8ac-566a-4114-918e-7c55d3a4c213" />


# Relay unit BPT VLS/101
The way it works is that YKP/200 will connect to PSU (Power Supply Unit) VA/200 and will also connect to a relay unit VLS/101. The wiring diagram is illustrated in figure 8 of [VLS 101 manual](manuals/BPT%20VLS%20101%20manual.pdf).  
<img width="274" height="895" alt="image" src="https://github.com/user-attachments/assets/33370c90-ee0b-4a99-9249-a2f9a24032ec" />  

From this diagram, we can see that terminal 10 is connected to terminal 5, and terminal 5 is ground/common, so terminal 10 is also groud/common. Terminal 11 is connected to VLS/101's B-2. And VLS/101's B-1 terminal is connected to YKP/200 terminal 6 and connect to VA/200's terminal 6 which is a +17.5V.  
When the aux button is not pressed, the relay unit B-1 is +17.5V but B-2 is not connect to ground, so the relay coil is not powered. When button is pressed, YKP/200's terminal 10 and terminal 11 will connect and VLS/101's B-1 terminal will connect to ground, then B-1 is +17.5V and B-2 ground gives power to relay coil, causing the A terminal switch to flip to the other side (thus triggering a signal to send to the digital bus of my driveway gate controller and gate opens).  

After examining the wiring, I can see that my terminal 5 and terminal 10 has same color wiring (blue green-ish with alternating white and brown stripes):  
<img height="500" src="https://github.com/user-attachments/assets/ac45213b-51c6-406a-abe1-7cc693c1786d" />  

Then I can just connect Ring's UNLOCK wire to terminal 11 and keep GROUND wire at terminal 5.  

# Wiring for door unlock to open drive way gate  
Provisional wiring (to be verified):  
| Ring Code  | Ring Color  | Ring Func  | BPT Terminal  | BPT Color | BPT Func  |
|---|---|---|---|---|---|
| C-2  | Brown  | AIN  | 8  | long white short green | Audio to monitor  |
| C-3  | Black  | AOUT  | 9  | brown-ish | Audio to panel  |
| C-4  | White  | GROUND  | 5 (same as 10) | green-ish blue with white and brown strips | Ground/Common/-  |
| C-5  | Grey  | UNLOCK  | 11  | Red with grey strip | Aux connect to relay  |
| C-6  | Purple  | DOORBELL  | 7  | long green short white | Call input  |
| ?  | Green  | VIDEO  | 3  | long brown short white |Video signal (co-axial) |
| ?  | Lavendar  | VIDEO SHIELD  | 4 | long white short brown | Video signal shield (co-axial)  |
