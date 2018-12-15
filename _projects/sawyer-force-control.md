---
layout: project
title: Final Project - Sawyer Force Control
date: December 15, 2018
image: http://unsplash.it/400?random
permalink: "sawyer-force-control.html"
---

# Sawyer Force Control

## Project Goal

The goal of the final project in my Master's in Robotics at Northwestern was to
implement a force controller on Rethink Robotic's Sawyer robot. This was to be
accomplished using an ATI Axia 80 Force/Torque (F/T) sensor attached to Sawyer's
end effector, in place of its normally attached grippers.

In a very general sense, this project was approached in four steps:
1. Design and machine adapter plates to rigidly attach the F/T sensor to Sawyer's wrist

2. Simulate a motion controller that will be used to drive Sawyer

3. Adapt the simulated control for use with the real world Sawyer

4. Use the F/T sensor to control the force applied by Sawyer at the end effector
while also controlling Sawyer's motion

Force control, or being able to control how a wrench is applied at a robots end
effector, has many important and impressive uses in industry and research today.
For instance, force control can be used to accurately a screw in a threaded
hole, or carefully apply a force to a textured surface. In industry, for example,
force control can be used to have a robotic arm deburr an arbitrary curved edge.
Force control is also used to enhance human-robot interaction by giving the robot
the ability to 'feel' a human touch and respond in ways that are perceived as natural.

If you are interested in learning more about the ROS package I made for this project,
including how to use the package yourself, please see the extremely detailed README on
[the packages GitHub repository](https://github.com/michaeltobia/sawyer_velctrlsim)

## Results

#### 1. Adapter Plates
The adapter plates used in this project were designed in OnShape. The design
makes use of threaded aluminum spacers to allow access to the screws that
attach the plates to Sawyer and the F/T sensor. A plastic spherical knob was
threaded on to an M10 threaded rod attached to the bottom adapter plate on the
F/T sensor. This allows for smooth contact of surfaces with minimal friction and
clean force readings, since the applied force is always perpendicular to the sphere.
The full adapter plate and F/T sensor assembly can be seen below.

<!-- FORCE SENSOR AND ADAPTER PLATE IMAGE -->

#### 2. Control Simulator
Running `sim_vel_ctrl.launch` opens the simulator portion of this package. In
this launch file, a trajectory generating node publishes `TransformStamped`
messages representing the desired trajectory along the `/desired_trajectory`
topic. A velocity controller calculates velocity commands to drive the simulated
Sawyer's end effector to this desired transform. These joint positions are
then interpolated from these commands and published to be visualized in RViz.
The result is a simulated Sawyer following an end effector trajectory described
in `traj_gen.py`, as seen below.

![testgif](https://www.doggifpage.com/gifs/155.gif)

<!-- SIMULATOR GIF -->
 
#### 3. Sawyer Velocity Control
After connecting to Sawyer, running `sawyer_vel_ctrl.launch` begins a velocity
control loop that drives Sawyer's end effector to the trajectory defined in
`traj_gen.py`. Running Sawyer in velocity control mode means its joints can be
ran as fast as the joint velocity limits will allow. **This is very fast.** If
given a quick trajectory in `traj_gen.py` Sawyer would happily track this position
fast enough to damage something or injure something in the way. Joint velocity
commands are limited in `sawyer_vel_ctrl.py` to 0.6 rad/sec maximum because of this,
to prevent accidents. The following gif is a short example of this velocity control
running.

<!-- Velocity control gif -->

#### 4. Sawyer Force Control
After connecting to both Sawyer and


\begin{equation}
\int \frac{1}{2} l(x,u) dx = 0
\end{equation}

\begin{equation}
\ V_{b}( t) =[ Ad_{X^{-1} X_{d}}] V_{d}( t) +K_{p} X_{e}( t) +K_{i} \int X_{e}( t) dt
\end{equation}

\begin{equation}
where...\ [ X_{e}] =\log\left( X^{-1} X_{d}\right) ;[ X_{e}] \in se( 3)
\end{equation}
