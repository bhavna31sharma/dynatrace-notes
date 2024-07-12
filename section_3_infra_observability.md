
## Section-2-The-Basics
- Dynatrace OneAgent Software is to be installed on your Host.

## Section-3-Infrasturcture-Observability
- Infra Observailbilty > Hosts
- to go to Classic View, three dots > classic view
- Diff types of problems - https://docs.dynatrace.com/docs/platform/davis-ai/basics/events/event-types/resource-events
    - Custom resource contention event - This generic resource contention event can be used by monitoring plugins or through the Dynatrace REST API to raise a customized resource contention event with a user-defined title. An example might be a custom resource contention event with a user-defined title - eg: Low batch job pool
 - Availability of host can be tracked. In case, your shut down is having maintenance window set up and thus dynarace should not count this as problem, set it up in Manage > Settings > Maintainence Window. You can add filters to the maintenance settings so that it only applies to filtered entities
    - availability status
        - Running
        - Offline
        - Maintenance
        - Unmonitored (OneAgent not running on host)
- Processes > All processes, can go within the process now to see detailed processes list         
- Events > CPU Saturations, Low Disk Space, Process Restart, Host or monitoring unavailable, etc
    - Events are specific occurrences or changes in the state of your monitored environment. These can be anything from deployment changes, service restarts, configuration changes, or performance anomalies.
    - Dynatrace categorizes events into different types such as Info, Error, Performance, Availability, Resource, and Custom events.
    - Events are usually more granular and specific, providing detailed information about particular occurrences within the monitored environment.
- Problems
    - Problems in Dynatrace are aggregated and correlated collections of events and anomalies that indicate a broader issue or incident affecting the monitored environment. A problem typically represents a significant impact on service performance, availability, or user experience.
    - Dynatrace automatically correlates related events and anomalies to form a single problem. This means that multiple events (like CPU spikes, slow response times, or service outages) that are related to the same root cause are grouped together into one problem.    
- Logs section to identify issues around specific log events and see how it relates to hosting performance or processes.
    - And because we're using the same timeline as the rest of the sections here, it makes it really easy to compare host performance metrics or process metrics around the time the log error took place.
    - And you can filter the logs based on process group status, log level and other.    
    - Settings > Monitoring - Monitored Technologies > Log Monitoring > Edit
        - Monitor Log monitoring on every host, else
        - Can go to individual host > ... > Settings > Log Monitoriong > Enable on this host
        - Or Settings > In left pane, click on Log monitoring to set more advanced settings 
- Settings > Monitoring > Monitoring Overview > Hosts
    - Infra only monitoring
    - full stack monitoring (3 times expensive)    
    - For K8s, no price difference on basis of pod size
    - https://docs.dynatrace.com/docs/manage/monitoring-consumption-classic/application-and-infrastructure-monitoring
    - https://docs.dynatrace.com/docs/platform-modules/infrastructure-monitoring/hosts/monitoring-modes
    
- Processes > All processes, can go within the process now to see detailed processes list          
- If a problem is detected as Frequent Issue over a period of time- Dynatrace will send alert only if severity increases. TO turn it off, Settings > Anamoly Detection > Frequent Issue Detection. 
- By default, host name come as DNS name. To rename, host > ... > just type the name
