# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


__Algorithm__:
 1) Start the program
Initialize the radar range evaluation process.

2) Import required libraries
Load the necessary Python packages (e.g., math or numpy) to support calculations.

3) Define input parameters & radar range function
Assign values to transmitted power, antenna gains, wavelength or frequency, radar cross-section, and minimum detectable signal;
then create a function implementing the Radar Range Equation.

4) Compute the maximum radar range
Substitute parameters into the Radar Range Equation and evaluate the resulting maximum range.

5) Display/plot the output
Print the calculated radar range and visualize results using appropriate plots. 


 __Code__:
```import numpy as np
import matplotlib.pyplot as plt

# Given values
Pt = 1000
G = 40
lambda_ = 0.05
sigma = 10
pi4 = (4 * np.pi) ** 3

R = np.linspace(1e3, 200e3, 500)     # Range
Pr_R = (Pt * G**2 * lambda_**2 * sigma) / (pi4 * R**4)
Pr_R_dB = 10 * np.log10(Pr_R)

plt.figure(1)
plt.plot(R / 1000, Pr_R_dB)
plt.xlabel("Range (km)")
plt.ylabel("Power Received (dB)")
plt.title("Received Power vs Range (Radar Equation)")
plt.grid(True)

Pt_values = np.linspace(100, 10000, 500)
R_fixed = 50e3
Pr_Pt = (Pt_values * G**2 * lambda_**2 * sigma) / (pi4 * R_fixed**4)

plt.figure(2)
plt.plot(Pt_values, Pr_Pt)
plt.xlabel("Power Transmitted")
plt.ylabel("Power Received")
plt.title("Received Power vs Transmitted Power")
plt.grid(True)

G_values = np.linspace(5, 60, 500)
Pt_fixed = 3000
Pr_G = (Pt_fixed * G_values**2 * lambda_**2 * sigma) / (pi4 * R_fixed**4)

plt.figure(3)
plt.plot(G_values, Pr_G)
plt.xlabel("Gain")
plt.ylabel("Power Received")
plt.title("Received Power vs Antenna Gain")
plt.grid(True)

plt.show()
```

__Output__:
   
<img width="1158" height="835" alt="image" src="https://github.com/user-attachments/assets/d0d8553b-6236-4f66-bd9d-90399ac977a0" />



<img width="1094" height="828" alt="image" src="https://github.com/user-attachments/assets/a7261c1d-0a30-44f7-89a8-288c6356782b" />



<img width="1082" height="840" alt="image" src="https://github.com/user-attachments/assets/89a8d24f-bb1a-434c-b8bc-a96e64341cbc" />




__Result__:
   

The maximum range of the radar system was successfully calculated using the Radar Range Equation and verified through Python programming.


