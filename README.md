# A4
circuit modeling
%Assignment 4 Fernanda Akegawa Monteiro 100955052
%Question 1
%--------------------part a)-------------------------
%Transfer function = H (s)
%Vout=((Zc/(Zc+Zr))*Vin
%Zc=1/Cs
%Zr=R
%Vout/Vin=((1/Cs)/((1/Cs)+R))=H(s)
%H(s)=1/(1+RCs)
%s=jw
%H(jw)=1/(1+RCjw)
%|H(jw)|=1/sqrt(1+(RCw)^2) ------> Low pass filter

%--------------------part b)-------------------------
%3dtb-> |H(jw)|^2=1/2
%|H(jw)|^2=1/(1+(RCw)^2)=1/2
%1+(RCw)^2=2
%(RCw)^2=1
%w=1/(RC)
R=20;
C=10e-6;
w=1/(R*C);   %w=5000
f=1/(2*pi*R*C) %f=795.77
%dw=linspace(0,2000,1000);
df=linspace(0,1100,1000);
H=1./(1+((R*C*2*pi*df).^2)); %not writing the |  |^2 for ploting
loglog(df,H)

%--------------------part c)------------------------
%H=1/(1+2e-4*s)=Vout/Vin
%Vin=Vout+Vout*2e-4*S
%Vin(t)=Vout(t)+2e-4*(dVout/dt)
%dVout/dt=(Vin(t)-Vout(t))/(2e-4)
%--------------------part d)------------------------
Vin=1;
for t=0:100
   % dVout/dt=ddVout;
   if t=0;
   Vout=0;
   end
    ddVout=(Vin(t)-Vout(t))/(2*10^-4);
    ddVout=Vout;
    plot(ddVout,t)
end
