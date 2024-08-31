In this folder, you will find the logs collected during the validation of the second use case, including the resource templates, specifically those for the services ``webserverA`` and ``webserverB``.

Additionally, the ``Logs`` folder contains the monitoring logs for the two security controls, or NSFs, that were utilized: Suricata and Squid. Operational logs for the Nginx web server are also included.

The logs provide evidence of a security event, detected by matching them, after conversion to a specific format, against the following detection pattern: `[network-traffic:extensions.'http-request-ext'.request_header.'X-Malicious-Header' = 'bad_value'] REPEATS 3 TIMES WITHIN 4 SECONDS`.

This pattern is written in the STIX patterning language and stored in the threat knowledge base according to the STIX data model. To facilitate matching, the logs are first converted into the STIX data model as STIX Cyber Observables (SCOs). The corresponding Suricata monitoring logs, converted to SCOs, can be found in the `stix_traffic_cyber_observable.json` file within the ``Logs`` folder.
