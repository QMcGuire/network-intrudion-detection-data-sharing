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
4. What to do in the presence of no groundtruth? 



### What I like
1. The way they construct is flexible trade off betwen the delay time and the overhead. 

### My take away:
1. Cumulative might be a good way to aggregate anomalous data because it smooth out any temporal variations and aggregate the detection of various systems, especially if attacks is at the same time
2. Can divide the subnetwork to detect monitor sudden changes early and effectively
3. 






# Automatic Relational Data Augmentation for ML
### What it is
1. An end-to-end system that takes as input a datset and a data repository, and outputs an augmented dataset such that training a predictive model oon this augmented sataset results in improved performance.
2. OUr system has 2 distinct components: a framework to search and join data with the input data, based on various attributes of the i nput and an efficient feature selection algorithm that prunes out noisy or irrelevant features from the resulting join
3. We explore how we can extend existing automatic machine learning tools to also perform automatic data augmentation byy joining related tables
### Challenges:
1. integrating related datasets requires finding the right join key between different datasets
2. There might be hundreds of related tables
### Big idea:
1. Works by first constructing a coreset, a representative but small set of rows from the original sample table. This coreset is strategically joined with candidate tables and features are evaluated using a novel technique called Random Injection Feature Selection (RIFS).
2. At a high level, RIFS helps determine if the results of a join are helpful for a predictive model by comparing candidate features against noise: if a candidate feature performs no better than a feature consisting of random noise, that feature is unlikely to be useful.
3. ARDA handles joins between mismatched keys that may not perfectly align using several interpolation strategies. 
4. The final output of ARDA is an augmented dataset, containing all of the user's original dataset as well as additional features that increase the performance of a predictive model.

### Contribution
1. We introduce ARDA, a system for automatic relational data augmentation which can discover joins that improve the performance of predictive models
2. Propose simple methods for performing one to many and soft key joins useful for ML models
3. Introduce RIFS, a specific feature selection technique custom-tailored to relational data augmentation
### Augmentatin workflow
#### coreset construction:
1. 2 main techniques, sampling and sketching
2. sampling: selects a subsets of the rows and re-weights them to obtain a coreset
3. sketching relies on taking sparse linear combination of rows which inherently results in modified row values
#### Join plan
1. supports single key join, multiple key join, mixed key join and multiple option key join
2. hard join where the value is exact match
3. soft key, do not require an exact match but the closest value
#### Join execution
#### Feature selection
1. Feature selection can be broadly categorized into filter models, wrapper models and embedded models
2. Filter model separates feature selection from classifier learning so that the bias of a learning algorithm does not interact with the bias of a feature selection algorithm. These algorithms rely on general characteristics of the training data such as distance, consistency, dependency, information and correlation
3. The wrapper model uses the predictive accuracy of the learning algorithm to determine the quality of selected features. Wrapper-type feature selection methods are tightly coupled with a specific classifier. Such methods are likely to get stuck in local minimax
4. Embedded model which includes information about labels and incorporates the performance of the model on the holdout data. Typically, the first step is to obtain a ranking of the features by optimizing a convex loss function

### Contribution
#### Random Injection Based Feature Selection
1. Design a comparison-based feature selection algorithm that circumvents the requirement of testing each subset of features.
2. Do this by injecting carefully constructed random features into our dataset. Use the random feaatures as a baseline to compare the input features with.
3. 

### My question
is it model dependent



