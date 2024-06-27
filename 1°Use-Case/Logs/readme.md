# Blocking Traffic from a Specific IP
## iptables
The ``iptables`` folder shows a simple case where a rule is used to block all the traffic coming from a specific IP. Here are the different phases, showing the behavior of the traffic before and after applying the rule.

## Before Applying the Rule

Execute the following command to ping the IP address `172.16.0.1` within the client pod:

```sh
/ # ping 172.16.0.1
--- 172.16.0.1 ping statistics ---
10 packets transmitted, 10 packets received, 0% packet loss
round-trip min/avg/max = 0.128/0.566/0.798 ms
```

## After applying the rule in the iptables-sf pod:
 
```sh
"iptables -I input -s 172.16.0.1 -j DROP"
```

The result will be:
```sh
/ # ping 172.16.0.1
--- 172.16.0.1 ping statistics ---
10 packets transmitted, 0 packets received, 100% packet loss
```

So actually all the packets coming from the specific IP are dropped.

# Nginx 
Again, we reported within the ``nginx`` folder 2 different requests, within the ``curl.txt`` file, for ports 80 and 8080. As can be seen by the collected logs, the requests directed to port 80 are forbidden, while the others to port 8080 are accepted.

# Tcpdump 
Lastly, we provided also the ``tcpdump`` logs, to double check the correctness of the traffic routing.
