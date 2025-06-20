
DBA Basics

**Introduction to DBA**

Relational database
- Data is stored in tables within relational database and the only way to talk to relational databases is through SQL commands
- Application talks to the database through the network to access the data.
- DBA is responsible for looking after the health of the database.
- DBA have different responsibility; recoverability incase your database crashes, availability, integrity, performance, security (only privileges people can access the data) and assist programmers. 

**DB performance tuning** 

**Terms**

Bottleneck; Area of a system where resource contention is highest. Produces a slowness so you have to find these bottlenecks.
Throughput: work per unit time
Response time: Time to complete a given workload
Baseline: A representation of system performance and the performance tuning relies on baseline. Should capture usage highs and lows and gives a picture of a normal running system. 
Snapshot: Can be overlaid to compare against baselines 

**Approaches to Performance Tuning** 

Proactive tuning - solving problems before they occur

- Review ADDM (Automatic diagnostic monitor) findings regularly and implement recommendations. ADDM is part of the AWR. AWR is the engine that gather stats and builds snapshots every 1hr of your system 
- Monitor real-time session data 
- Respond to Oracle alerts

Reactive Tuning

- Run ADDM jobs manually
- Use ASH to resolve transient performance issues
- Use AWR Compare periods to resolve performance degradation over time

SQL Tuning 
- Locate high load sql statements and tune the heck out of em
- Optimize data access paths 
