### Exercise 1: Bayes Rule ###

Suppose you are a witness to a nighttime hit-and-run accident involving a taxi in
Athens. All taxi cars in Athens are blue or green. You swear under oath that
the taxi was blue. Extensive testing shows that, under the dim lighting conditions,
discrimination between blue and green is 75% reliable.
(a) Given your statement as a witness and given that 9 out of 10 Athenian taxis
are green, what is the probability of the taxi being blue?
(b) Is there a significant change if 7 out of 10 Athenian taxis are green?
(c) Suppose now that there is a second witness who swears that the taxi is green.
Unfortunately he is color blind, so he has only a 50% chance of being right.
How would this change the estimate from (b)?

### Exercise 2: Bayes Filter ###
A vacuum cleaning robot is equipped with a cleaning unit to clean the floor. Furthermore, the robot has a sensor to detect whether the floor is clean or dirty. Neither
the cleaning unit nor the sensor are perfect.
From previous experience you know that the robot succeeds in cleaning a dirty floor
with a probability of
p(xt+1 = clean | xt = dirty, ut+1 = vacuum-clean) = 0.7,
where xt+1 is the state of the floor after having vacuum-cleaned, ut+1 is the control
command, and xt
is the state of the floor before performing the action.
The probability that the sensor indicates that the floor is clean although it is dirty
is given by p(z = clean | x = dirty) = 0.3, and the probability that the sensor
correctly detects a clean floor is given by p(z = clean | x = clean) = 0.9.
Unfortunately, you have no knowledge about the current state of the floor. However,
after cleaning the floor the sensor of the robot indicates that the floor is clean.
1
(a) Compute the probability that the floor is still dirty after the robot has vacuumcleaned it. Use an appropriate prior distribution and justify your choice.
(b) Which prior gives you a lower bound for that probability?


