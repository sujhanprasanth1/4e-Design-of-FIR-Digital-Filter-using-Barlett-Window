# FIR-FILTER-DESIGN
# EXP 4e: Design-of-FIR-Digital-Filter-using-Barlett-Window

# AIM 1:  
To perform Design-of-LOWPASS FIR-Digital-Filter-using-Barlett-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) = Wc/ %pi ;

else

hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);

end

end

// Bartlett Window

for n = 1:M

W(n)=1-((2*abs((n-1)-((M-1)/2))/(M-1));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR LPF using Bartlett Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR LPF using Bartlett Window');





# OUTPUT: 

<img width="869" height="696" alt="image" src="https://github.com/user-attachments/assets/66ee9be5-f367-432a-905b-fcb776a28222" />

# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: 
To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) = 1-Wc/ %pi ;

else

hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);

end

end

// Bartlett Window

for n = 1:M

W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR HPF using Bartlett Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR HPF using Bartlett Window');

# OUTPUT: 
<img width="661" height="722" alt="image" src="https://github.com/user-attachments/assets/4bcb2506-7378-4fc1-bf55-65c5b2afed37" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: 
To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

Wc2=Wc(2);

Wc1=Wc(1);

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) =(Wc2-Wc1)/%pi ;

else

hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);

end

end

// Bartlett Window

for n = 1:M

W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR BPF using Bartlett Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR BPF using Bartlett Window');


# OUTPUT: 
<img width="878" height="633" alt="image" src="https://github.com/user-attachments/assets/a4eadef2-3278-4038-be82-190e5c4cc272" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ;

close ;

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency =');

Wc2=Wc(2);

Wc1=Wc(1);

alpha= (M -1)/2 // Center Value

for n = 1:M

if (n ==alpha+1)

hd(n) =1-((Wc2-Wc1)/%pi);

else

hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);

end

end

// Bartlett Window

for n = 1:M

W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));

end

//Windowing filter coefficients

h = hd.*W;

disp(h,'Filter Coefficients are')

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1)

plot(2*fr, hzm)

xlabel( ' Normalized Digital Frequency w');

ylabel( 'Magnitude ');

title( ' Frequency Response of FIR BSF using Bartlett Window ')

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2);

plot(2*fr , hzm_dB);

xlabel( ' Normalized Digital Frequency W' );

ylabel( 'Magnitude in dB');

title('Frequency Response of FIR BSF using Bartlett Window');



# OUTPUT: 

<img width="838" height="757" alt="image" src="https://github.com/user-attachments/assets/52d59094-48af-47ff-ab6b-40cec00f1d93" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.
