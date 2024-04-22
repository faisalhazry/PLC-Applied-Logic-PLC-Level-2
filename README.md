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

## Project 2 Digital control logic


