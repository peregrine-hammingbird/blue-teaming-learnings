# THM SOC Summary(Elastic Stack)

## Room: 
Elastic Stack: The Basics

## Goal: 
I learned how to use ELK(Discover tab, KQL,Creating Visualizations,Creating Dashboards)

## Key concepts: 
Elasticsearch, Logstash, Beats, Kibana

・Beats collect data from multiple agents. For example, Winlogbeat collects Windows event logs, and Packetbeat collects network traffic flows.

・Logstash collects data from beats, ports, or files, parses/normalizes it into field value pairs, and stores them into Elasticsearch.

・Elasticsearch acts as a database used to search and analyze data.

・Kibana is responsible for displaying and visualizing the data stored in Elasticsearch. 
　The data stored in Elasticsearch can easily be shaped into different visualizations, time charts, infographics, etc., 
　using Kibana.

## What I did: 
I used ELK to search a source_ip which IP address has the maximum number of connections.
I used ELK to search a Username which user is responsible for the overall maximum traffic.
I used ELK to search a source_ip  which IP caused the spike observed in the time chart on 11th Jan.

## Detection idea: 
This could be detected by logs.

## Next action: 
Next, I will practice Introduction to SOAR
