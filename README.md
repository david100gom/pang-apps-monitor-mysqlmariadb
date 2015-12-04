# prever-apps-monitor-mysqlmariadb
Mysql and Mariadb monitoring application for Traffic, Queries per second, Reads/Writes per second and more.
You can monitor and access your database using prever.io cloud web service on mobile, tablet and Laptop anywhere.

## Screen shot
###### Realtime monitoring ######
![Realtime monitoring](https://github.com/prever-apps/prever-apps-monitor-mysqlmariadb/blob/master/screen-shot.png "Realtime monitoring")

###### Realtime monitoring on Mobile ######
![Mobile](https://github.com/prever-apps/prever-apps-monitor-mysqlmariadb/blob/master/screen-shot-2.png "Realtime monitoring")

## Getting Started
#### Sign up for Prever.io ####
Before you begin, you need an Prever.io account. 
Please visit <a href="http://prever.io" target="_blank">http://prever.io</a> and create an account and retrieve your user key in user profile.

#### Minimum requirements ####
To run the application you will need **Java 1.5+**.

#### Installation ####
Very easy to install ^^.

##### Step 1 #####

###### Windows ######
Download a <a href="https://github.com/prever-apps/prever-apps-monitor-web/releases/download/1.0/prever-apps-monitor-mysqlmariadb.zip">Prever mysql/mariadb monitoring application</a> file and unzip it.

###### Linux ######
``` 
wget https://github.com/prever-apps/prever-apps-monitor-web/releases/download/1.0/mysqlmariadb.tar
tar -xvf prever-apps-monitor-web.tar
``` 
##### Step 2: Configure prever.properties file #####
cd prever-apps-monitor-mysqlmariadb/conf

Confgiure your account and user key in prever.properties.
```bash
prever.username=your username in prever.io
prever.userkey=your user key in prever.io
``` 

Confgiure database connection properties
```bash
jdbc.driverClassName=com.mysql.jdbc.Driver
jdbc.url=jdbc:mysql://localhost
jdbc.username=username
jdbc.password=password
``` 

Declare your status variable.
```bash
#If MySQL is frequently accessing the first row of a table index, it suggests that it is performing a sequential scan of the entire index. This indicates that the corresponding table is not properly indexed.
status.Handler_read_first = false
#If this variable is high, it suggests that MySQL's memory buffer is incorrectly configured for the amount of writes the server is currently performing.
status.Innodb_buffer_pool_wait_free = false
#It provides real-time information on how many clients are currently connected to the server. This can help in traffic analysis or in deciding the best time for a server re-start.
status.Threads_connected = true
#This value provides a benchmark to help you decide the maximum number of connections your server should support. It can also help in traffic analysis.
status.Max_used_connections = true
status.Cpu_time = true
status.Queries = true
status.Memory_used = false
status.Innodb_deadlocks = false
# Performing filesystem reads for database indexes slows query performance. If this variable is high, it indicates that MySQL's key cache is overloaded and should be reconfigured.
status.Key_reads = false
#A high value indicates that many queries are not being optimally executed. A necessary next step would be to examine the slow query log and identify these slow queries for optimization.
status.Slow_queries = false
#A high value indicates that many queries are not being optimally executed. A necessary next step would be to examine the slow query log and identify these slow queries for optimization.
status.Select_full_join = false

######################################################################
#Below fields are not STATUS's variables. These fields are generated by calculation.
status.queries_per_second = true
#Unit: kb
status.traffic_in = true
#Unit: kb
status.traffic_out = true
#Unit: %
status.buffer_usage = true
#Innodb writes per second
status.writes_per_second = true
#Innodb reads per second
status.reads_per_second = true
``` 

Note: User key can be found in your profile of Prever.io
##### Step 3: Run #####
###### Windows ######
``` 
prever/prever.bat
``` 
###### Linux ######
``` 
prever/./prever.sh
``` 
##### Step 4: Access your devices #####
Register your device in Prever.io

Login your account.
See main dashborad and you can find unregistered device.
Register the unregistered device.

##### Step 5: You are happy to play with your data #####
Wow!! all done. Enjoy and play with your device and your data.
