https://sadservers.com/scenario/saint-john

# Description

A developer created a testing program that is continuously writing to a log file /var/log/bad.log and filling up disk. You can check for example with tail -f /var/log/bad.log.
This program is no longer needed. Find it and terminate it. Do not delete the log file.

# Solution

lsof /var/log/bad.log  // find pid of bad process
kill -9 590            // kill bad process 

#Alternative 

sudo fuser -ki /var/log/app.log // faster solution becuase of built in kill with interaction
