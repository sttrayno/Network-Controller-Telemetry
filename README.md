# Network-Controller-Telemetry

Lab guide for building Grafana dashboards against Cisco network controllers


As we covered

TIG stack in detail

Grafana - Much of our time in this lab will be spend building our visuals

InfluxDB - InfluxDB in this example allows us to store our telemetry information in a time series database.

Telegraf - This is probably one of the more difficult concepts to fully understand here but Telegrafs function is to primarily act as the middle-man in this architecture collecting data from our inputs (In this case ACI, DNA-C, vManage) and formating then outputing it into our Influx time series database. The most important concept of Telegraf to get are the plugins, which can be input or output, typically our output will be to InfluxDB but could be to another type of database such as Postgre or MySQL. The input can vary depending on what system we're looking to collect data from, in this lab guide we will be using the exec input plugin to execute a python script that will connect to our controller and output the data. Telegraf's original purpose was to collect metric data from servers.
