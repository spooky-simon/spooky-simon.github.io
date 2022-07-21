---
title: Fiero Suspension
layout: page
---

# Fiero Suspension

## Stock Points

As stated 100 other times on this site, we have to figure out what we're working with before we start to make changes.

<figure>
  <img src="{{site.url}}/docs/assets/seinfeld.jpg" alt="image of jerry seinfeld saying whats the deal"/>
  <figcaption><em>What's the deal with this suspension?</em></figcaption>
</figure> 

### The Plan

We have to ensure the wheels are level, my driveway is certainly not. I will shim the wheel with bits of ply and check with a laser level. After making sure we're on level ground (so to speak), I'll paintakingly measure the x,y,z positions of every pickup point on the car. Not looking forward to the process, but looking forward to the results.

The front suspension is a SLA double wishbone. The rear is a MacpPherson strut. I'll need to either find or painstakingly measure the 3D location for each suspension point.


### Suspension Kinematics

A lot of work has been done on Fieros to simulate the kinematics of the 1988 redone suspension. Little has been done on the 1984-87 setup. Yarmouth [sic] did a relatively in depth analysis of a 1987 Fiero but did not include the raw data to verify or use. I was unable to get in contact with him to obtain them.

In order to check my work against his, I would have to do my own suspension analysis. Unfortunately, there are limited third party suspension kinematic solvers and I couldn't find a complete 3D solver available for free from a reputable source. I will have to make my own.

The first (and basically only) result is a youtube video from Spinning Thumbs on coding his own <a href="https://www.youtube.com/watch?v=lD2DKIhrkxs">kinematic solver</a>. For whatever reason, he was unable to finish his project and did not upload a part 2, or the finished code. However, I liked his iterative approach to solving it since a quick google into the inverse kinematics of a parallel non-planar linkage system proved daunting.

I'm not sure if Spinning Thumbs was aware, but he was running a stochastic gradient descent algorithm to solve the system. After a week, I was able to put his approach into practice and in a second iteration of the code, I built a more traditional gradient descent algorithm since the derivatives, gradients, and jacobians were relatively simple to calculate and it ended up cutting the solve time of the system ten-fold.

Gradient descent is used to solve a number of equations at the same time. The equations we were using was moving the wheel and then measuring the lengths of the suspension links against what they were supposed to be. If they were too long, the suspension point was moved closer to the points it was linked to, and if it was too close, it was moved out. The corner of the Fiero has 4 points that can move in ways that can be hard to predict analytically. the tie rod point on the knuckle, the wheel center, and the upper and lower knuckle pickup points. Each of these points is linked to other points by a piece of metal and the distance between them cannot change. For example: The upper pickup point on the knuckle is connected to the two upper wishbone pickup points, the wheel center, the lower knuckle pickup point, and the tie rod outer point. This is 5 links whose length we have to maintain as we move the wheel in space. In total, there are 17 link length calculations we have to perform, some are duplicates of eachother. In a twist of fate, removing the duplicate calculations makes the gradient descent slower because you are ignoring parts of the system and therefore not descending at the steepest gradient. Because there are only 17 equations and each equation only has the x, y, and z variable of a suspension point, there are only 51 variables to dither on each iteration, hence traditional gradient descent being faster then the previous stochastic approach.

I used the wikipedia recommended cost function (objective function) and ran an invariate learning rate (for ease of coding). While not instantaneous, my code is able to calculate 1000 different suspension positions in about 0.5 sec. A better coder could likely optimize further, but this suffices for the speed and acurracy that I am looking for.

See the code here: https://github.com/spooky-simon/Kinematic-Solver