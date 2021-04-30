<!----Smart Charging Wizard---->
_A Lightweight User Interface for Cloud-based Smart Charging of Electric Vehicles_

_____________________

# Why should you use the Smart Charging Wizard? 🤔
Smart charging, i.e. the controlled and coordinated charging of Electric Vehicles (EVs) seems promising for efficient electric mobility. 
According concepts, however, require sufficient user acceptance. 
For this purpose, the Smart Charging Wizard provides a lightweight User Interface (UI) that makes smart charging more transparent.
In particular, the utilization of energy and time flexibilities in EV charging events to reduce both EV operating cost and battery aging is illustrated.  

_____________________

# What do you have to put into the Smart Charging Wizard? 📥
Once you parked your EV at a charging station, you may calculate a charging event for various input parameters, these comprise:
- Your desired time of departure
- Your desired State of Charge (SOC) at departure
- A dynamic electricity tariff, if applicable
- The specifications of your EV

The following screencast presents the **Input Page** of the Smart Charging Wizard, and how to set the aforementioned inputs:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/input.gif)

_____________________

# What magic does the Smart Charging Wizard do? 🧙
The Smart Charging Wizard is a container-based web app written in [_Python_](https://www.python.org/).
It contains a [_CasADi_](https://web.casadi.org/docs/) optimization module and a [_Streamlit_](https://docs.streamlit.io/en/stable/) front end.
Once you hit the **Calculate**-Button, the optimization scheme is run to reduce both battery aging and electricity costs. 
This can be achieved by adapting the charging power of your EV for specific points in time while considering the dynamic behavior of the EV battery.
Furthermore, the Smart Charging Wizard respects all constraints given by you (departure time and SOC) and the EV (battery capacity, charging power).
Finally, the results are prompted as a table and some plots on the **Result Page**.
See the following screen cast: 

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/result.gif)

_____________________

# How does it help you charge your EV? 🔌
If you like what the Smart Charging Wizard calculated for you, the actual charging process may be started.
To adapt, monitor, or stop the charging process later or from another device, you can enter an optional session token, e.g. your name. 
Or, if you just want to get it on, hit the **Start Charging**-Button. 
The Smart Charging Wizard will then send the calculated charging power profile to a second backend service called Charging Session Handler (CSH). 
While you are doing other important things, the CSH takes care of charging your EV.
On the **Charging Page**, you can monitor the charging process in real time and immediately stop it, if your plans change suddenly. 
See the following screen cast for the details:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/6c274b0225123d3fd3d3701204e47932c255ba1d/media/charging.gif)

_____________________

# What's behind the magic of the Smart Charging Wizard? 💡
If you now wonder, how all of that might work, here's some more insight.
You interact with the Smart Charging Wizard, e.g. via a smart device using HyperText Transfer Protocol (HTTP).
The Smart Charging Wizard runs together with the Charging Session Handler (CSH) and a Message Queuing Telemetry Transport (MQTT) server in a cloud environment.
Each service is containerized by means of [_Docker_](https://www.docker.com/) and deployed on a [_Kubernetes_](https://kubernetes.io/) cluster.
Via JavaScript Object Notation (JSON) encoded messages, the MQTT server establishes communication between Smart Charging Wizard, CSH, and a Programmable Logic Controller (PLC).
For communication between the PLC and the charging station, we choose the User Datagram Protocol (UDP).
The purpose of the PLC is to set the current at the charging station using the International Electrotechnical Commission (IEC) 61851 standard.
Furthermore, the PLC receives the charging station’s actual status and forwards it via MQTT to the Smart Charging Wizard.

That was too fast? Check out the following figure that shows an overview of the IoT architecture and the participants in the context of the Smart Charging Wizard:

![](https://github.com/EnergyLabSmartCharging/Smart-Charging-Wizard/blob/8dce2833825fdf344c203d58fb93a3f86bf30572/media/architecture.jpg)

_____________________

# Who contributed? 🤝
Of course, all of that magic could not have been achieved without many hands working togehter.
Don't miss the following list of contributors with their major task and affiliation:

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
Source Code (_Coming Soon!_)

[Paper on the Maths](https://arxiv.org/abs/2009.12201) (Preprint)

Paper on the Architecture (_Coming Soon!_)

Our Test Environment: The [Energy Lab 2.0](https://www.elab2.kit.edu/index.php) at the [Karlsruhe Institute of Technology](https://www.kit.edu/english/index.php)

[Python](https://www.python.org/)

[Streamlit](https://docs.streamlit.io/en/stable/)

[CasADi](https://web.casadi.org/docs/)

[Docker](https://www.docker.com/) 

[Kubernetes](https://kubernetes.io/)

_____________________

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fenergylabsmartcharging.github.io%2FSmart-Charging-Wizard&count_bg=%231A12D9&title_bg=%23D91212&icon=&icon_color=%23E7E7E7&title=clicks&edge_flat=false)](https://hits.seeyoufarm.com)

_____________________

