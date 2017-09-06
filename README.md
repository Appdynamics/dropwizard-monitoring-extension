## Dropwizard

Dropwizard is a Java framework for developing ops-friendly, high-performance, RESTful web services.
Dropwizard pulls together stable, mature libraries from the Java ecosystem into a simple, light-weight package that lets you focus on getting things done.

Dropwizard has out-of-the-box support for sophisticated configuration, application metrics, logging, operational tools, and much more, allowing you and your team to ship a production-quality web service in the shortest time possible.
 
## Prerequisites
We will be reporting various measuring instruments that DropWizard Metrics provides. For more detailed metrics, refer: 
http://metrics.dropwizard.io/3.1.0/manual/core/

## Dropwizard Monitoring Extension

This is an addon to the Appdynamics Machine Agent. This extension collects the metrics by invoking the Dropwizard API and and displays them in the AppDynamics Metric Browser.

## Installation

1. Run 'mvn clean install' from the dropwizard-monitoring-extension directory
2. Download the file dropwizard-monitoring-extension-{version}.zip found in the 'target' directory into \<Machineagent_Install_dir\>/monitors/
3. Unzip the downloaded file
4. Open \<machineagent_install_dir\>/monitors/DropWizardMonitor/config.yaml and configure the HBase server peoperties. You can provide multiple HBase server properties.
5. Restart the machineagent

## Workbench

Workbench is a feature that lets you preview the metrics before registering it with the controller. This is useful if you want to fine tune the configurations. Workbench is embedded into the extension jar.

To use the workbench dollow all the installation steps:
1. Start the workbench with the command
java -jar /path/to/MachineAgent/monitors/DropWizard/DropWizardMonitor.zip
This starts an http server at http://host:9090/. This can be accessed from the browser.
2. If the server is not accessible from outside/browser, you can use the following end points to see the list of registered metrics and errors.
#Get the stats
curl http://localhost:9090/api/stats
#Get the registered metrics
curl http://localhost:9090/api/metric-paths
3. You can make the changes to config.yml and validate it from the browser or the API
4. Once the configuration is complete, you can kill the workbench and start the Machine Agent

## Metrics

The metrics will be reported under the tree: Server|Component:<TIER_ID>|Custom Metrics|Dropwizard

## Contributing

Always feel free to fork and contribute any changes directly via [GitHub](https://github.com/Appdynamics/dropwizard-monitoring-extension/).

## Community

Find out more in the [AppSphere](https://www.appdynamics.com/community/exchange/) community.

## Support

For any questions or feature request, please contact [AppDynamics Center of Excellence](mailto:help@appdynamics.com).
