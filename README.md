# Simulating_COVID-19_SIR-Model
An epidemic like COVID-19 is an SIR epidemic. An individual is initially Susceptible (S). Then s/he might get Infected (I) and finally Recover (R). However, as one can expect, each transition is probabilistic.

An event like Susceptible or Infected or Recovered is pushed into the proirity queue and each event in priority queue necessarily has the structure a) the time when the event occurs, b) the type of event (transmit or recover) and c) which node it concerns.
If the event is a transmit event and the corresponding node v is susceptible, v is deleted from the S list and add it is added to the I list. The events corresponding to the node v transmitting the infection to its neighbors, along with the time at which this happens is pushed into the priority queue.
For each neighbor, a coin is tossed with probability τ for each day until we get a heads. For the day we get a heads, a transmit event is added for that neighbor.
For v’s recovery we toss a biased coin with γ probability of it showing heads. We keep tossing until we get a heads. If we get a heads on the ith trial, v will recover after i days.
If the event is a recover event, then the node is removed from the I list and it is added into the R list.

This simulation is performed for a maximum of 300 days, using τ(transmission probability) as 0.5 and γ (recovery probability) as 0.2 with a a graph of 10000 nodes and maxium of 3000 edges from each node.
