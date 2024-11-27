#!/bin/bash

while :
do
    cpuUsage=$(top -bn1 | awk '/Cpu/ { print $2}')
    memUsage=$(free -m | awk '/Mem/{print $3}')

    echo "CPU Usage: $cpuUsage%"
    echo "Memory Usage: $memUsage MB"

    if systemctl is-active --quiet docker.service; then
        curl -X GET https://test.com/monitoring/test/api
        echo "Docker is running. Sent request to https://test.com/monitoring/test/api"
    else
        echo "Docker is not running."
    fi
    sleep 60
done
