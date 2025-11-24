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
   
_PROGRAM_:
```
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
   
<img width="583" height="455" alt="image" src="https://github.com/user-attachments/assets/ca95646f-4418-4863-bdfb-0b0120ce10fd" />

<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/b3a19108-9f39-4b86-a3d0-37ef72135f10" />

<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/2044ed6b-5a7d-4e86-b602-5dac7f47c26e" />





   __Result__:
   
The maximum range of the radar system was successfully calculated using the Radar Range Equation and verified through Python programming.



