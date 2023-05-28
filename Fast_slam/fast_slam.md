
### Exercise: FastSLAM Implementation ###
***FastSLAM is a Rao-Blackwellized particle filter for simultaneous localization and
mapping. The pose of the robot in the environment is represented by a particle
filter. Furthermore, each particle carries a map of the environment, which it uses
for localization. In the case of landmark-based FastSLAM, the map is represented
by a Kalman Filter, estimating the mean position and covariance of landmarks.
Implement the landmark-based FastSLAM algorithm as presented in the lecture.
Assume known feature correspondences.***


(a) Complete the code blank in the sample motion model function by implementing the odometry motion model and sampling from it. The function updates
the poses of the particles based on the old poses, the odometry measurements
δrot1, δtrans and δrot2 and the motion noise. The motion noise parameters are:
[α1, α2, α3, α4] = [0.1, 0.1, 0.05, 0.05] (1)

(b) Complete the code blanks in the eval sensor model function. The function
implements the measurement update of the Rao-Blackwellized particle filter,
using range and bearing measurements. It takes the particles and landmark
observations and updates the map of each particle and calculates its weight
w. The noise of the sensor readings is given by a diagonal matrix
Qt =
1.0 0
0 0.1

(c) Complete the function resample particles by implementing stochastic universal sampling. The function takes as an input a set of particles which carry
their weights, and returns a sampled set of particles.
How does the resampling procedure differ from resampling in the standard
particle filter for localization (Exercise sheet 7)?
Some implementation tips:
• To read in the sensor and landmark data, we have used dictionaries. Dictionaries provide an easier way to access data structs based on single or multiple keys.
The functions read sensor data and read world data in the read data.py
file read in the data from the files and build a dictionary for each of them with
time stamps as the primary keys.
To access the sensor data from the sensor readings dictionary, you can use
sensor readings[timestamp,’sensor’][’id’]

sensor readings[timestamp,’sensor’][’range’]

sensor readings[timestamp,’sensor’][’bearing’]

and for odometry you can access the dictionary as

sensor readings[timestamp,’odometry’][’r1’]

sensor readings[timestamp,’odometry’][’t’]

sensor readings[timestamp,’odometry’][’r2’]
