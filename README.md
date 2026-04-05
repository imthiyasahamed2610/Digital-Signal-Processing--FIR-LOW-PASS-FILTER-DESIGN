# Digital-Signal-Processing--FIR-LOW-PASS-FILTER-DESIGN
## AIM:
To generate design of low pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Low Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
clc;                % Clear screen
clear all;          % Clear variables
close all;          % Close all figure windows

wc = input('Enter the value of cut off frequency: ');
N  = input('Enter the value of filter length: ');

alpha = (N-1)/2;
eps   = 0.001;

% High Pass Filter Coefficient
n  = 0:1:N-1;
hd = (sin(pi*(n-alpha+eps)) - sin(wc*(n-alpha+eps))) ./ (pi*(n-alpha+eps));

% Hamming Window Sequence
n  = 0:1:N-1;
wh = 0.54 - 0.46*cos((2*pi*n)/(N-1));

% Final High Pass Filter
hn = hd .* wh;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'ms');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('High Pass Filter using Hamming Window');
grid on;

## OUTPUT:
<img width="621" height="587" alt="image" src="https://github.com/user-attachments/assets/fc260b78-5b74-4d10-a283-724d0070be9f" />


## RESULT:
![WhatsApp Image 2026-04-05 at 4 58 21 PM](https://github.com/user-attachments/assets/b8da72c7-cbdb-4ac9-95bd-42d320c7a5ae)


