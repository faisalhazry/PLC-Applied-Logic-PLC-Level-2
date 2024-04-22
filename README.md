# PLC-Applied-Logic-PLC-Level-2
This is revision of project Applied Logic PLC Level 2 for future project as templet  

## Project 1 Digital control logic
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/ed2852d4-bf9f-4898-bdb8-796ef5313e56)

### Sumary 
Today, we’re going to be maintaining the pressure in a receiver on a compressor application.  There are two pressure switches which close at 90 and 110psi (low and high).  To control the pressure, we have one pump.  Additionally, we want to illuminate an indicator light when the pressure is above 90psi.

### IO/ Assigned Memory
I:0/0 ‐ Low pressure switch (closes at 90psi and above) 
I:0/1 ‐ High pressure switch (closes at 110psi and above) 
O:0/0 – Pressure pump 
O:0/1 – Pressure indicator light

### Test Criteria
To start, run your program on Emulate.  The pump should start immediately but the light should be off. 

Next, force only the low pressure switch on (closed).  The pump should remain energized and the light should now also energize. 

Third, leave the low pressure switch closed and force the high pressure switch on as well.  The pump should deenergize and the light should remain energized. 

Fourth, leave the low pressure switch forced on and force off the high pressure switch.  The pump should remain deenergized and the light should remain on.  

Lastly, force both pressure switches off and verify that the pump starts back up and the light goes off. 

### Programing
#### Control
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/3337234b-9dff-4f61-a448-afe55389bc43)


#### Digital IO
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/da6198ca-1089-4182-b5ce-9ed77e4aba1a)

#### Main 
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/163c1107-f79d-4cc0-adce-9451d42adff5)


## Project 2 Digital filling station 
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/ceaa80e1-c2c2-423d-ae65-3a22dc25e2a2)

### Sumary
A conveyor belt carries boxes with colored labels to our filling staƟon and beyond. The proximity switch closes when a box arrives, and either a red or blue photo eye tells us which label is on the box. Red labeled boxes get filled with pecans and blue labels are for walnuts. A level switch tells us when the box is full and ready to send along.

### IO/ Assigned Memory
I:0/0 - Proximity switch (closes when a box is near)
I:0/1 - Level switch (closes when the box is full)
I:0/2 - Red photo eye (closes when a red label is in front of it)
I:0/3 - Blue photo eye (closes when a blue label is in front of it)
O:0/0 - Conveyor motor (makes the conveyor move forward when closed)
O:0/1 - Walnut hopper (when closed, solenoid opens allowing contents to fall from the hopper)
O:0/2 - Pecan hopper (when closed, solenoid opens allowing contents to fall from the hopper)

### Test Criteria
To start, run your program on Emulate. The conveyor motor should start immediately but both hoppers should be off.

Next, force only the proximity switch on (closed). The conveyor motor should shut off, and both hoppers should remain deenergized.
Third, leave the proximity switch switch closed and force the red photo eye on as well. The conveyor motor and the walnut hopper should remain off, but the pecan hopper should energize.

Fourth, leave the proximity switch closed and force the red photo eye off and the blue photo eye on. The conveyor motor should remain off, but the pecan hopper should deenergize and the walnut hopper should energize.

Next step, force the level switch on. The hoppers should both deenergize and the conveyor should start back up to move the box forward.

Finally, force the proximity switch, the level switch and both photo eyes off. Both hoppers should remain deenergized and the conveyor should keep running.

Bonus test: with the proximity switch and level switch open, force both photo eyes on. Neither hopper should energize. (We don’t want to release product when there isn’t a box to catch it in.)

### Programing
#### Control
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/048ef16c-8285-4cd9-baa0-37e425267b7c)

#### IO
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/3d92b759-9898-4415-a100-f6d677865a71)

#### Main 
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/524de7f3-aab4-42d0-8e1b-56e95b093bb5)


## Project 3 Inventory Management 

### Sumary
Our department manages three raw materials: “widgets,” “doodads” and “wockies.”  These all have part numbers in our system of 123, 456, and  789 respectively.  People will use a barcode scanner which will write the following string to our PLC: “PPP‐QQ:D” (without quotes) which will contain part number (PPP), quantity (QQ) and direction (1 ‐ incoming, 2 ‐ outgoing).  Store the on‐hand quantity of each.

### IO/ Assigned Memory
ST9:0 ‐ Barcode scan into PLC from barcode scanner 
N7:0 ‐ Part #123 quantity on‐hand 
N7:1 ‐ Part #456 quantity on‐hand  
N7:2 ‐ Part #789 quantity on‐hand 

### Test Criteria
To start, run your program on Emulate.  Nothing should be happening.  Check N7:0, N7:1 and N7:2 and make sure all three are equal to 0. 

Next, change the value of ST9:0 to “123‐10:1” without quotes.  Then check the N7 data file and N7:0 should be equal to 10.  N7:1 and N7:2 should be 0 still.  The value of ST9:0 should be automatically reset to a blank / empty / null / default value IMMEDIATELY after each scan (or each time we manually set the value). 

Third, set the value of ST9:0 to “123‐10:1” AGAIN.  You shouldn’t have to manually change the value to anything else between last step and this test.  Then check the N7 data file and N7:0 should be equal to 20. N7:1 and N7:2 should be 0 still.

Fourth, set the value of ST9:0 to “456‐15:1”.  Then check the N7 data file and N7:0 should be equal to 20. N7:1 should be 15 and N7:2 should be 0 still.

Next step, set the value of ST9:0 to “789‐30:1”.  Then check the N7 data file and N7:0 should be equal to 20. N7:1 should be 15 and N7:2 should be 30.  Now we know that incoming scans work!

Now, set the value of ST9:0 to “123‐19:2”.  Then, immediately after, set it to “456‐14:2”.  Then, change it once more to “789‐29:2”.  When we check the N7 data file and N7:0, N7:1 and N7:2 should all be equal to 1.  Now we know that outgoing scans work! 
Bonus test: set the value of ST9:0 to “149‐1:1”.  Nothing should change in our N7 data file, and we shouldn’t have any errors / interruptions in the flow of the program.  It should simply ignore the unrecognized part number. 

### Programing
#### Barcode read scanner
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/efa9825d-1d4e-40f4-a240-b5786bbbb3c3)

#### Decison Program
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/65b5d8b7-53b0-4e72-8d79-f0c8017c10db)

#### String Calculation 
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/58edf873-fd62-473f-9276-08e85766cdeb)


## Project 4 Multiposition Servo Application 
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/9df60a22-fb41-4a63-a554-4d75391bd074)

### Sumary 
A modular water treatment system is being integrated into an existing system.  When the host system calls for a cycle, our servo will cycle a control valve from the home position to fill for 10 seconds, then to drain for 20 seconds, then to flush for 10 seconds, and then back to home until the next call.  The cam‐operated microswitches tell us what position the valve is in. 
BONUS TASK 1: If you really want to show off, create an integer N7:0 which reports the current position of the valve.  The positions should be 0 = HOME, 1 = FILL, 2 = DRAIN, 3 = FLUSH and 4 = TRAVELLING 
(between positions). 
BONUS TASK 2: Set up B3:0/0 as a reset / interrupt button which will abort the process and return the valve to the home position. 

### IO/ Assigned Memory
I:0/0 ‐ Home microswitch (closes when valve in home position) 
I:0/1 ‐ Fill microswitch (closes when valve in fill position) 
I:0/2 ‐ Drain microswitch (closes when valve in drain position) 
I:0/3 ‐ Flush microswitch (closes when valve in flush position) 
I:0/4 ‐ Cycle call (signal closes when host requires a cycle) 
O:0/0 – Servo (energize to turn the cam thus changing valve position) 
Bonus IO: 
N7:0 – Valve position integer 
B3:0/0 – Reset / cycle interrupt button 

### Test Criteria
To start, run your program on Emulate.  The servo should energize immediately.  If you did the bonus portion of this project, N7:0 should be equal to 4. 

Next, force the fill microswitch on (closed).  The servo should still remain energized looking for home, but N7:0 should now be 1. 

Third, force the fill microswitch back off and the home microswitch on.  Now the servo should deenergize and N7:0 should be set to 0. 

Fourth, momentarily force I:0/4 on and then back off.  The servo should energize once more, but N7:0 should still be 0. 

Next step, force the home microswitch off.  N7:0 should go to 4.  Then force the fill microswitch on.  N7:0 should be equal to 1 and the servo should deenergize FOR ONLY 10 SECONDS and then start back up automatically. 

Now, force the fill microswitch off.  N7:0 should go to 4.  Then force the drain microswitch on.  N7:0 should be equal to 2 and the servo should deenergize FOR ONLY 20 SECONDS and then start back up automatically. 

Only one more mode to test.  Force the drain microswitch off.  N7:0 should go to 4.  Then force the flush microswitch on.  N7:0 should be equal to 3 and the servo should deenergize FOR ONLY 10 SECONDS and then start back up automatically. 

Finally, force the flush microswitch off.  N7:0 should go to 4.  Then force the home microswitch on.  N7:0 should be equal to 0 and the servo should deenergize and stay that way.  SUCCESS! 
Bonus test: momentarily force I:0/4 on and then back off.  The servo should energize, but N7:0 should still be 0.  Then toggle B3:0/0 on and then back off.  Next, force the home microswitch off and the fill microswitch on (closed).  The servo should still remain energized looking for home, but N7:0 should now be 1.  To wrap it up, force the fill microswitch off.  N7:0 should go to 4.  Then force the home microswitch on.  N7:0 should be equal to 0 and the servo should deenergize and stay that way. 

### Programing
#### Control
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/fb955174-c35c-4873-8914-119fc30cf632)

#### IO
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/0b56a8dc-4e0c-4e08-a70d-bd47d2c9fd87)

#### Main
![image](https://github.com/faisalhazry/PLC-Applied-Logic-PLC-Level-2/assets/121289405/c9d6905f-5edd-49e0-a4c6-c856ec00b342)








