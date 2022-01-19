# CS 560 Assignment Animations and Images



## Geometric Planning

Here the robot can only translate in a 10x10 2D plane. The robot is a non symmetrically shaped polygon (triangle) with it's origin at it's left most point. We use minkowski addition using the robot's flipped polygon on the obstacles to get the configuration space of the problem.

The sampling based tree algorithm RRT and RRT* is shown in the following sections. It forms a tree data structure from the start position to the goal position and avoids all obstacles using collision checks at every sampled point.

### RRT

The following is the RRT algorithm. This is a sub-optimal but quite a fast algorithm.

<video src="https://user-images.githubusercontent.com/25320503/149968226-db68f83a-015e-445f-bd7d-14253c7b5768.mp4" controls="controls" style="max-width: 90vw;">
</video>

### RRT Star

This is an optimal algorithm, which uses rewiring technqiues within a region to find the best possible path amognst the discovered paths to the goal.

<video src="https://user-images.githubusercontent.com/25320503/150119283-c3fe6038-e523-42cc-b413-61a28e9f185c.mp4" controls="controls" style="max-width: 730px;">
</video>

#### Here the robot can translate and rotate in a 10x10 2D plane.

### RRT

![2_rrt](https://user-images.githubusercontent.com/25320503/149982090-d0de949f-20ce-4527-9d5c-d4a8ca58f414.png)

### RRT Star

![2_rrt_star](https://user-images.githubusercontent.com/25320503/149982250-653415d4-cfd6-4af9-9f23-09a98e0a8ba1.png)


## Kinodynamic Planning

### RRT with velocity as a control

1. Sample a random point
2. We find the nearest point on the tree to the sampled point
3. Sample 20 controls - linear and angular velocities.
4. Find the control which takes the robot closest to the random point (with collision checks)
5. Add that point to the tree 

Following is the demonstration.

<video src="https://user-images.githubusercontent.com/25320503/149969046-9544781a-4f8a-496e-9f0f-69d50564dca7.mp4" controls="controls" style="width:90vw; max-width: 730px;">
</video>

### RRT with acceleration as a control

I do the same thing as above, except we sample linear and angular accelerations, which take us closer to how they work in reality. 

<video src="https://user-images.githubusercontent.com/25320503/150120037-a6e1c646-c7b1-4c6e-87c4-09be51e2d2ba.mp4" controls="controls" style="max-width: 730px;">
</video>


## Localization

### Particle Filters

Sampling 100 particles around 100x100 space and using a sampling based approach to bayes filters to localize the robot in this space.


<video src="https://user-images.githubusercontent.com/25320503/149969691-dbf506a5-3d76-4949-b689-383e4dd61116.mp4" controls="controls" style="max-width: 730px;">
</video>

As you can see from above, the random particles in space start getting more and more concentrated as the robot moves and gets the bearing as an observation of the state at every step.

Here is another illustration of the same.

<video src="https://user-images.githubusercontent.com/25320503/149970194-5c5520c8-d743-4572-9e3c-eb12acb9474a.mp4" controls="controls" style="max-width: 730px;">
</video>




