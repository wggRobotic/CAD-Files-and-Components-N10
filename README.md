# Robot components

Here you will find all the essential components of our robot N-10 available as .stl and .stp files, enabling anyone to build and modify the robot. 

Our robot is a rover featuring a Rocker-Bogie suspension system, inspired by the Mars rovers and the open-source project [Stair Climbing Rover](https://www.printables.com/model/194299-stair-climbing-rover) by WildWilly. The components have been modified, supplemented, and completely redesigned to suit our specific needs.

![N-10_frontview](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/bf1c7328-c23e-4cbe-af66-96450a57053e)

## Main Body Structure

The main body of the rover is assembled using aluminum extrusions from [Makerbeam](https://www.makerbeam.com/makerbeam-makerbeam-regular-starter-kit-black.html). This design choice ensures a stable, robust, yet lightweight framework for the robot.

Most of the other components are designed for 3D printing and can be assembled using M3, M2.5, or M2 machine screws. For additional stability and support, the servomotors, motor mounts, and wheel hubs are anchored in the plastic using [M3 heat-set inserts](https://www.amazon.de/ruthex-Gewindeeinsatz-St%C3%BCck-Gewindebuchsen-Kunststoffteile/dp/B08BCRZZS3/ref=sr_1_5?crid=17XN2W9D8KS40&dib=eyJ2IjoiMSJ9.chJHNCet5aQ0sdjbprRc9YiyWImaSKCMgxzpF0Odb6mG3Uw6O4oPoJGumEcnij26fxHUnqFu4xEbCiukhTJEgfRtwTroXTYtp6I2u7Oj8ezBf8J0Vm2ra-8HVxpufjoTbuTRTPW0PJ-YRjcHVb0n2xf97lAt-PJU9hZ8-PSX64yPoOslK6qB0rIqrohywO-fdkR2HRTEM7-HABXztPI6a5ZQvwsfHOoXDcItj80shxqz2-HefZcCygZ-Q3RW8Awk-ppkOqzjRlWHilI-Uu6TwTb-dIYF8T5-GOBviLdMch0.EocP6OkBp9Vki3ejz39Wx-2732BW1RPTk52ZiD_WocI&dib_tag=se&keywords=m3%2Bheat%2Binsert&qid=1719955437&s=industrial&sprefix=m3%2Bheat%2Cindustrial%2C75&sr=1-5&th=1).

Material Recommendations:

  + Load-bearing components: PETG
  + Decorative/Chassis components: PLA (sufficient for parts that do not bear heavy loads)

Enjoy building and customizing your own robot!

![N-10_backview](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/c757f021-7299-4b9a-96bc-98f256b3cafd)


## Wheel Control and Alignment

The control and alignment of each wheel are managed by Hobby servomotors of the type MG996 [amazon link](https://www.amazon.de/AZDelivery-Digital-Getriebe-Hubchrauber-Flugzeug/dp/B07H89JH74/ref=sr_1_2?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=20UB04WN0BON9&dib=eyJ2IjoiMSJ9.jMjuySQHT6p8VIY-ZIwi8eP9WQJ9V1MrcKxaDV1JJg4PRRWaKzoqgBB9yN_9xgObVnsSbaOOko2qLZnxiPspi8gaGecjEiFInNaGroJ06pNMcJr5EKOoNp8pfKIAUZGuqwX5CWbhRgeHcCt37xzNel7SX5nhwR0ZShuztfvetHMurphIKWJllOyqCvQf4yk7g2I_1_g6FaLOq8EPZrDAzRy_pexkP4v7pn-SU7T0fBnbm6birAZ4GndJXkDXJ2S_mEUkR-qhmcHrf41Jt7gBGO1_OqcaoRwtFx7SWKjT7cI.OOeIdcPjQSuF0THw2KD0bblc1hnfhNPcDn3p2AsPUf0&dib_tag=se&keywords=MG996&qid=1719952179&sprefix=mg996%2Caps%2C144&sr=8-2&th=1). These servomotors are addressed via I2C through an Adafruit PCA9685 servo board.

![Radsteuerung](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/d4700c3a-2e6c-459a-99f7-2b8c3054262d)

The wheel and motor mounts, as well as the wheel hubs, are specially designed for our purposes and printed from PETG. Due to space constraints, the motor mounts needed to be fabricated from steel to prevent rotation, as a printed part with a thickness of 2mm would not provide the necessary strength.

![Halterung](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/f9dd840f-60f2-4c2c-aabc-091eb7804936)

![Radaufnahme](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/e1395c14-dbce-42e0-9259-59804debf6c9)



## Motors and motorcontrol
Our six wheels are powered by Faulhaber DC motors with planetary gearboxes [2224U018S R IEH2-512 22GPT 44:1](https://www.faulhaber.com/de/produkte/serie/22gpt/), generously provided by Faulhaber for this project. Motor control and regulation, as well as the power supply for other components, are handled by a Kinematics Kit, kindly provided by [EduArt Robotik](https://www.eduart-robotik.com/). This kit is designed to be mounted on a Raspberry Pi 4 or [5](https://www.berrybase.de/raspberry-pi-5-8gb-ram) and can be expanded modularly. The basic components of the kit include:

+ Adapter Board either directly pluggable onto a Raspberry Pi 4/5 or as a standalone EduArt Ethernet controller board, with which you can connect any computer with an Ethernet interface. This gives you the freedom to build the computing power into your robot that you need for your desired application. This board is supplied via the socket strips, i.e. a circuit board with the appropriate sockets for a power supply unit or a battery should be used. The possible input voltage Vin is 12V to 55V. Depending on how many motors are connected, the power supply must be able to supply higher currents. High-current batteries are recommended for operating a robot (min. 8A).

+ Motorcontrollers can be plugged in directly. This allows you to control the speed of 1 to 8 motors. The motor controllers are available in two versions, single-channel or dual-channel. Up to four motor controllers can be used, i.e. it is possible to use 1 to 4 larger motors (IRMS up to 5A) or 1 to 8 smaller motors (IRMS up to 2.5A). The dielectric strength of the single-channel motor controllers is 55V. The dielectric strength of the dual-channel motor controllers is 35V.

+ The Power Management Module takes over the charge control of a 19.2V NiMH battery pack and also offers an on/off logic. Temperature monitoring of the battery uses an integrated 6.8kOhm NTC. Never connect a battery other than the one supplied by EduArt.
    
+ The Auxiliary Power Supply Module provides additional voltage levels with which you can supply additional devices. The permissible operating voltage is between 15V and 36V.

Warning: The Raspberry single-board computer is supplied directly via the socket connectors. Never connect an external power supply for the Raspberry via USB-C.

![Free_Kinematics_Kit_1920](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/0ba67526-036f-4526-a45c-32b8420f3916)

![Free_Kinematics_Kit_Electrical_Interface_Desc_1920](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/a908d785-35f4-4d51-8ecc-d744f49c71be)

## Power Supply

The power and voltage supply is provided by a NiMH, 19.2V, 4.5 Ah battery pack. Although Nickel-Metal Hydride batteries are significantly heavier than comparable Li-ion batteries, they have much lower risks of fire and explosion. Additionally, these batteries are more maintenance-friendly, which outweighs the disadvantages for us. For powering the Raspberry Pi 5 and the servomotors, the voltage is stepped down using DC-DC converters, as described in the Motor Control section. Specifically, for powering the servomotors, we use an additional DC-DC converter [UWS-5/10-Q12P-C](https://www.digikey.de/de/products/detail/murata-power-solutions-inc/UWS-5-10-Q12P-C/10427628) on our board that supplies the servos on the PCA9685 board with 5V at 10A as an external power source.

## Cameras and Camera Feed

The robot is equipped with three cameras:

+ Front Cameras: Mounted on the robot arm are an [Intel RealSense D435](https://www.amazon.de/Intel-RealSense-82635AWGDVKPRQ-Erfassung-beweglicher/dp/B07BLS5477) and a [Waveshare MLX90640](https://www.amazon.de/Waveshare-MLX90640-Communicating-Interface-Raspberry/dp/B07ZKK8QWY) thermal imaging camera, both facing forward.
+ Rear Camera: A USB camera module [OV2710](https://www.berrybase.de/usb-2.0-kameramodul-2-megapixel-ov2710-sensor-1450-low-light?number=USBCAM-OV2&utm_source=google&utm_medium=cpc&gad_source=1&gclid=CjwKCAjwyo60BhBiEiwAHmVLJcHQucbtdbESN0yuI6bVZ5HOoqdbWIbmEjVRBcczMSEdCzt6vbW_oBoCiiIQAvD_BwE) is used as a rearview camera.

All cameras have been recycled from older projects.

In our GUI, users can switch between the different camera feeds with the press of a button.

## Simple Robot Arm Assembly

This section provides a brief description of the simple robot arm mounted on the N10 robot. 

![Arm_topview](https://github.com/wggRobotic/CAD-Files-N10/assets/120591442/d316788a-5b93-4feb-8acc-bedf19230b7c)

The main components include:

+ Two powerful [Servomotors](https://www.amazon.de/ANNIMOS-Servomotor-Drehmoment-Vollmetallgetriebe-Montagehalterungen/dp/B0C69NNP9P/ref=sr_1_3_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=UCIEWCEVMBRO&dib=eyJ2IjoiMSJ9.eTzcKcyFLjDNHDpnPQZJRfFhKbAR_WBfuoLJeXxlH6KBujWXHRrs_x90tFlDvEu367pgTSnAFVVGcFjP9yLmQUbCXhf3vvwoP0qKpWB9hCGZbYcZBGu33ggxs5dtio-8DiRSc_nJy1WuIdFL93Eo1WjrbN1Ju_cae9FhVhUSpF7Wco-Wh4DlLKj_jMu_KlCgu9w2U5_rPTc_Jl4Hmu8ZmZezD00Ck7NDL44A_NYS0yS2ToD6ZyOGd-OXaLEs4ESttlNLcq0g_ZLHrUHcIDhI1RwBdlwq0DrzhIh03Zq-7p0.Mx7QMXx5J2M_lZuvLIVTyTHeCN6Ae1HbLnZYiZIw5Jo&dib_tag=se&sprefix=servo%2Caps%2C106&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY) with aluminum brackets: These form the basic structure of the arm. 

+ Camera Module: Equipped with an [Intel-RealSense D435](https://www.amazon.de/Intel-RealSense-82635AWGDVKPRQ-Erfassung-beweglicher/dp/B07BLS5477/ref=sr_1_1?crid=3KMNU2EF5XETZ&dib=eyJ2IjoiMSJ9.p-wzVPg_w5n9smo8CAmUAmRTBOyszuqXzuvq7Murz5eZTBwt9a1uKVtMttfcG6_I7w4RY7rotHaA59tmr3-tyx7jGvyHzPeWoATC433wU_k.BqajalRkjcJpVI9YPAtI4ZiZLPEulvg62Qicgw8WWLg&dib_tag=se&keywords=intel%2Brealsense%2Bd435&qid=1719951552&sprefix=intel%2Breal%2Caps%2C105&sr=8-1&th=1) camera and a thermal imaging camera module ([Waveshare MLX90640](https://www.amazon.de/Waveshare-MLX90640-Communicating-Interface-Raspberry/dp/B07ZKK8QWY)).
  
+ Gripper: A simple gripper controlled by a [9g servomotor](https://www.amazon.de/Miuzei-Hubschrauber-Helikopter-Fahrzeugmodelle-Steuerung/dp/B07KPS9845/ref=sr_1_1_sspa?dib=eyJ2IjoiMSJ9.lygpGv5pFROZz7M3BpIC1HiLKXb8VI47frXlfyK9FP0EpUpopKclBeyTEdA92TkooSRaof66bFbMhb9mVahZZQwGlvJTlpNccGZH2MtS3z76oD2dpTvudjy5K5gDB2Wr7MlMHtJaimLiWz-Rv4tI9Z06j2mWLTuhrNQy7_LjsbTf-dPUs_04aYF955WEfz6kUMepedn4It269E7F6XvArZnCpvwsF8BRg7haZXndgPfpS1oXfU-hz-jI7td05NRu4gE7FMrwZqM0f-AkCuE04ffQQyT7XRBZYd0V2rG-hEk.TqNgT7w-e1UQIRFZTIPoaH47vqUAJO5tFQxCZdYmF_E&dib_tag=se&keywords=9g+servo&qid=1719951774&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1).
  
+ Control: The arm is controlled via I2C using an [Adafruit PCA9685 servo board](https://www.amazon.de/PCA9685-16-Kanal-12-Bit-Arduino-Robort/dp/B07Y9PTY12/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=1H58JK0GL9NFW&dib=eyJ2IjoiMSJ9.sjVEWI4eKRct-eZBQe_falPylAAwfhP8vZm8uHwHw66MRq0ATak9f7IIULp36zjukcF5EAij4hVMcSNmdBgMud2f-AMP_C3jbILbSyO9KD9OGyWViLzLGNoxXIqxymJ1gFsvUm8Q7Ir2M-0g2c2kmnue8tN2o81HSOSYR3C1--mLdxFhAHc_zcR0KkqPxyjhoQd1BjaoIHVv59fo3a8INueA9dn1atLidDkxX4F7HrQ.-r1tciRJ8uMP2lGuUtUHNLkgY6wIfp8SJxpd5GLO-9s&dib_tag=se&keywords=PCA9685&qid=1719951819&sprefix=pca9685%2Caps%2C81&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1).


## Component-list

Component | Unit price | Quantity | Total price | Note
-------- | :--------: | :--------: | :--------: | --------
MG996 - Servomotor   | 6.00 €   | 6 | 36.00 €   | [Amazon](https://www.amazon.de/AZDelivery-Digital-Getriebe-Hubchrauber-Flugzeug/dp/B07H89JH74/ref=sr_1_2?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=20UB04WN0BON9&dib=eyJ2IjoiMSJ9.jMjuySQHT6p8VIY-ZIwi8eP9WQJ9V1MrcKxaDV1JJg4PRRWaKzoqgBB9yN_9xgObVnsSbaOOko2qLZnxiPspi8gaGecjEiFInNaGroJ06pNMcJr5EKOoNp8pfKIAUZGuqwX5CWbhRgeHcCt37xzNel7SX5nhwR0ZShuztfvetHMurphIKWJllOyqCvQf4yk7g2I_1_g6FaLOq8EPZrDAzRy_pexkP4v7pn-SU7T0fBnbm6birAZ4GndJXkDXJ2S_mEUkR-qhmcHrf41Jt7gBGO1_OqcaoRwtFx7SWKjT7cI.OOeIdcPjQSuF0THw2KD0bblc1hnfhNPcDn3p2AsPUf0&dib_tag=se&keywords=MG996&qid=1719952179&sprefix=mg996%2Caps%2C144&sr=8-2&th=1)
ANNIMOS 25kg Servomotor   | 29.98 €   | 2 | 59.96 €   | [Amazon](https://www.amazon.de/ANNIMOS-Servomotor-Drehmoment-Vollmetallgetriebe-Montagehalterungen/dp/B0C69NNP9P/ref=sr_1_3_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=UCIEWCEVMBRO&dib=eyJ2IjoiMSJ9.eTzcKcyFLjDNHDpnPQZJRfFhKbAR_WBfuoLJeXxlH6KBujWXHRrs_x90tFlDvEu367pgTSnAFVVGcFjP9yLmQUbCXhf3vvwoP0qKpWB9hCGZbYcZBGu33ggxs5dtio-8DiRSc_nJy1WuIdFL93Eo1WjrbN1Ju_cae9FhVhUSpF7Wco-Wh4DlLKj_jMu_KlCgu9w2U5_rPTc_Jl4Hmu8ZmZezD00Ck7NDL44A_NYS0yS2ToD6ZyOGd-OXaLEs4ESttlNLcq0g_ZLHrUHcIDhI1RwBdlwq0DrzhIh03Zq-7p0.Mx7QMXx5J2M_lZuvLIVTyTHeCN6Ae1HbLnZYiZIw5Jo&dib_tag=se&sprefix=servo%2Caps%2C106&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)
9g Micro Servomotor  | 2.00 €   | 1 | 2.00 €   | [Amazon](https://www.amazon.de/Miuzei-Hubschrauber-Helikopter-Fahrzeugmodelle-Steuerung/dp/B07KPS9845/ref=sr_1_1_sspa?dib=eyJ2IjoiMSJ9.lygpGv5pFROZz7M3BpIC1HiLKXb8VI47frXlfyK9FP0EpUpopKclBeyTEdA92TkooSRaof66bFbMhb9mVahZZQwGlvJTlpNccGZH2MtS3z76oD2dpTvudjy5K5gDB2Wr7MlMHtJaimLiWz-Rv4tI9Z06j2mWLTuhrNQy7_LjsbTf-dPUs_04aYF955WEfz6kUMepedn4It269E7F6XvArZnCpvwsF8BRg7haZXndgPfpS1oXfU-hz-jI7td05NRu4gE7FMrwZqM0f-AkCuE04ffQQyT7XRBZYd0V2rG-hEk.TqNgT7w-e1UQIRFZTIPoaH47vqUAJO5tFQxCZdYmF_E&dib_tag=se&keywords=9g%2Bservo&qid=1719951774&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)
EduArt Kinematics Kit  | 786.75 €   | 1 | 786.75 €  | [Eduart Robotik](https://www.eduart-robotik.com/)
Faulhaber DC motors with planetary gearboxes  | 209.20 €   | 6 | 1255.20 €   | [2224U018S R IEH2-512 22GPT 44:1](https://www.faulhaber.com/de/produkte/serie/22gpt/)
Raspberry Pi 5 8Gb  | 86.50 €   | 1 | 86.50 €   | [berrybase](https://www.berrybase.de/raspberry-pi-5-8gb-ram) 
Intel RealSense D435 | 343.92 € | 1 | 343.92 € | [Amazon](https://www.amazon.de/Intel-RealSense-82635AWGDVKPRQ-Erfassung-beweglicher/dp/B07BLS5477?th=1)
Waveshare MLX90640 | 71.99 € | 1 | 71.99 € | [Amazon](https://www.amazon.de/Waveshare-MLX90640-Communicating-Interface-Raspberry/dp/B07ZKK8QWY)
USB camera module OV2710 | 33.40 € | 1 | 33.40 € | [berrybase](https://www.berrybase.de/usb-2.0-kameramodul-2-megapixel-ov2710-sensor-1450-low-light?number=USBCAM-OV2&utm_source=google&utm_medium=cpc&gad_source=1&gclid=CjwKCAjwyo60BhBiEiwAHmVLJcHQucbtdbESN0yuI6bVZ5HOoqdbWIbmEjVRBcczMSEdCzt6vbW_oBoCiiIQAvD_BwE)
PCA9685 Servomotor Drive Module | 6.50 € | 1 | 6.50 € | [Amazon](https://www.amazon.de/PCA9685-16-Kanal-12-Bit-Arduino-Robort/dp/B07Y9PTY12/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=1H58JK0GL9NFW&dib=eyJ2IjoiMSJ9.sjVEWI4eKRct-eZBQe_falPylAAwfhP8vZm8uHwHw66MRq0ATak9f7IIULp36zjukcF5EAij4hVMcSNmdBgMud2f-AMP_C3jbILbSyO9KD9OGyWViLzLGNoxXIqxymJ1gFsvUm8Q7Ir2M-0g2c2kmnue8tN2o81HSOSYR3C1--mLdxFhAHc_zcR0KkqPxyjhoQd1BjaoIHVv59fo3a8INueA9dn1atLidDkxX4F7HrQ.-r1tciRJ8uMP2lGuUtUHNLkgY6wIfp8SJxpd5GLO-9s&dib_tag=se&keywords=PCA9685&qid=1719951819&sprefix=pca9685%2Caps%2C81&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
Black Starter Kit Regular MakerBeam  | 117.95 € | 1 | 117.95 € | [Makerbeam](https://www.makerbeam.com/makerbeam-makerbeam-regular-starter-kit-black.html)
Maschine screws (M2, M2.5 M3) | 24.65 € | 1 | 24.65 € | [Amazon](https://www.amazon.de/Edelstahl-Sechskopf-Knopf-Schrauben-Unterlegscheiben-Sortiment-Aufbewahrung/dp/B07FPGNTXD/ref=sr_1_1_sspa?crid=2UL3AQDCLIF90&dib=eyJ2IjoiMSJ9.pILkoNUYORKH02omgGo1XNmNFckv_8r9HRLXB9li4dhKD-Ew3TvRDzX5WsXYpMcyR8zW5dlMc61tFv4yNgacQs4yQz8S5GYLCmXaSG4gTVPYUQrHYS2nP6LvB7f1n4acfrp6UgmVXTm97_zJVL36W4Ti8y7QKyLGJkrfBnkcj7y6--g_K8i0BgHs6LCgmP6eKVjnnbwq97OfUoSA1sHhrcUDbwSiHQQu-_eFwE_Xz-vYNFDuwFN40lp9-WCoviQIXFpM4xNp6d1dUk7MaPbL1-ZpcDyUFfrZiVAXLR3V5OA.Dm0YttZ6EzuYx8afRyiYxNxK4RdZVS_piXpbV0i4MLU&dib_tag=se&keywords=m3%2Bschrauben%2Bset&qid=1720015943&sprefix=m3%2Bschr%2Caps%2C80&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)
Heat-Set Inserts | 8.99 € | 1 | 8.99 € | [Amazon](https://www.amazon.de/ruthex-Gewindeeinsatz-St%C3%BCck-Gewindebuchsen-Kunststoffteile/dp/B08BCRZZS3/ref=sr_1_5?crid=17XN2W9D8KS40&dib=eyJ2IjoiMSJ9.chJHNCet5aQ0sdjbprRc9YiyWImaSKCMgxzpF0Odb6mG3Uw6O4oPoJGumEcnij26fxHUnqFu4xEbCiukhTJEgfRtwTroXTYtp6I2u7Oj8ezBf8J0Vm2ra-8HVxpufjoTbuTRTPW0PJ-YRjcHVb0n2xf97lAt-PJU9hZ8-PSX64yPoOslK6qB0rIqrohywO-fdkR2HRTEM7-HABXztPI6a5ZQvwsfHOoXDcItj80shxqz2-HefZcCygZ-Q3RW8Awk-ppkOqzjRlWHilI-Uu6TwTb-dIYF8T5-GOBviLdMch0.EocP6OkBp9Vki3ejz39Wx-2732BW1RPTk52ZiD_WocI&dib_tag=se&keywords=m3%2Bheat%2Binsert&qid=1719955437&s=industrial&sprefix=m3%2Bheat%2Cindustrial%2C75&sr=1-5&th=1)
|  | |**TOTAL:** | 2833.81 € |

The total price of all components is very high, but most of the components are high-quality products that can usually be replaced very easily with comparable, significantly cheaper components. For example, simpler [Pololu motors](https://www.pololu.com/category/272/24v-37d-metal-gearmotors) can be used instead of Faulhaber motors. It should also be mentioned at this point that some of these components, like the Intel-Realsense D435, were already available from previous projects at our school and have now found a new use. We would also like to thank Faulhaber, EduArt Robotik and Siemens for making their components available to us free of charge.

## Software Control
For more details on software control, please refer to the software section.

