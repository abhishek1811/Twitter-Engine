# Twitter-Engine
Simulation of Twitter Engine (5 M users) with Actor Model (Scala) and Spray (REST API)

How to run the code
￼Normal
￼You need sbt and Java version 7 (not version 8) installed on the machine. Open two terminals, or run the server part of code on server machine and client part of code on client machines.
For Server machine, open the terminal, navigate to the server folder : cd //path
and then type the command
run sbt
Now you’ll enter the sbt console.

Server:
> compile
> run ScalingFactor Number_of_Client_Machines Time
For Client machine, open the terminal, navigate to the client folder :
cd //path
and then type the command
run sbt
Now you’ll enter the sbt console.
Client:
> compile
￼
> run IP_address ScalingFactor Event/Regular
* We are reading the tweets from a file, so we need to change the exact path location of where the file is present. So while before running the code on client machine, just change the path of text file (located in the main folder).
Change file path in client code. (Line Number 139)
REST API
The requirements are similar, you need to open up three terminals and cd into 3 folders, namely: Server, RestServer and Client. After that you need to run sbt and compile.
Following this, the commands are written below with an example: Server:
> compile
> run ScalingFactor Number_of_Client_Machines Time
Rest Server:
> compile
> run IPServer IPSelf
Client:
> compile
> run IPServer ScalingFactor Event/Regular IPRestServer
￼￼￼￼￼
Twitter Architecture
The architecture that we’ve implemented is shown below:
￼￼
Number of people followed (Following)
Twitter Stats
￼The stats we have implemented are:
￼￼￼
Followers
￼￼￼
Tweeting stats
We implemented two types of tweeting stats namely Regular and Event.
Regular
￼￼￼￼
Event
In this stats, we bombard tweets every second.
Functionalities Implemented
We’ve implemented six functionalities, namely :
￼￼• Return Followers
• Return Tweets
• Return Mentions
• Re-tweet
• Post Mention
• Post Tweet

Event Normal
Observations and Graphs
￼￼￼￼Scaling Factor : 1 , Number of Client Machines: 1 , Time: 60 seconds , Event
20000
15000
10000 ￼ ￼ ￼ Messages Processed Per
￼￼￼￼￼5000
0
1 4 7 1013161922252831343740434649525558
Sec
￼￼￼
￼￼40000
35000
30000
25000
Scaling Factor : 2 , Number of Client Machines: 1 , Time: 60 seconds , Event
￼￼￼￼￼￼￼￼￼20000 ￼ ￼ ￼ Messages Processed Per
15000
10000
 5000
    0
Sec
￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼￼45000
40000
35000
30000
25000
20000
15000
10000
5000 0
Messages Processed Per Sec
Scaling Factor : 3 , Number of Client Machines: 1 , Time: 60 seconds , Event
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼0 10 20 30 40 50 60 70
￼￼40000
35000
30000
25000
20000
15000
10000
5000 0
Messages Processed Per Sec
Scaling Factor : 4, Number of Client Machines: 1 , Time: 60 seconds , Event
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼￼Scaling Factor : 5 , Number of Client Machines: 1 , Time: 60 seconds , Event
35000
30000
25000
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
Messages processed per sec:
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Regular Normal
Scaling Factor : 3 , Number of Machines: 1 , Time: 60 seconds , Regular
￼￼￼Scaling Factor : 1 , Number of Machines: 1 , Time: 60 seconds , Regular
Messages processed per sec:
25000
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Scaling Factor : 2 , Number of Machines: 1 , Time: 60 seconds , Regular
Messages processed per sec:
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼25000
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
Messages processed per sec:
￼￼Scaling Factor : 4 , Number of Machines: 1 , Time: 60 seconds , Regular
Messages processed per sec:
35000
30000
25000
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Scaling Factor : 5 , Number of Machines: 1 , Time: 60 seconds , Regular
Messages processed per sec:
40000
35000
30000
25000
20000
15000
10000
5000
0
1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼The Regular tweeting graph is shown below:
Number of users: 40,000 Number of seconds : 60
￼The Event tweeting graph is shown below:
Number of users: 40,000 Number of seconds: 120
￼
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼EVENT Rest API
￼￼￼Scaling Factor : 1 , Number of Client Machines: 1 , Time: 60 seconds , Event
2500
2000
1500
1000
500
0
1 4 7 1013161922252831343740434649525558
Messages processed per sec:
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼12000
10000
 8000
 6000
 4000
 2000
    0
Messages processed per sec:
Scaling Factor : 2 , Number of Client Machines: 1 , Time: 60 seconds , Event
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Scaling Factor : 3, Number of Client Machines: 1 , Time: 60 seconds , Event
700
600
500
400
300
200
100
0
1 4 7 1013161922252831343740434649525558
Messages processed per sec:
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Scaling Factor : 4 , Number of Client Machines: 1 , Time: 60 seconds , Event
Messages processed per sec:
10000
 8000
 6000
 4000
 2000
0
1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼Regular Rest API
￼￼￼12000
10000
 8000
 6000
 4000
 2000
    0
Messages processed per sec:
Scaling Factor : 1, Number of Client Machines: 1 , Time: 60 seconds , Regular
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼12000
10000
 8000
 6000
 4000
 2000
    0
Messages processed per sec:
Scaling Factor : 2, Number of Client Machines: 1 , Time: 60 seconds , Regular
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼12000
10000
 8000
 6000
 4000
 2000
    0
Messages processed per sec:
Scaling Factor : 3, Number of Client Machines: 1 , Time: 60 seconds , Regular
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
￼12000
10000
 8000
 6000
 4000
 2000
    0
Messages processed per sec:
Scaling Factor : 4, Number of Client Machines: 1 , Time: 60 seconds , Regular
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼1 4 7 1013161922252831343740434649525558
Output
The output screen of running REST API is shown below:
￼
￼Some Cool Stuff
● Implemented exact twitter statistics.
● The average number of tweets per second is greater than 30,000.
● The max number of tweets per second that we recorded were 53,000 tweets
for 1,50,000 users.
● The people who have more followers tweet more, which is true in the real
scenario as well.
￼
References
www.sysomos.com - For Tweeter Stats
￼￼
