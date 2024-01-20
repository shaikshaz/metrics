Situation:To developed a bash script to monitor system metrics on Ubuntu and any compatible systems. The script focuses on CPU usage, memory usage, disk space, service status, and system logs.

Task:

The primary goal is to log and check various system metrics, including CPU, memory, disk space, service status, and system logs. Additionally, the script allows for customization by adjusting threshold values.I have also incorporated AWK commands to enhance my knowledge.

AWK-Awk is mostly used for pattern scanning and processing. It searches one or more files to see if they contain lines that matches with the specified patterns and then perform the associated actions.

Action:

Script Components:

Metrics Monitored:

CPU Usage (>90%)
Memory Usage (>90%)
Disk Space Usage (>90%)
Service Status (e.g., SSH not running)
System Logs (detect errors)
Logging Features & Customizations:

All messages are directed to a metrics.txt file.
Customization is enabled by allowing the users to adjust threshold values.
AWK Command Implementation:

AWK is utilized for formatting the metrics.txt file.
Commands like free -check for memory usage, df -h -check for disk space, top -check for CPU usage, and grep for finding errors in logs are incorporated.
Execution/Usage:

The script needs to be made executable using chmod +x metrics.sh.
I have Executed the script using ./metrics.sh or bash metrics.sh.
Dependencies:


The script is designed and to run on Ubuntu and other compatible systems.
Dependencies include tools such as htop or vmstat, which needed to be preinstalled.
Result:

The result is a comprehensive bash script that efficiently monitors and logs critical system metrics, providing users with the flexibility to customize threshold values. AWK commands enhance the script's functionality, and clear execution steps and dependencies make it user-friendly.
