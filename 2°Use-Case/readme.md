Here it is possible to find the logs and relative templates, ``webserverA`` and ``webserverB``, used for the 2° use-case.
In particular within the ``Logs`` folder we provide the logs of the 2 security functions used, Suricata and Squid.
Then we also reported the logs of the nginx web server.

The security event corresponsing to the logs shown for this use case is generated when the logs match the following pattern:
`[network-traffic:extensions.'http-request-ext'.request_header.'X-Malicious-Header' = 'bad_value'] REPEATS 3 TIMES WITHIN 4 SECONDS` 

The pattern is written in the STIX patterning language and it is stored in the threat knowledge base according to the STIX data model. In order to perform the matching the logs are first converted into the STIX data model, in particular into STIX Cyber Observables. The corresponding converted Suricata monitoring logs appear in the ``stix_traffic_cyber_observable.json`` file in the ``Logs`` folder.
