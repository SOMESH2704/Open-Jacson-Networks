# Series Queues with infinite capacity - Open Jackson Network

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the each conveyor of (c) waiting time of each material in the system (d) waiting time of each material in each conveyor, if the arrival  of materials follow Poisson process with the mean interval time 12 seconds, service time of  lathe machine in series follow exponential distribution  with service time  1 second, 1.5 seconds and 1.3 seconds respectively and average service time of robot is 7 seconds.

## Software required :
Visual components and Python

## Theory

![image](https://user-images.githubusercontent.com/103921593/203239736-7b81f599-71a8-4ae7-b63e-5d98acd9ea54.png)


## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203239789-bc870dce-6727-487b-a0e2-4fc3f5114889.png)


## Experiment:

<img width="1038" height="613" alt="image" src="https://github.com/user-attachments/assets/2878f151-e81c-4539-911c-8f9e88a4a3d6" />

## Program
```

import math

ArrivalTime = float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ServiceTime1 = float(input("Enter the mean inter service time of Lathe Machine 1 (in secs): "))
ServiceTime2 = float(input("Enter the mean inter service time of Lathe Machine 2 (in secs): "))
ServiceTime3 = float(input("Enter the mean inter service time of Lathe Machine 3 (in secs): "))
RobotTime = float(input("Enter the Additional time taken for the Robot (in secs): "))

Lambda = 1 / ArrivalTime
Mu1 = 1 / (ServiceTime1 + RobotTime)
Mu2 = 1 / (ServiceTime2 + RobotTime)
Mu3 = 1 / (ServiceTime3 + RobotTime)

print("Series Queues with Infinite Capacity - Open Jackson Network")
print("The mean arrival rate per second               : %0.2f" % Lambda)
print("The mean service rate per second of Lathe 1    : %0.2f" % Mu1)
print("The mean service rate per second of Lathe 2    : %0.2f" % Mu2)
print("The mean service rate per second of Lathe 3    : %0.2f" % Mu3)


if (Lambda < Mu1) and (Lambda < Mu2) and (Lambda < Mu3):
    # Calculating performance metrics for each server
    Ls1 = Lambda / (Mu1 - Lambda)
    Ls2 = Lambda / (Mu2 - Lambda)
    Ls3 = Lambda / (Mu3 - Lambda)

    Ls = Ls1 + Ls2 + Ls3 

    Lq1 = Ls1 - Lambda / Mu1
    Lq2 = Ls2 - Lambda / Mu2
    Lq3 = Ls3 - Lambda / Mu3

    Wq1 = Lq1 / Lambda
    Wq2 = Lq2 / Lambda
    Wq3 = Lq3 / Lambda

    Ws = Ls / (3 * Lambda)

```
## Output

<img width="857" height="309" alt="image" src="https://github.com/user-attachments/assets/c50fc1a5-11f5-4417-b241-967957dd8db7" />

## Result

The average number of material in the system and in the conveyor and waiting time are successfully found.
