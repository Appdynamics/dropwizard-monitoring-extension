## Dropwizard
Dropwizard is a Java framework for developing ops-friendly, high-performance, RESTful web services.
Dropwizard pulls together stable, mature libraries from the Java ecosystem into a simple, light-weight package that lets you focus on getting things done.

Dropwizard has out-of-the-box support for sophisticated configuration, application metrics, logging, operational tools, and much more, allowing you and your team to ship a production-quality web service in the shortest time possible.

## Dropwizard Monitoring Extension
This is an addon to the Appdynamics Machine Agent. This extension collects the metrics by invoking the Dropwizard API and and displays them in the AppDynamics Metric Browser.
 
## Prerequisites
We will be reporting various measuring instruments that DropWizard Metrics provides. For more detailed metrics, refer: 
http://metrics.dropwizard.io/3.1.0/manual/core/

## Usage
 Please take a look at the class `com.appdynamics.monitors.DropwizardMonitor` as the starting point.
 The `execute` method is the entry method.  This class does the initialization and triggers the execution
 of the task `com.appdynamics.monitors.DropwizardMonitorTask`.
 
 The task in this case is executed in a thread pool. The business logic is contained in the task class. 
 The task class fetches the data through an http call and then reports the metric.  
  
## Build
 Its maven, you know how to build!
 `mvn clean install`

## Workbench 
 1. After the build, copy the `StarterMonitor-1.0.0.zip` to `<Machine-Agent>/monitors`
 2. Run `java -jar extensions-starter-http.jar` to start the workbench server.
 3. Open http://localhost:9090 from a browser to see the workbench preview.
 
## Files
  1. `DropwizardMonitor.java`
  2. `DropwizardMonitorTask.java`
  3. `monitor.xml`
  4. `config.yml`
  5. `pom.xml`
  
## Metrics

The metrics will be reported under the tree: Server|Component:<TIER_ID>|Custom Metrics|Dropwizard


## Contributing

Always feel free to fork and contribute any changes directly via [GitHub](https://github.com/Appdynamics/dropwizard-monitoring-extension/).

## Community

Find out more in the [AppSphere](https://www.appdynamics.com/community/exchange/) community.

## Support

For any questions or feature request, please contact [AppDynamics Center of Excellence](mailto:help@appdynamics.com).
