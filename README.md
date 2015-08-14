## DataDog check dns nameservers
Implements service checks for nameservers.  

Supports querying a specific name server and comparing the answer to expected results.

Currently, only A records are supported.  For hosts with multiple 'A' records, only the first
address from the nameserver is checked.

### Metrics collected
* dns.query_time :  time taken to query the name server, in milliseconds, by nameserver

### Events reported
* DNS timeout event
* DNS record mis-match
* other DNS exceptions

### Dependencies
The check requires the python module dnspython to be installed in the python instance used by the
datadog agent.

### TODO
* Implement other DNS record types, such as CNAME and PTR records.
* Support DNS round robin style records, e.g. hostnames with multiple 'A' records/addresses.
