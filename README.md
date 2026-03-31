# -Git--24bec10158-
#!/bin/bash
# Script 1: System Identity Report
# Author: [Your Name] | Course: Open Source Software
# --- Variables ---
STUDENT_NAME="Amrita" # Fill in your name
SOFTWARE_CHOICE="Git" # Fill in your chosen software
# --- System info ---
KERNEL=$(uname -r)
USER_NAME=$(whoami)
UPTIME=$(uptime -p)
# --- Display ---
echo "================================"
echo " Open Source Audit — $STUDENT_NAME"
echo "================================"
echo "Kernel : $KERNEL"
echo "User : $USER_NAME"
echo "Uptime : $UPTIME"
# TODO: Add distro name, date, and license message
