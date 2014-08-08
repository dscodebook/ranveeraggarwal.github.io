---
layout: projects
title: Monorail Controller
subtitle: Simulation of a Monorail Controller in VHDL
category: projects
---

###Description
A monorail system (or any software-operated system) can be modelled, to some extent as a Finite State Machine (FSM). Basically, that means, that you can model it as combination of states and transition function between those states. I modelled one such system in VHDL which was interfaced with a Spartan (Xilinx) FPGA.

---
###The State Machine - Explained
I assume the train to start at a station. There it waits for 20 clock cycles and then tries to close the doors. If there is someone blocking the door, then it waits for the person to get in. If not, the door closes. Then the train waits for a green signal. This is because I don’t want the signal system to get desynchronised (if the door closes after the green signal, the system by which the signals change would become very complicated). On the door close it starts off its engine and begins accelerating once the signal turns green. It accelerates until it reaches a saturation velocity. It then moves with that velocity. If a station is nearby, it starts de-accelerating at double the rate it accelerated and finally stops on arrival and this goes on. In addition, I have another variable that determines the direction in which the train goes – this determines in turn that which engine of the train must be running (The train has a front and a rear engine).

---
###Inference
In this project, I simulated the Mumbai Monorail as an FSM and tried to cover all the cases wherein the simulation can go faulty. The most important thing is that the train must not get too much delayed and must move as fast as possible between different stations to optimise travel time, which is covered well in this project.

---
###Project Report
THe project report (PDF) can be found [here](https://drive.google.com/file/d/0B59e9Iwu1fbJMDFTTUJ6N1N3RFU/edit?usp=sharing).
