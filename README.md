# Research Paper - The RAFT Consensus Algorithm 
## Summary
Raft is a consensus algorithm designed as an alternative to Paxos. It was meant to be more understandable than Paxos by means of separation of logic, but it is also formally proven safe and offers some additional features.Raft offers a generic way to distribute a state machine across a cluster of computing systems, ensuring that each node in the cluster agrees upon the same series of state transitions. It has a number of open-source reference implementations, with full-specification implementations in Go, C++, Java, and Scala. It is named after Reliable,Replicated,Redundant, And Fault-Tolerant.

# Team
* Sharwari Phadnis
* Janhavi DahiHande
* Pratik Bhandarkar (013735748)
* Kruti Thukral (012586041)
* Nishtha Aatrey (013006292)

# Contributions by Team Members
## Kruti Thukral
* Understood and researched on the various aspects of RAFT
* Worked on implementation of prototype using open soure python library 
* During the presentation, talked on performance and optimizations in RAFT
* During the presentation, gave a quick demo on a protoype using RAFT open source library
* Played an active role in the Q & A session during the presentation

## Pratik Bhandarkar
* Researched the "safety" part of RAFT i.e. how RAFT maintains the consistency while dealing with leader and/or follower/candidate failures
* During presentation talked about following safety aspects of RAFT:
  - Election restriction
  - Leader crashes
  - Candidate/follower crashes
  - Timing and availability requirements
* Actively participated in the Q & A session during the presentation

## Sharwari Phadnis
* Explored and researched the "Log Replication" aspect of RAFT in deep.
* Worked on testing and verifying the prototype implemented for RAFT.
* During the presentation, explained the Log Replication part of the RAFT that covered:
  - RAFT Log Mechanism
  - Replicated State Machines
* Played an active role in the Q & A session during the presentation

# How to run the prototype
## Dependencies:
* python3
* pysyncobj

Download pysyncobj using below
pip3 install pysyncobj

We are testing RAFT (Leader election and replication demo) using three servers running locally on various ports. We have a simple counter class which increments the counter by a specific value and it is seen to replicated on all servers. 
- During the run, one can see that the state is getting changed on all servers when the leader increments the count
- If one kills the server which happens to be the leader, there is a leader election which happens internally and another leader is elected which then continues incrementing the counter.

Our cluster has three servers running locally,which are expected to have the shared state . Execute below commands to test the prototype
Start server A running on port 4000 as below:
python3 Raft_Prototype.py 4000 3000 2000 

Start server B running on port 3000 as below:
python3 Raft_Prototype.py 3000 4000 2000

Start server C running on port 2000 as below:
python3 Raft_Prototype.py 2000 3000 4000

Now when you kill serverA , in the outout of other servers, you can see another server being elected as the leader
Thus in the above prototype, we saw a working example of log replication and leader election


