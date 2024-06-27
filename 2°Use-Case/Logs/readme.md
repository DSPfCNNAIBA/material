Here we provide an overview and a description of each folder.

## nginx
Within ``nginx`` we reported the initial requests, before the realignment workflow, to trigger the creation of alerts, monitored by Suricata.
We performed the requests with an additional header and we gathered logs from the nginx server.
Within ``nginx/curl.txt`` we provided the commands that we used from the client to perform the requests, and their related responses.
## suricata
Within ``suricata``folder we reported all the gathered logs from Suricata.
They presents both the rules in ``rules.txt`` file, that can be specified by the administrator, and the logs related to the requests monitored in the ``file-logs.json``. In particular we configured suricata to print all the details of the http requests and response.


Just to give a better clarification, 3 different requests are reported, in order to trigger the creation of the STIX logs, according to a predefined pattern.
We present the logs of suricata before and after the realignment workflow, in order to underline and demonstrate how Squid is effectively enforced.

The ``iptables-routing-rules`` file within the ``suricata``folder represents the rules used to perform the routing within one of the SF in the chain. Starting from this file and considering the interfaces, reported within the ``Templates`` folder in the ``setup-terminal`` files, is possible to recreate the traffic flow.

## Squid
Within the ``Squid`` folder we reported the request that we have used to trigger the Squid response, performed by the client, and its relative response, within ``squid.txt`` file.
The ``iptables-routing-rules`` file within the ``Squid``folder represents the rules used to perform the routing within the SF in the chain,for the specific pod, during the realignment workflow.