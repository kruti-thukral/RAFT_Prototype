download pysyncobj using below
pip3 install pysyncobj

we are testing this using three servers running locally on various ports. We have a sample counter class which increments the counter by some value and it should be replicated on all servers. 
-During the run you can see that the state is getting changes on all servers when one the leader increments the count
-If you kill one server, there is a leader election which happens internally and other leader is elected which then continues incrementing the counter

Our cluster has three servers running locally and which are expected to have the shared state
Start server A running on port 4000 as below:
python3 Raft_Prototype.py 4000 3000 2000 

Start server B running on port 3000 as below:
python3 Raft_Prototype.py 3000 4000 2000

Start server C running on port 2000 as below:
python3 Raft_Prototype.py 2000 3000 4000

Now when you kill serverA , in the logs of other servers, you can see other server elected as the leader
So Above is an example of log replication and leader election


