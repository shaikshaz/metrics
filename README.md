Objective:

This is a bash script which monitors systems metrics for the following:

CPU Usage: Checks and logs if CPU usage exceeds 90%
Memory Usage: Checks and logs if memory usage exceeds 90%.
Disk Space: Checks and logs if disk space usage exceeds 90%.
Service Status: Checks and logs if a specific service (e.gSSH) is not running.
System Logs: Checks and logs if errors are detected in system logs.

I've also implemented Logging Features & Customizations:
All messages are output to metrics.txt
You can customize my script by adjusting the threshold values
I wanted to learn how to advance my knowledge with awk command so i made sure to implement it when i was formatting the metrics.txt file and some cool commands i used a lot was:
AWK
What is awk-select data – one or more pieces of individual text
Cool command like free -check memory usage; df -h -check disk space;top-check CPU usage;grep-to find out errors

Execution/Usage:
Firstly make the script executable via chmod,metrics.sh
To execute metrics.sh or bash metrics.sh

Dependencies:
This script is run on Ubuntu and compatible .
