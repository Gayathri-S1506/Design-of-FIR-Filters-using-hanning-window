# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
clear;
close;

M = 61;              // Increased filter length (sharper filter)
fc = 0.25;           // Lower cutoff (narrower passband)

// Hanning window
n = 0:M-1;
w = 0.5 - 0.5 * cos(2 * %pi * n / (M-1));

// Ideal impulse response
hd = sin(2 * %pi * fc * (n - (M-1)/2)) ./ (n - (M-1)/2);
hd((M-1)/2 + 1) = 2 * %pi * fc;

// Apply window and normalize
h = hd .* w;
h = h / sum(h);

// Display and plot
disp(h);

subplot(2,1,1);
plot(h);
xlabel('Samples');
ylabel('Amplitude');
title('Impulse Response (fc = 0.25, M = 61)');

[H, f] = frmag(h, 512);
subplot(2,1,2);
plot(f, H);
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Frequency Response (Low Pass FIR Filter)');



# OUTPUT
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/a5fa0e67-d7a5-47ac-ab54-1b654239b036" />


# RESULT
Thus, a Low Pass FIR Digital Filter was successfully designed using the Hanning window method in SCILAB.
