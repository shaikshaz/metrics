# metrics
create metrics
#!/bin/bash

# Function to log messages to metrics.txt
log_message() {
  echo "[ $(date '+%Y-%m-%d %H:%M:%S') ] $1" >> metrics.txt
}

# Function to check CPU usage
check_cpu() {
  cpu_threshold=90
  cpu_usage=$(top -bn1 | grep "%Cpu" | awk '{print $2}' | cut -d. -f1)
  
  if [ "$cpu_usage" -gt "$cpu_threshold" ]; then
    log_message "High CPU usage detected: $cpu_usage%"
  fi
}

# Function to check memory usage
check_memory() {
  mem_threshold=90
  mem_usage=$(free | awk '/Mem/ {print int($3/$2*100)}')
  
  if [ "$mem_usage" -gt "$mem_threshold" ]; then
    log_message "High memory usage detected: $mem_usage%"
  fi
}

# Function to check disk space
check_disk() {
  disk_threshold=90
  disk_usage=$(df -h | awk '/\/$/ {print $5}' | cut -d% -f1)
  
  if [ "$disk_usage" -gt "$disk_threshold" ]; then
    log_message "High disk usage detected: $disk_usage%"
  fi
}

# Function to check a specific service (e.g., SSH)
check_service() {
  service_name="sshd"
  
  if ! systemctl is-active --quiet $service_name; then
    log_message "Service $service_name is not running"
  fi
}

# Function to check logs for errors
check_logs() {
  error_count=$(grep -i -E 'error|failed' /var/log/syslog | wc -l)
  
  if [ "$error_count" -gt 0 ]; then
    log_message "Errors detected in system logs: $error_count"
  fi
}

# Main monitoring function
main() {
  echo "System Metrics Monitoring Script"

  check_cpu
  check_memory
  check_disk
  check_service
  check_logs

  echo "Monitoring complete. Results logged in metrics.txt"
}

# Execute main function
main 
