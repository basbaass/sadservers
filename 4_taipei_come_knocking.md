https://sadservers.com/newserver/taipe

# Description: 

There is a web server on port :80 protected with Port Knocking. Find the one "knock" needed (sending a SYN to a single port, not a sequence) so you can curl localhost.

# Solution:

touch script.sh

vi script.sh 

----

#!/bin/bash

for i in $(seq 1 65535); do
	knock localhost "$i"
	if curl -s --fail  localhost:80 2> /dev/null; then
		echo "Accepted on port ${i}"
		break
	fi
done

echo $(curl localhost) | md5sum

------

chmod +x script.sh

./script.sh


