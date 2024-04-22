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






