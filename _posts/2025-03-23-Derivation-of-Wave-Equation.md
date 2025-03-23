---
tags: Seismic-Hazard
---
Waves are one of the physical phenomena which travel through a medium or vacuum. They are divided into two categories, mechanical waves and electromagnetic waves. Mechanical waves, such as seismic waves, water waves, and sound waves are examples of waves which travel through a medium which are an earth structure and air respectively. Electromagnetic waves, such as light, microwave, radio, and infrared are examples of waves which travel through vacuum, they do not need a medium. The physical phenomena of waves that we observe in our daily activity, can be explained mathematically. The waves travel as a function of position and time. What mathematical equation describes the behaviour of waves?

As I mentioned above, the waves are a function of position ($$x$$) and time ($$t$$) or mathematically is $$u(x,t)$$. We also can define the another two directions, $$y$$ and $$z$$ directions in terms of 3-dimension, where the $$x$$ and $$y$$ are horizontal direction also $$z$$ is vertical direction. For simplicity, this article will explain only in a 1-dimension of position perspective through the simple illustration of string.

Since the waves are moving from point to another point during a range of time, we can use the second Newton’s Law, where a particle of a wave as a mass ($$m$$) of the object moves by a certain acceleration ($$a$$) which is caused by external force ($$F$$). The Newton’s Second Law can be written as

$$F = m a$$

In the example of string, the external forces are represented as tensions $$T$$. There are two tensions work in this process, $$T_1$$ is the initial tension at position $$x$$ and $$T_2$$ is the tension that has changed the position as long as $$x$$, and it turns the final position at $$x + \Delta x$$. There is an angle $$\theta$$ formed which is relative to tension direction and horizontal direction, we see this as a cartesian direction. So, the tensions are observed into two components, $$x$$ and $$y$$. We first must extract the tensions which work for each direction.

## Tension in x-component

We extract the tension in $x$ direction of cartesian direction as follow

$$T_x = T_2 cos \theta - T_1 cos \theta$$

When the $$\theta$$ is very small (close to 0), then the $$cos \theta \approx 1$$, then

$$T_x = T_2 - T_1$$

Assuming all the tensions are the same, $$T_2 = T_1$$, then the tension in the $$x$$ component is none or equal to zero.

## Tension in y-component

By using the same way, we extract the tension in the $$y$$ component as follow

$$T_y = T_2 sin \theta - T_1 sin \theta$$

When the $$\theta$$ is very small (close to 0), then the $$sin \theta \approx tan \theta$$, where 

$$tan \theta = \frac {\Delta u} {\Delta x}$$

for the $$\Delta u$$ is the step change in the $$y$$ component and the $$\Delta x$$ is the step change in the $$x$$ component. Then, the equation of $$T_y$$ become

$$T_y = T_2 tan \theta - T_1 tan \theta$$

$$T_y = T_2 \frac {\Delta u} {\Delta x} - T_1 \frac {\Delta u} {\Delta x}$$

Since the $$T_2$$ has change at $$x + \Delta x$$  during time $$t$$ in the $$x$$ direction and $$T_1$$ is at $$x$$ as initial position during time $$t$$, then the all tensions are the same ($$T_2 = T_1 = T$$), we can write

$$T_y = T (\frac {\Delta u (x + \Delta x, t)} {\Delta x} - \frac {\Delta u (x, t)} {\Delta x})$$

By this equation, there is tension in he $$y$$ component of the string. We can put into the Newton's Second Law equation

## Combine
Since the tension in the spring only work at the $$y$$ component, we can write the equation into the Newton's Second Law as follow

$$F = m a$$ where $$F = T_y$$

$$T (\frac {\Delta u (x + \Delta x,t)} {\Delta x} - \frac {\Delta u (x,t)} {\Delta x}) = m a$$

The mass of string's element $$m$$ can be approximated by using linear mass density, which describes the total amount of mass along element of string's length ($$\Delta x$$), where $$m = \rho \Delta x$$. Then, the acceleration can be described as the change of position twice relative to time or it can be mentioned as the second derivative of position relative to time, $$a = \frac {\delta^2 u(x,t)} {\delta t^2}$$. We can put these terms into the previous equation

$$T (\frac {\Delta u (x + \Delta x,t)} {\Delta x} - \frac {\Delta u (x,t)} {\Delta x}) = \rho \Delta x \frac {\delta^2 u(x,t)} {\delta t^2}$$

Divided by $$\rho \Delta x$$

$$\frac {T} {\rho}  \frac {1} {\Delta x} (\frac {\Delta u (x + \Delta x,t)} {\Delta x} - \frac {\Delta u (x,t)} {\Delta x}) = \frac {\delta^2 u(x,t)} {\delta t^2}$$

$$\frac {T} {\rho}  \frac {1} {\Delta x} (\frac {\Delta u (x + \Delta x,t) - \Delta u (x,t)} {\Delta x}) = \frac {\delta^2 u(x,t)} {\delta t^2}$$

The $$\frac {\Delta u (x + \Delta x,t) - \Delta u (x,t)} {\Delta x}$$ is the first derivative relative to the position $$\Delta x$$ and can be applied limit for $$\Delta x \rightarrow0$$, then

$$\lim_{\Delta x \to 0} \frac {\Delta u (x + \Delta x,t) - \Delta u (x,t)} {\Delta x} = \frac {du(x,t)} {dx}$$

Since we have $$\frac {1} {\Delta x}$$, it make second derivative of the position, then 

$$\lim_{\Delta x \to 0} \frac {1} {\Delta x} \lim_{\Delta x \to 0} (\frac {\Delta u (x + \Delta x,t) - \Delta u (x,t)} {\Delta x}) = \frac {d} {dx} (\frac {du(x,t)} {dx}) = \frac {d^2u(x,t)} {dx^2}$$

Because the left hand side only change in the $$x$$, then we can write it as partial derivative, then

$$\frac {T} {\rho} \frac {\delta^2u(x,t)} {\delta x^2} = \frac {\delta^2 u(x,t)} {\delta t^2}$$

This is the wave equation in 1-Demenison.
