
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

- Review ADDM (Automatic diagnostic monitor) findings regularly and implement recommendations. ADDM is part of the AWR. AWR is the engine that gather stats and builds snapshots every 1hr of your system state and ADM takes that data and presents it to us.
- Monitor real-time session data 
- Respond to Oracle alerts

Reactive Tuning - fixing the issue as it comes 

- Run ADDM jobs manually
- Use ASH to resolve transient performance issues
- Use AWR Compare periods to resolve performance degradation over time

SQL Tuning 
- Locate high load sql statements and tune it.
- Optimise data access paths  - how oracle is executing and satisfying queries and improving the performance.

**AWR** (Automatic Workload Repository)

- The AWR system collects, processes and maintains oracle performance statistics.
- MMON(Manageability monitor process) & MMNL (Manage Ability Monitor Light process). Writes stats from the ASH buffer in the SGA. to disk and it writes to disk when the ASH buffer is full. 
- stores data in SYSAUX tablespace for both non-container databases and container databases.

DB time

What can slow down response time? Most common Database Performance problems 

- web browser used and how heavy it is
- WAN connection
- LAN issue
- Lack of adequate server hardware ex CPU,Memorry,Network,Storage
- Poorly configured initialisation parameters - OS level misconfiguration.
- Poor application coding
- Concurrency problems; locks and waits for buffer cache access


