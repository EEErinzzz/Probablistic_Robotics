### In the following you will implement a complete particle filter. 
(a) Complete the code blank in the sample motion model function by implementing the odometry motion model and sampling from it. The function samples new particle positions based
on the old positions, the odometry measurements δrot1, δtrans and δrot2 and the motion noise.
The motion noise parameters are:
[α1, α2, α3, α4] = [0.1, 0.1, 0.05, 0.05]
The function returns the new set of parameters, after the motion update.

(b) Complete the function eval sensor model. This function implements the measurement update step of a particle filter, using a range-only sensor. It takes as input landmarks positions
and landmark observations. It returns a list of weights for the particle set. See slide 15 of the
particle filter lecture for the definition of the weight w. Instead of computing a probability,
it is sufficient to compute the likelihood p(z|x, l). The standard deviation of the Gaussian
zero-mean measurement noise is σr = 0.2.

(c) Complete the function resample particles by implementing stochastic universal sampling.
The function takes as an input a set of particles and the corresponding weights, and returns
a sampled set of particles.
Some implementation tips:

• To read in the sensor and landmark data, we have used dictionaries. Dictionaries provide an easier way to access data structs based on single or multiple keys. The functions
read sensor data and read world data in the read data.py file read in the data from the
files and build a dictionary for each of them with time stamps as the primary keys.
To access the sensor data from the sensor readings dictionary, you can use

sensor readings[timestamp,’sensor’][’id’]

sensor readings[timestamp,’sensor’][’range’]

sensor readings[timestamp,’sensor’][’bearing’]

and for odometry you can access the dictionary as
sensor readings[timestamp,’odometry’][’r1’]

sensor readings[timestamp,’odometry’][’t’]

sensor readings[timestamp,’odometry’][’r2’]

To access the positions of the landmarks from landmarks dictionary , you can use
position x = landmarks[id][0]

position y = landmarks[id][1] 

