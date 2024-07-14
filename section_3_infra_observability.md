
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
- By default, host name come as DNS name. To rename, host > ... > Settings> General > just type the name
    - Change all host name following rule, Settings > Monitoring - Host Naming > Add new Rule
- For a host > Settings > Disk options (to exclude specific disk) or Exclude network traffic

- Infra Observability > Host Networking
    - Connections - Usually overloaded processes can have trouble accepting new connections resulting in refused connections or timeout connections
    - Retransmissions usually should not be greater than 2%. If greater thatn 3% or 4%, can negatively impact user experience


## Section-4-Cloud-Automation
- Chat option top right corner
- Cloud Automation - can contact the DT team to have this functionality
- Under cloud automation, we have
    - RELEASES
    - Service-level Objectives
    - Orchestration Projects
- Release monitoring
    - release stages of different deployed versions.
    - versions across your deployment stages and prod environment
    - known bugs and if these are release blockers
    - risk related to specific versions
    - how new version behaving compared to previous versions
    - name, release version, build version, stage, product, latest validation
        - can filter on problem impacted releases, secuurity vulns impacted releases, etc
    - Under release events, all events eg: process restart, deployment events
    - tracked issues - you can link your tracker here eg: jira tracker
    - https://docs.dynatrace.com/docs/platform-modules/automations/release-monitoring/version-detection-strategies
- Service level objectives
    - to find how reliable the service is
    - service level indicator to define measure how successful the delivery is
    - eg: cart loading time < 250 ms
    - A Service Level Indicator (SLI) is a metric that quantifies the performance of a service in a way that is meaningful to users
        - Examples
            - availability - how much the service was available    
            - latency - time taken to respond by the service - for db, %age of quueries completed inn less than 200 ms
            - error rate - eg: for API, %age of requests resulting in 5XX sserver error
            - Throughput
            - Durability
            - Coverage - eg: for CDN, %age of global regions having access to service
    - Dynatrace New SLO
        - Service side objective - service level availability, service-method availability, service performance (good mins/total mins)
        - Client side objective - User experience, mobile crash-free users, synthetic availability (involves simulating user interactions with a service to test its performance and availability)
        - You can define target, warning on available metrics

 ## Section-5-Application-Observability  
 - FrontEnd
    - details by browser
    - user type (real, synthetic, robots)
    - geolocation breakkdown
    - load actions (with avg time for loading a page)
    - XHR actions (any user action)
    - custom user actions (eg: durationtime of some javascript code)
    - apdex rating (overall performannce ratings)
    - number of errors per minute with error type
    - resources (3rd party, 1st party, cdn)
    - your services
        - response time, requests, error rate, service flow
    - availability
    - composite metrics across response time (helpful to analyze where your performance should be) with compare to previous time frame option
    - top 3 pages
    - top 3 included domains
    - top errors
    - top 3 user actions
    - problems 




