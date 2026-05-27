Scenario								|Single-AZ | Multi-AZ standby | Multi-AZ cluster (1 writer + 2 readers)|Aurora Serverless
Personal blog, 200 visits/day				                   X
Hospital OT scheduling app, low traffic but zero downtime tolerated	               X			
E-commerce site, read-heavy, traffic spikes on Fridays				                                    X
Internal report tool, used 30 min/day, idle the rest				                                                                     X
Discord-like product needing millions of small DBs				                                                                     X



Q>Look at the storage type options (gp2, gp3, io1, io2, magnetic). Explain in your own words: for a 100 GB database getting hammered with writes, why does the disk matter more than CPU/RAM? What does IOPS mean and why does it scale with disk size?

Ans: The disk which has a higher iops can reduce the CPU and RAM usage becuase writes to disk will be faster.RAM does not has to hold the memory for a long time till it is flushed in disk


Q> What is connection pooling? If your app makes 1,000 concurrent DB connections at ~10 MB each, what's the rough memory cost on the DB server? How does a 50-connection pool change that math?
Ans: 1GB memory is being used is creating DB connections.If connection pool is used then it reduces to 500MB

Q> Simple, Weighted, Latency, Failover, Geolocation, Geoproximity, Multivalue, IP-based. For each, give a one-sentence real use case. 
Simple: Simple Web site
Weighted: Certain percentage of users go to one endpoint
Failover: DR site when primary setup fails the failover trggers

Q>What is a scheduled scaling policy and when does it beat dynamic scaling?
When we estimate a big traffic during some time we can use scheduled scaling policy.It can ensure ec2 instances are made before hand so that no traffic could be missed during strong uptime.

Q> Explain the cooldown period and why a 100-second warmup matters
Ans: When a scaling decision is made by scaling group , the cooldown period is wait time till the next scaling decision is made
100-second warmup matters before instance startup becuase the instance has to download python dependcies , and start gunicorn server.




