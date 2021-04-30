<!----Smart Charging Wizard---->
_A Lightweight User Interface for Cloud-based Smart Charging of Electric Vehicles_
_____________________

# Why should you use the Smart Charging Wizard? 🤔
Smart charging, i.e. the controlled and coordinated charging of Electric Vehicles (EVs) seems promising for efficient electric mobility. 
According concepts, however, require sufficient user acceptance. 
For this purpose, the Smart Charging Wizard provides a lightweight User Interface (UI) that makes smart charging more transparent.
In particular, the utilization of energy and time flexibilities in EV charging events to reduce both EV operating cost and battery aging is illustrated.  
____________________

# What do you have to put into the Smart Charging Wizard? 📥
Once you parked your EV at a charging station, you may calculate a charging event for various input parameters, these comprise:
- Your desired time of departure
- Your desired State of Charge (SOC) at departure
- A dynamic electricity tariff, if applicable
- The specifications of your EV

The following screencast presents the input page of the Smart Charging Wizard, and how to set the aforementioned inputs:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/input.gif)
_____________________

# What magic does the Smart Charging Wizard do? 🧙
is a web app with a back end optimization module and a front end . 

> TBD: motivation and short intro


- runs optimization scheme to minimize both battery aging costs and electricity costs
- considers dynamic behavior of the EV battery
- respects the constraints given by you (time and SOC) and the EV (battery capacity, charging power)

> TBD: GIF of starting calculation and result page
![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/result.gif)
_____________________

# How does it help you to charge your EV? 🔌
> TBD: GIF of starting the charging event and charging page

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/charging.gif)

_____________________

# What's behind the magic of the Smart Charging Wizard? 💡
The following figure shows an overview of the IoT architecture and the participants in the context of the Smart Charging Wizard:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/70c1f9599fd206746cd8a929149cdf7edcf377c5/media/architecture.jpg)

- EV user interacts with the Smart Charging Wizard via a smart device using HyperText Transfer Protocol (HTTP)
- Smart Charging Wizard runs together with a Charging Session Handler (CSH) and a Message Queuing Telemetry Transport (MQTT) server in a cloud environment
- MQTT server establishes communication between web app, CSH, and a Programmable Logic Controller (PLC) via JavaScript Object Notation (JSON) encoded messages
- For communication between the PLC and the charging station, we choose the User Datagram Protocol (UDP)
- The PLC sets the current at the charging station using the International Electrotechnical Commission (IEC) 61851 standard, receives the charging station’s actual status and measurements, and forwards them via MQTT to the Smart Charging Wizard

_____________________
# Who contributed? 🤝

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
# Where else should you have a look at? 🔎
[Streamlit](https://docs.streamlit.io/en/stable/)

[Casadi](https://web.casadi.org/docs/)
____________________
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fenergylabsmartcharging.github.io%2FSmart-Charging-Wizard&count_bg=%231A12D9&title_bg=%23D91212&icon=&icon_color=%23E7E7E7&title=clicks&edge_flat=false)](https://hits.seeyoufarm.com)
____________________
