# Network-Controller-Telemetry

Lab guide for building Grafana dashboards against Cisco network controllers

As we've convered in previous labs, TIG stack . Previously we've managed to abstract away some of the details however this lab we need to go a little deeper to start to build more custom integrations for collecting data. Before we do that let me give a bit of commentary on the individual components so you can understand where they all fit together.

## TIG stack in detail

Grafana - Much of our time in this lab will be spend building our visuals in Grafana. Grafana makes to a simple workflow to create and build visual dashboards from our datasources and supports mutliple datasources. As you should now we aware in this lab we'll be using InfluxDB as our datasource but the following instructions should get you comfortable with Grafana to allow you to integrate with other datasources. 

InfluxDB - InfluxDB in this example allows us to store our telemetry information in a time series database. In this lab we won't use InfluxDB too much other than to create a database. Most of our configuration will be done in Telegraf.

Telegraf - This is probably one of the more difficult concepts to fully understand here, Telegrafs function is to primarily act as the middle-man in this architecture collecting data from our inputs (In this case ACI, DNA-C, vManage), format then outputing into our Influx time series database. One of the most important concept of Telegraf to get are the plugins, which can be input or output, typically our output will be to InfluxDB but could be to another type of database such as Postgre or MySQL. The input can vary depending on what system we're looking to collect data from, in this lab guide we will be using the exec input plugin to execute a python script that will connect to our controller and output the data. Telegraf's original purpose was to collect metric data from servers.
