# Assignment7
## INTRODUCTION
In this assignment we will try to use the transfer functions which are in frequency domain to find out the time responses of various oscillatory systems and plot them.
We will import scipy.special to use functions such as lti, impulse, bode, lsim etc. This will help us convert from frequency to time domain and analyse them. These functions from the scipy module make our work a lot easier.
### Forced Harmonic Oscillator

Behaviour while varying damping coefficients:

The frequency or laplace domain transform of f(t) = cos(1.5t)exp(-0.5t)u(t)
is given by :

F(s) =(s + 0:5)/((s + 0:5)2 + 2:25)

The system is defined by the following differential equation :

(d2x/dt2) + 2:25x = f(t)
Now we will use the functions appropriately to find out the time response of the system

![Figure_7 1](https://user-images.githubusercontent.com/81006760/115753046-5a58a180-a3b8-11eb-8a79-4d5eb1deb0bf.png)

x(t) vs t for 0.5 and 0.05 damping factor

Behaviour while varying frequiencies

In the above problem we varied the damping coeffecients, now we will observe the system's behaviour while varying frequency from 1.4 to 1.6, while keeping the damping coefficients constant at 0.05.
We then plot the time response for varying frequencies in the same plot.
We observe that at frequency = 1.5 it peaks, because w = 1.5 is the resonant frequency of the system

![Figure_7 2](https://user-images.githubusercontent.com/81006760/115750038-5d05c780-a3b5-11eb-97e8-649293823309.png)

x(t) vs t for varying frequencies

#### Coupled Spring System
We are given the simultaneous equations of a coupled spring system as follows :

d2x/dt2 + (x-y) = 0 d2y/dt2 + 2(y-x) = 0

We use these initial conditions : x(0) = 1 ,x'(0) = y'(0) = y(0) = 0

We then solve for x by substituting y in the 1st eq and then we resubstitute x for getting y. After this we find out the time responses of x,y and plot them. The plots are given below.

![Figure_7 3](https://user-images.githubusercontent.com/81006760/115750731-1d8bab00-a3b6-11eb-9a65-4080c33f8e09.png)

Coupled spring system

##### Two Port LCR system
Madnitude and Phase plots

The given two port LCR network has the values : R = 100 ohm , L = 1uH , C = 1uF. We use the bode function to plot the magnitude and phase plots of the transfer function.

The transfer function is : H(s) =1/s2LC + sRC + 1

The initial conditions are zero, the bode plots are as follows and they are plotted using the following piece of code

![Figure_7 4](https://user-images.githubusercontent.com/81006760/115751571-ee296e00-a3b6-11eb-982a-2d29610eb5fd.png)

Magnitude and Phase plots

Output of the given LCR system for a given input

When an input V(t) = cos(1000t)u(t) - cos(1000000)u(t) is given to the system, we try to find the output. After solving for the output, we get the following plots.

![Figure_7 5](https://user-images.githubusercontent.com/81006760/115752018-55dfb900-a3b7-11eb-8b79-214170ad7eb1.png)

Transient Response

![Figure_7 6](https://user-images.githubusercontent.com/81006760/115752183-7b6cc280-a3b7-11eb-8b46-5aaa11fa0d16.png)

Output of RLC

###### Conclusion

For t less than 30us:

cos(1000t) is close to one as 1000t is almost zero increasing at a slow pace.So, due to the dominant nature of cos(1000000t), the output has cosine nature.

As t increases cos(1000t) dominates cos(1000000t) , therefore the output oscillates with dominant frequency of 1000Hz with small oscillations of frequency 1MHz.

