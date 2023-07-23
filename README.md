# Driver-Drowsiness-Detection
This project detects whether a driver is drowsy by using the Viola-Jones Algorithm to detect various features of the driver's face.

2 separate functions check the eyes and the mouth. Eye detection is done by looking for 2 dark spots(the eyes) split by a bright spot(the nose) since the eyes look darker than the nose and cheeks on video.

Here the program checks if the eyes are open or closed. It checks the amount of white pixels present within the area it perceives as the eyes. If there are a considerable amount of white pixels it means that the eyes are open otherwise the eyes are closed.

Mouth detection is done similarly to that of the eyes. The program looks for 2 dark spots(the eyes and the mouth) and a bridge in between(the nose and cheeks). The program checks if the mouth is open by checking if the lips are parted and if there are a considerable amount of white pixels between the lips(the teeth). If the lips are parted, the driver is yawning/talking.

These 2 programs are then combined to create a probability function to avoid wrong detection. The probability values are as follows

| Mouth  | Closing | Split |
|--------|--------:|------:|
| Eyes   |         |       |
| Open   |  100%   |  84%  |
| Close  |   50%   |  15%  |

Once the probability has been determined a random number is generated and the application checks in what range the number falls. It then gives the final verdict on whether the driver is drowsy or awake. Since the program runs a check constantly every second there is a very low chance of the application performing a wrong prediction constantly for a long period.

# How to run the application
Please run the DrowsinessDetection.m file first. This will open your webcam and start the detection process.
If you are facing any issues running this file make sure that you have downloaded the required packages for MATLAB to access your webcam.
You will be prompted to download the required packages in the error message.
