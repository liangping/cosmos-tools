ELK is a famous and powerful log tool.  ELK stands for Elasticsearch,  Logstash and Kibana.

Prerequisites:

>     [root@iZ259zncm66Z kibana-6.4.0-linux-x86_64]# java -version
>     java version "1.8.0_25"
>     Java(TM) SE Runtime Environment (build 1.8.0_25-b17)
>     Java HotSpot(TM) 64-Bit Server VM (build 25.25-b02, mixed mode)

Install ELK:

download and unzip the following files.

> wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.4.0.tar.gz
> wget https://artifacts.elastic.co/downloads/logstash/logstash-6.4.0.tar.gz
> wget https://artifacts.elastic.co/downloads/kibana/kibana-6.4.0-linux-x86_64.tar.gz

Configuration:

1. Run elasticsearch.

> cd path/to/elasticsearch
> bin/elasticsearch
> curl http://localhost:9200/

2. Run Kibana

> cd path/to/kibana
> open config/kibana.yml and set **elasticsearch.url** to point at your Elasticsearch instance, set **server.host** to external ip
> bin/kibana
> curl http://localhost:5601

3. Run Logstash on each cosmos node.
> cd path/to/logstash
> create a cosmos.conf.
> bin/logstash -f cosmos.conf

You can download cosmos.conf from https://raw.githubusercontent.com/liangping/cosmos-tools/master/elk/cosmos.conf

Then you can manage your logs in one log management server. (Perhaps you will need wait a couple of minutes to see logs on kibana)

I hope you will enjoy this amazing tool.
