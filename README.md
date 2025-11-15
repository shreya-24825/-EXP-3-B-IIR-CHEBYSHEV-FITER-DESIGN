# EXP 3 : IIR-CHEBYSHEV-FITER-DESIGN

## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```
clear;

Fs = 5000;          
fc = 1500;          
b = [0.0929 0.2787 0.2787 0.0929];   
a = [1.0000 -0.5772 0.4218 -0.0561];
 
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

f = f_norm * Fs;

clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I Low Pass Filter (Order 3)");
xgrid();

disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```

## PROGRAM (HPF): 
```
clear;
Fs = 5000;      
fc = 1500;        
b = [0.4218 -0.5772 0.2787 -0.0929];   
a = [1.0000 -0.5772 0.4218 -0.0561];
  
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);
f = f_norm * Fs;

clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I High Pass Filter (Order 3)");
xgrid();

disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```


## OUTPUT (LPF) : 

<img width="1901" height="1083" alt="E3(i) - LPF(chebyshev)" src="https://github.com/user-attachments/assets/776277b0-837f-4375-b2dd-9ba1718cc49a" />


## OUTPUT (HPF) : 

<img width="1916" height="1199" alt="E3(ii) - HPF(Chebyshev)" src="https://github.com/user-attachments/assets/5740c2db-9ce6-4668-b803-801fd9b76798" />


## RESULT: 

A 3rd-order Chebyshev Type I high-pass filter was designed with cutoff frequency 1500 Hz and sampling frequency 5000 Hz. The frequency response shows ripple in the passband and sharp attenuation in the stopband.
