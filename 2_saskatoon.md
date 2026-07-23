https://sadservers.com/scenario/saskatoon

# Description 

There's a web server access log file at /home/admin/access.log. The file consists of one line per HTTP request, with the requester's IP address at the beginning of each line (first column).

Find what's the IP address that has the most requests in this file (there's no tie; the IP is unique). Write the solution into a file /home/admin/highestip.txt. For example, if your solution is "1.2.3.4", you can do echo "1.2.3.4" > /home/admin/highestip.txt

NOTE: The solution IP shows 482 times, ie grep -c -F -f highestip.txt access.log returns 482, if your solution has a different (lower) number you got the wrong most common IP.

# Solution 

awk '{print $1}' access.log | sort | uniq -c | sort | tail -n 1 | awk '{print $2}' > ./highestip.txt 

// The `awk` commands extract and isolate the IP addresses from the log, while `sort` with 'uniq -c' organizes IP addresses and removes duplicates, and displays thecounts of each group/IP address.
