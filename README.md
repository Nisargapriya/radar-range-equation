# radar-range-equation
Aim:

To implement and analyze the Radar Range Equation using SCILAB and determine the variation of received power and transmitted power with radar range

EQUIPMENTS REQUIRED:

• Computer with i3 Processor

• SCI LAB

THEORY:

Radar Range Equation is used to determine the maximum range at which a radar system can detect a target. It relates the transmitted power, antenna gain, wavelength, radar cross section of the target, and the minimum detectable power at the receiver.

The maximum radar range is given by:

Rmax = [ (Pt G² λ² σ) / ((4π)³ Pmin) ]^(1/4)

where,

Pt = Transmitted power (W)
G = Antenna gain
λ = Wavelength (m)
σ = Radar cross section (m²)
Pmin = Minimum detectable power (W)
Rmax = Maximum radar range (m)

The radar range equation shows that the maximum detection range increases with transmitted power, antenna gain, wavelength, and target radar cross section. It decreases as the minimum detectable power increases.

Thus, the radar range equation is used to analyze the performance and detection capability of a radar system.

ALGORITHM:

1. Start the program.

2. Define the speed of light (c) and operating frequency (f).

3. Calculate the wavelength using:
      λ = c/f

4. Specify the antenna gain and radar cross section.

5. Define the transmitted power and minimum detectable power.

6. Compute the maximum radar range using the radar range equation.

7. Calculate the received power corresponding to different radar ranges.

8. Calculate the required transmitted power for different radar ranges.

9. Convert the power values into dBm.

10. Plot received power versus radar range.

11. Plot required transmitted power versus radar range.

12. Analyze the radar performance characteristics.

13. Stop the program.

PROGRAM :
```
clear;
clc;

c = 3e8;
f = 3e9;

lambda = c/f;

Gr_dB = 30;
Gr = 10^(Gr_dB/10);

sigma = 1;

Pt_fixed = 1000;
Pr_min = 1e-12;

R = 1000:500:100000;

num1 = Pt_fixed * (Gr^2) * (lambda^2) * sigma;
den1 = ((4 * %pi)^3) * (R.^4);

Pr = num1 ./ den1;
Pr_dBm = 10 * log10(Pr / 1e-3);

num2 = Pr_min * ((4 * %pi)^3) * (R.^4);
den2 = (Gr^2) * (lambda^2) * sigma;

Pt_req = num2 ./ den2;
Pt_req_dBm = 10 * log10(Pt_req);

subplot(2,1,1);
plot(R/1000, Pr_dBm);
xtitle("Received Power vs Radar Range", ...
       "Range (km)", ...
       "Received Power (dBm)");

subplot(2,1,2);
plot(R/1000, Pt_req_dBm);
xtitle("Required Transmitted Power vs Radar Range", ...
       "Range (km)", ...
       "Required Transmitted Power (dBm)");

grid();
```
TABULATION:

<img width="365" height="450" alt="image" src="https://github.com/user-attachments/assets/6c4ad69d-b350-4698-989a-bf9e5328008c" />

 OUTPUT :

 <img width="956" height="598" alt="image" src="https://github.com/user-attachments/assets/c1be8a43-8cfd-45e3-9d6a-8906758d8b0e" />

 RESULT:

Thus, the radar range equation is implemented using SCILAB and the radar range characteristics are obtained and verified.

 
