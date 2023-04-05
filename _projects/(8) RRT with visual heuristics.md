---
name: RRT with visual heuristics 
tools: [python, pygame]
image: /images/icon_rrt.gif
description: Designed path-finding RRT algorithm with heuristics based on a visual classifier.
---

# RRT with visual heuristics 
Designing and developing a path-finding RRT algorithm with heuristics based on a visual classifier.

### Problem Domain
- Domain is a 2D maze with obstacles the agent must go around to reach the goal.
- Discrete action space - front, back, left, right, move, stop.
- Different variants of domain include static/dynamic obstacles, start locations, and goal locations.

### Implementation
- Expert trajectories are automatically generated for the image classifier.
- Base RRT is run in a dynamic or static environment to find an expert trajectory.
- Every step along this trajectory from start to goal, the picture of the environment is saved along with the action taken by the agent as training/test data for the image classifier neural network.
- A CNN model is trained with this data to predict action from current state.

### Results
![preview](/images/rrt_results.png)  <br>



<p class="text-center">
{% include elements/button.html link="https://github.com/Pavan-pk/RRT-with-visual-heuristics" text="Project repository" %}
</p>