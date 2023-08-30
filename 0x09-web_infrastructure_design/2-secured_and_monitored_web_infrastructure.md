## DESCRIPTION:
*Three server web infrastructure that hosts the website www.foobar.com, it must be secured, serve encrypted traffic, and be monitored.*

## EXPLANATION OF SOME SPECIFICS ABOUT THIS INFRASTRUCTURE:
+ For every additional element, why you are adding it
+ What are firewalls for?
<br/>The firewalls are to prevent malicious intrusions into each of the servers.
+ Why is the traffic served over HTTPS?
<br/>This is encrypted using an SSL certificate to prevent interception/reading of HTTP request/response.
+ What monitoring is used for?
<br/>It is used for monitoring the servers and it’s in/out performance and alerts the administrator of any problems.
+ How the monitoring tool is collecting data?
<br/>The monitoring tool observes the servers and provides key metrics about the servers' operations to the administrators.
+ Explain what to do if you want to monitor your web server QPS?
<br/>This can be monitored using any of the available monitoring services. e.g., NewRelic, DataDog, etc.

## ISSUES WITH THIS INFRASTRUCTURE:
+ Why terminating SSL at the load balancer level is an issue?
<br/>Between the load balancer and the web server, the information can still be intercepted unencrypted.
+ Why having only one MySQL server capable of accepting writes is an issue?
<br/>It becomes a SPOF.
+ Why having servers with all the same components (database, web server and application server) might be a problem?
<br/>This setup is not easily scalable, because each set of resource has to be provided repeatedly, which also leads to troubleshooting problems.
