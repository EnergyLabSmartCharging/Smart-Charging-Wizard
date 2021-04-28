# Smart Charging Wizard 
_A Lightweight User Interface for Cloud-based Smart Charging of Electric Vehicles_
_____________________
-  is a web app with a back end optimization module and a front end User Interface (UI). 

> TBD: motivation and short intro
- utilization of energy and time flexibilities in charging events of Electric Vehicles (EVs)


## What information do you have to put into the Smart Charging Wizard?
- desired time of departure
- desired SOC at departure
- specifications of EV
- applicable electricity tariff

> TBD: GIF of inputs
![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/2b02231229afe39d7e31ad68062dedd161bc3271/SmartChargingWizardDemo.gif)
_____________________

## What magic does the Smart Charging Wizard do?
- runs optimization scheme to minimize both battery aging costs and electricity costs
- considers dynamic behavior of the EV battery
- respects the constraints given by you (time and SOC) and the EV (battery capacity, charging power)

> TBD: GIF of starting calculation and result page
![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/2b02231229afe39d7e31ad68062dedd161bc3271/SmartChargingWizardDemo.gif)
_____________________

## How does the Smart Charging Wizard help you to charge your EV?
> TBD: GIF of starting the charging event and charging page

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/2b02231229afe39d7e31ad68062dedd161bc3271/SmartChargingWizardDemo.gif)

_____________________

## What's behind the magic of the Smart Charging Wizard?
The following figure shows an overview of the IoT architecture and the participants in the context of the Smart Charging Wizard:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/641651377aedb4eb9a6a724ceae51873c04cb863/media/0001.jpg)

- EV user interacts with the Smart Charging Wizard via a smart device using HyperText Transfer Protocol (HTTP)
- Smart Charging Wizard runs together with a Charging Session Handler (CSH) and a Message Queuing Telemetry Transport (MQTT) server in a cloud environment
- MQTT server establishes communication between web app, CSH, and a Programmable Logic Controller (PLC) via JavaScript Object Notation (JSON) encoded messages
- For communication between the PLC and the charging station, we choose the User Datagram Protocol (UDP)
- The PLC sets the current at the charging station using the International Electrotechnical Commission (IEC) 61851 standard, receives the charging station’s actual status and measurements, and forwards them via MQTT to the Smart Charging Wizard

_____________________
## Contributions

[Stefan Meisenbacher, M.Sc.](https://github.com/smeisen) (Optimization Logic, _Karlsruhe Institute of Technology_)

[Karl Schwenk, M.Sc.](https://github.com/KarlSchwenk) (Frontend Implementation, _Karlsruhe Institute of Technology & Mercedes-Benz AG_)

Johannes Galenzowski, M.Sc. (Communication Concept, _Karlsruhe Institute of Technology_)

Tobias Moser, B.Eng. (Hardware Support, _Karlsruhe Institute of Technology_)

[Friedrich Wiegel, M.Sc.](https://www.iai.kit.edu/Ansprechpersonen_1554.php) (Hardware Support, _Karlsruhe Institute of Technology_)

Matthias Frey (Deployment Support, _Karlsruhe Institute of Technology_)

[Dr.-Ing. Simon Waczowicz](https://www.iai.kit.edu/Ansprechpersonen_2620.php) (Supervision, _Karlsruhe Institute of Technology_)

[Prof. Dr. Ralf Mikut](https://www.iai.kit.edu/Ansprechpersonen_1030.php) (Supervision, _Karlsruhe Institute of Technology_)

[Prof. Dr. Veit Hagenmeyer](https://www.iai.kit.edu/Ansprechpersonen_1213.php) (Supervision, _Karlsruhe Institute of Technology_)

_____________________
## References
Streamlit 
Casadi
____________________
