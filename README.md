WEB SERVER PERFORMANCE ISSUE POSTMORTEM


Issue Summary
The issue occurred around 5pm-7pm it took 2 hours to find and rectify the problem, the issue occurred due to an overload of requests to the server.

Duration
The issue occurred around 5pm-7pm EAT.

Impact
Our server became very slow in serving requests to our customers causing errors and long wait times for the page to become responsive. This affected 85% of our customers.

Timeline
The issue was detected at 5pm through a datadog monitoring alert triggered by high right and read requests.
The team started investigating to pinpoint the root of the problem. Initial thoughts of the team was slow internet connection.

Misleading Paths
The initial focus was on querying internet quality and speed which turned out to be okey.

Escalation
The problem was escalated to a senior software engineer who has extensive experience at 5:30pm.
Resolution
Around 6:40pm the problem was identified successfully which turned out to be the settings of the load balancer, our load balancer was not distributing requests to our servers evenly. The loadbalancer was reconfigured and the distribution of requests set up to be even.
Root Cause and Resolution

Root Cause
The root cause of the problem was in the configuration of the load balancer which did not evenly distribute requests slowing down our system. 

Resolution
The configuration was redone on our load balancer and tested to ensure that distribution of requests was now even to restore normalcy in our system and ensure proper system performance.



Corrective and preventative measures

Improvements and fixes
Audit load balancer settings regularly to avert configuration issues.
Implement a monitor alert for load balancer request distribution and its overall performance.

Tasks to address the issue
Set up monitoring for the load balancer.
Conduct load balancer configuration reviews fortnightly.
Develop a load testing plan to simulate traffic spikes and optimize system performance.

These measures will prevent similar incidents in the future and improve system reliability and overall performance.
0x00. Shell, basics
