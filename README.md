# -Git--24bec10158-
#!/bin/bash
# Script 1: System Identity Report
# Author: [Amrita] | Course: Open Source Software
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

#!/bin/bash
# Script 2: FOSS Package Inspector
PACKAGE="" # e.g. httpd, mysql, vlc, firefox
# Check if package is installed
if rpm -q $PACKAGE &>/dev/null; then
 echo "$PACKAGE is installed."
 rpm -qi $PACKAGE | grep -E 'Version|License|Summary'
else
 echo "$PACKAGE is NOT installed."
fi
# TODO: Add a case statement that prints a one-line
# philosophy note about the package based on its name
case $PACKAGE in
 httpd) echo "Apache: the web server that built the open internet" ;;
 mysql) echo "MySQL: open source at the heart of millions of apps" ;;
 # TODO: Add your software and 3 others
esac


#!/bin/bash
# Script 3: Disk and Permission Auditor
DIRS=("/etc" "/var/log" "/home" "/usr/bin" "/tmp")
echo "Directory Audit Report"
echo "----------------------"
for DIR in "${DIRS[@]}"; do
 if [ -d "$DIR" ]; then
 PERMS=$(ls -ld $DIR | awk '{print $1, $3, $4}')
 SIZE=$(du -sh $DIR 2>/dev/null | cut -f1)
 echo "$DIR => Permissions: $PERMS | Size: $SIZE"
 else
 echo "$DIR does not exist on this system"
 fi
done
# TODO: Add a section that checks if your software's
# config directory exists and prints its permissions

#!/bin/bash
# Script 4: Log File Analyzer
# Usage: ./log_analyzer.sh /var/log/messages
LOGFILE=$1
KEYWORD=${2:-"error"} # Default keyword is 'error'
COUNT=0
if [ ! -f "$LOGFILE" ]; then
 echo "Error: File $LOGFILE not found."
 exit 1
fi
while IFS= read -r LINE; do
 if echo "$LINE" | grep -iq "$KEYWORD"; then
 COUNT=$((COUNT + 1))
 fi
done < "$LOGFILE"
echo "Keyword '$KEYWORD' found $COUNT times in $LOGFILE"
# TODO: Add a do-while style retry if the file is empty,
# and print the last 5 matching lines using tail + grep

#!/bin/bash
# Script 5: Open Source Manifesto Generator
echo "Answer three questions to generate your manifesto."
echo ""
read -p "1. Name one open-source tool you use every day: " TOOL
read -p "2. In one word, what does 'freedom' mean to you? " FREEDOM
read -p "3. Name one thing you would build and share freely: " BUILD
DATE=$(date '+%d %B %Y')
OUTPUT="manifesto_$(whoami).txt"
# TODO: Compose a paragraph using $TOOL, $FREEDOM, $BUILD
# and write it to $OUTPUT using echo and >>
echo "Manifesto saved to $OUTPUT"
cat $OUTPUT


 

