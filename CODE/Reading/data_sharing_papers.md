# Information Sharing for Distributed Intrusion Detection System
### Challenges want to address:
1. What information to share
2. How to share information
### Contribution:
1. Propose a simple yet robust scheme to monitor changes in the local statistics
2. Present a learning algorithm to decide to decide when to share information so that both the communication overhead and the detection delay are minimized
### Problems:
1. centralized detection approach suffers from scalability problems due to central bottleneck
### Methods:
1. detecting shifts in the mean level of a set of traffic measurements
2. The measurements are analyzed by a detection system, which reports any abrupt change in the mean level of the set of measurements.
3. A more practical approach is to place multiple intrusion detection systems at different locations in the network and let these systems share summary statistics of their observed statistics. These distributed detection systems then cooperate to detect any change in the traffic. The advantage of this distributed system is that it is scalable, decentralized and does not have a single point of failure. However, there are 2 inherent challenges for this approach, i.e te detection algorithm for each distributed intrusion detection system and how the information is shared among the distributed intrusion detection systeems.
4. In order to reduce the overhead for online impelementation,we use the recursive version of non-parametric CUSUM algorithm which is defined as follows:
#### A.  Cumulative Sym (CUSUM) Change Detection
2 types. 
1. one is fixed-size batch detection, which tests for the change of mean value every time a fixed window of new sample points have been collected.
2. another is sequential change-point detection, which tests for the change every time a new measurement arrives
3. We require an algorithm to detect changes of at least size h and estimare the change point m in a sequential manner
4. Measure the performance of the detection scheme in terms of 1. the detection delay and false positive rate

#### B. Distributed Detection Using CUSUM
1. When a detection system observes any suspicious activities, it informs its y valye to other detection system. After receiving the broadcase, the other detection system can directly add the recieved y_n to calculate a new y_n value. However, in some network applications, we may assign a weight to the broadcast first, then add the weighted y to calculate the new y value. 
### C. Sharing Distributed Evidence
1. The most challenging part for detecting attacks at thre reflector is that the reply traffic from the victim to the reflector may be widely distributed
2. We can take 2 steps to tackle this problem. First, we divide the network into serveral subnetworks according to the network topology. Each detection system is implemented to monitor a single subnetwork's traffic.



### Additional infor
1. The reflector attack contains 3 stages
2. turing the computer into a "zombie"
3. "zombies" are ordered to send the spoofed traffic wiith the victim's IP address as the source IP address to the third parties
4. In the third stage, the third parties will then send the reply traffic to the victim, which constitute a DDoS attack
5. The reflector attack traffic is further diluted by the third parties, which makes the attack traffic even more distributed
6. The reflector attack has the ability to amplify the attackk traffic, which makes the attack even more potent
7. Motivation for the distributed Detection is that, if we implement the detection system in the reflectors, we can detect the attack traffic and filter it before it arrives at the victim. Furthermore, once the reflector can detect the onset of the attack, in principle we can trace the zombies that are the source of the attack

8.There are 2 detection opportunities for the reflector. The first is to monitor the spoofed traffic from the "zoombies"
9. The second is to monitor the reply traffic from the victim
10. 


### My concerns: 
1. They choose the statistics they are interested in. But what if we cannot find a single statistics that can detect the intrusion detection, what if the detection is only detected when we use many features?
2. How to choose which thresholds to detect the anomalies, what if the data from each measurements points are ver diverse? How do they come up with the mechanism to combine the data from various points?
3. How to detect the changes due to the natural variations of the network versus the one caused by intrusion?







