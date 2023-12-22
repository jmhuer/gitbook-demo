---
cover: ../.gitbook/assets/Screen Shot 2023-12-20 at 7.14.26 PM.png
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Robotics

### Robot and Drone Collaboration and Automation

This blog post is a glimpse into my journey exploring the applications of robots and drones within indoor environments. Throughout this post, I delve into the necessary steps and offer access to computer vision and control software.&#x20;

We consider various applications such as: senior care, general home assistance, security systems, drone signal routers, and food recognition using drone cameras. The projects covered here encompass both my industry endeavors at emerging tech labs and academic research labs. While I've shared these projects publicly, I've omitted certain details or code to honor industry confidentiality and non-disclosure agreements (NDAs).

The code for the work discussed here is available in the following repositories:

{% embed url="https://github.com/jmhuer/DJITelloAutonomy2" %}
Drone automation and collaboration codebase
{% endembed %}

{% embed url="https://github.com/srinithish/Smarttable" %}
Robotic hand codebase
{% endembed %}

### Applications of Robotic Arms

***

### Robotic xArm 6DOF

In today's manufacturing landscape, robotic arms are integral, serving various scales from intricate circuit board assembly to heavy-duty tasks like automotive production lines. At GE Appliances' Emerging Tech Group, we incorporated a simple robot arm (Robotic xArm 6DOF) into several experiences. In one instance, we integrated a camera and computer vision, enabling the arm to identify and reach for specific food items. Additionally, the robot arm was equipped with a speech recognition solution to facilitate communication with humans.  Furthermore, we did a proof of concept with the robot arm collaborating with a drone, Parrot Mambo, to deliver small food items to a nearby user.&#x20;

The repositories used for this demostration can be found here:

{% embed url="https://github.com/srinithish/Smarttable" %}

### UFACTORY xArm 7

The proof of concept with the Robotic xArm 6DOF served as an initial exploration, presenting several potential ideas within the organization. However, to delve into more substantial applications, our group transitioned to the UFACTORY xArm 7 robotic arm.

The UFACTORY xArm 7 boasts impressive reliability and precision, capable of repeating movements within 0.1 mm at a speed of 1 m/s. Engineered with a X86 chip, it adeptly manages control algorithms, ensuring precise motions. Featuring a compact powertrain joint, a self-developed outer rotor brushless motor, and an integrated harmonic drive, the xArm 7 offers heightened repeatability and torque capability. Equipped with a programmable gripper, this model allows control over its position, speed, and force, enabling effective performance across various tasks. It includes suction cups with a payload capacity of 4 kg and a maximum vacuum degree of -90kpa. Its functionalities span pick-and-place operations, packing, sorting, and more. Moreover, the device comes with a comprehensive set of add-ons, including a gripper, suction cup, and camera module, enhancing its versatility and applicability.

Below we have a video of our dishwasher unloading example:

{% embed url="https://www.youtube.com/embed/Nqcwmck2szk" %}

### Home Assistant Robot

***

We collaborated closely with the [FirstBuild Microfactory](https://firstbuild.com/) to engineer a robot from scratch, involving motor selection, battery mounting and wiring, and the design of a CAD frame using 80/20 t-slot materials. This design enables users to affix different mechanisms for diverse applications. Our skid-steer design facilitates 360-degree turns in confined indoor spaces, while its high payload capacity ensures the robot can transport heavy loads without torque stalling. Additionally, we integrated computer vision and incorporated drone loading capabilities to enable collaborative functions.

{% embed url="https://www.youtube.com/embed/bEvj1QQuPf4" %}

