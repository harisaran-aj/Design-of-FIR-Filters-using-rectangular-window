# Design-of-FIR-Filters-using-rectangular-window
# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
// DESIGN OF LOW PASS FIR FILTER USING RECTANGULAR WINDOW

clc;
clear;
close;

// Filter specifications
N = 21;          // Filter length
fc = 0.12;       // Normalized cutoff frequency (0 < fc < 0.5)
M = N - 1;
n = 0:M;

// Ideal impulse response (sinc function)
hd = 2 * fc * sinc(2 * fc * (n - M/2));

// Rectangular window
w = ones(1, N);

// FIR filter coefficients
h = hd .* w;

// Frequency response
[H, f] = frmag(h, 1024);   // magnitude response

// ---- Plot impulse response (use plot2d3 instead of stem) ----
figure(1);
plot2d3(n, h);
title('Impulse Response of FIR Low Pass Filter (Rectangular Window)');
xlabel('n');
ylabel('h[n]');
xgrid();

// ---- Plot magnitude response ----
figure(2);
plot(f, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency');
ylabel('|H(f)|');
xgrid();

// ---- Display filter coefficients ----
disp("Filter Coefficients (h[n]):");
disp(h');

disp("Filter length (N): " + string(N));
disp("Cutoff frequency (fc): " + string(fc));
disp("Window used: Rectangular");
```
# OUTPUT
<img width="428" height="698" alt="image" src="https://github.com/user-attachments/assets/180385d3-c05a-419b-9016-17f7d3b60b39" />

<img width="762" height="598" alt="image" src="https://github.com/user-attachments/assets/0d60975b-febb-47b2-b542-5dbaf5c3cb1b" />

<img width="758" height="632" alt="image" src="https://github.com/user-attachments/assets/c027d094-227c-481d-9faf-8c569ad87870" />

# RESULT
 Design of low pass FIR digital filter using SCILAB was generated.
