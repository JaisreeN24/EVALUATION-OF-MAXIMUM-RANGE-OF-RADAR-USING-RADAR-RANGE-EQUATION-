# RADAR-RANGE-EQUATION

# EXP - 8  EVALUATION OF RADAR RANGE USING SCILAB

## AIM:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through SCILAB.

---

### Theory:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

<img width="292" height="100" alt="image" src="https://github.com/user-attachments/assets/780256d8-a29a-465e-847e-6bf9047252eb" />

<br><br>

<img width="302" height="130" alt="image" src="https://github.com/user-attachments/assets/fe92b7c4-2b9f-48e6-b8c9-e1bbe8b14097" />

---

### Procedure:

1. Set Up the Python Enviroment:Ensure that Pytho is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2. Import Necessary Libraries: Import the math library in Python.
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section and minimum detectable power.
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6. Execute the program: Run the Python script to calculate and display the maximum range of the radar.

---

### Program:

```sci
clc;
clear;
close;

Pt = 1000;          
G = 40;             
lambda = 0.03;      
sigma = 1;          

R = 1000:1000:100000; 

Pr = (Pt * G^2 * lambda^2 * sigma) ./ ...
     (((4 * %pi)^3) * (R.^4));

Pr_dB = 10 * log10(Pr);

figure(1);
plot(R, Pr_dB);
xlabel("Range R (m)");
ylabel("Received Power Pr (dB)");
title("Pr(dB) vs Range(R)");
xgrid();

Pr_min = 1000;

Pt_required = (Pr_min * ((4 * %pi)^3) .* (R.^4)) ./ ...
              (G^2 * lambda^2 * sigma);

Pt_dB = 10 * log10(Pt_required);

figure(2);
plot(R, Pt_dB);
xlabel("Range R (m)");
ylabel("Transmitted Power Pt (dB)");
title("Pt(dB) vs Range(R)");
xgrid();


```

---

### Output Waveform:

### R vs Pr(dB):

<img width="754" height="712" alt="image" src="https://github.com/user-attachments/assets/bc8572e8-8a17-47fb-932c-27d11bff859b" />

### R vs Pt(dB):

<img width="753" height="716" alt="image" src="https://github.com/user-attachments/assets/250b8e4e-2f9b-4f0d-9cb3-ebb483109c02" />


---

### Manual Calculation:

<img width="842" height="1353" alt="WhatsApp Image 2026-06-09 at 14 47 10" src="https://github.com/user-attachments/assets/4c2a653c-cd53-46a4-90fb-8f85328a1340" />


---

### Result:

Thus, the value of maximum range of a radar of a radar system calculated using the Radar Equation is successfully verified using Scilab.
