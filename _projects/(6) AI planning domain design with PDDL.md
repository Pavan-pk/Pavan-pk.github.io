---
name: AI - Planning domain design using PDDL
tools: [PDDL]
image: /images/PDDL_image.png
description: Designing various planning domains and actions sets for problems ranging from simple switches to logistics with durative constraints.
---

# AI - Planning domain design using PDDL
This project involves designing the domain aswell as problem definition for switch and logistics problem with duration actions and minimum delivery time constraints.<br>
I have used PDDL 2.1 to define the above mentioned parts of the project.<br>

### Problem 1 - Tricky switch domain
- A switch can be toggled.
- There are 10 switches
- The ten switches are in initial positions: {on, off, on, off, off, on, off, off, on, off}.
- A switch can only be switched on if it has exactly one neighbour that is already on.  
<br>

### Problem 2 - Basic logistics domain
Diagram below gives set of locations and paths.<br>
![preview](/images/basic_logistics.png)  

Actions: <br>
- Packages can be loaded into and out of trucks (a driver does not have to be present).
- Drivers can walk between connected locations.
- Drivers can get into and out of trucks.
- A truck with a driver inside can move between connected locations.<br>

Objects:
- Two drivers
- Two trucks
- Four packages
- Eleven locations<br>

Initial state:
- The drivers are in locations {wp1, wp4}
- The trucks are in locations {wp6, wp9}
- The packages are in locations {wp2, wp3, wp5, wp11}

Goal state:
- Both drivers must be home in wp1.
- The packages must be in their destination locations:
- package 1 and 3 in location wp9
- package 2 and 4 in location wp2  
<br>

### 3. Logistics domain with durative actions and timed delivery constraints.
Below Diagram gives a description of the problem. <br>
![preview](/images/Planning_domain.png)  

Following were the addition to the basic logistics domain:

- Packages can be loaded into and unloaded from trucks (10 time units).
- Drivers can walk between connected waypoints (at a speed of 0.5).
- Drivers can get into and out of trucks (10 time units).
- Trucks with drivers can drive between connected waypoints (at a speed of 1).
- The boat and the plane don’t need drivers to move.
- They can only travel over the blue and yellow edges (connected to the lighthouse and the sky). Trucks can only travel on roads.
- The boat travels at a speed of 1.5.
- The plane travels at a speed of 2.  
<br>

<p class="text-center">
{% include elements/button.html link="https://github.com/Pavan-pk/PDDL_planning" text="Project repository with PDDL code and generated plans." %}
</p>