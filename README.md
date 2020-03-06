# Network Controller Telemetry (ACI / DNA-Centre / vManage)

In previous labs we've demonstrated how there's a plethora of data we can get from network devices with techniques such as Model Driven Telemetry or SNMP. With the rise in network controllers however there's a different level of data we can get such as network health, client health and application peformance scores. The challenge normally comes that how can we build an easy way to aggregate this data from multiple different system sources.

As we've convered in previous labs, we're going to use the TIG (Telegraf/Influx/Grafana) stack. Previously we've managed to abstract away some of the details however this lab we need to go a little deeper to start to build more custom integrations for collecting data. Before we do that let me give a bit of commentary on the individual components so you can understand where they all fit together.

## TIG stack in detail

**Grafana** - Much of our time in this lab will be spend building our visuals in Grafana. Grafana makes to a simple workflow to create and build visual dashboards from our datasources and supports mutliple datasources. As you should now we aware in this lab we'll be using InfluxDB as our datasource but the following instructions should get you comfortable with Grafana to allow you to integrate with other datasources. 

**InfluxDB** - InfluxDB in this example allows us to store our telemetry information in a time series database. In this lab we won't use InfluxDB too much other than to create a database. Most of our configuration will be done in Telegraf.

**Telegraf** - This is probably one of the more difficult concepts to fully understand here, Telegrafs function is to primarily act as the middle-man in this architecture collecting data from our inputs (In this case ACI, DNA-C, vManage), format then outputing into our Influx time series database. One of the most important concept of Telegraf to get are the plugins, which can be input or output, typically our output will be to InfluxDB but could be to another type of database such as Postgre or MySQL. The input can vary depending on what system we're looking to collect data from, in this lab guide we will be using the exec input plugin to execute a python script that will connect to our controller and output the data. Telegraf's original purpose was to collect metric data from servers.

## Test environment

## TIG Deployment

## Influx config

## Telegraf config

## Collection scripts

## Grafana Config
