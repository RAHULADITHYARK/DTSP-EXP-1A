
# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

 To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
## 1.DIRECT METHOD
```
clc;
clear;
clf;

x = [1 2 3 4];   // change this as needed
N = length(x);


X = zeros(1, N);

for k = 0:N-1
    for n = 0:N-1
        X(k+1) = X(k+1) + x(n+1) * exp(-%i*2*%pi*k*n/N);
    end
end

mag = abs(X);
ph = atan(imag(X), real(X));


disp("Input x(n):"), disp(x);
disp("DFT X(k):"), disp(X);
disp("Magnitude:"), disp(mag);
disp("Phase:"), disp(ph);


k = 0:N-1;

subplot(2,1,1);
plot2d3(k, mag);
title("Magnitude Spectrum");
xlabel("k"); ylabel("|X(k)|");

subplot(2,1,2);
plot2d3(k, ph);
title("Phase Spectrum");
xlabel("k"); ylabel("Phase (rad)");
```
## 2.FFT
```
clc;
clear;
close;


xn = [1 2 3 4 4 3 2 1];
N = length(xn);
n = 0:N-1;


Xk = fft(xn);


mag = abs(Xk);
ph = atan(imag(Xk), real(Xk));   // phase


y = ifft(Xk);

subplot(2,2,2);
plot2d3(n, mag);
title('Magnitude Spectrum');
xlabel('k'); ylabel('Magnitude');

subplot(2,2,3);
plot2d3(n, ph);
title('Phase Spectrum');
xlabel('k'); ylabel('Phase (radians)');
```

# OUTPUT: 

1.Direct mothod

<img width="768" height="725" alt="image" src="https://github.com/user-attachments/assets/78b9e798-adef-4a8a-a6d4-ed627ab84292" />

2.FFT

<img width="766" height="726" alt="image" src="https://github.com/user-attachments/assets/3dc5057e-548e-4300-a603-f3fe1eee6147" />


# RESULT: 
The DFT was successfully computed using the direct formula and using FFT.
