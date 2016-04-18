# Collect-System-Metrics

It is a project for collecting system matrics by using Topbeat. Purpose of this project is to collect and transfer system metrics ( CPU usage, Memory usage and Disk usage ) in real-time.

For This I am using Topbeats,Elasticsearch,Kibana Dashboard.

## STEP BY STEP GUIDE :

#### 1)Install Elasticsearch,Topbeat and Kibana.
[https://www.elastic.co/guide/en/elasticsearch/reference/current/_installation.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/_installation.html)

[https://www.elastic.co/guide/en/beats/topbeat/current/topbeat-installation.html](https://www.elastic.co/guide/en/beats/topbeat/current/topbeat-installation.html)

[https://www.elastic.co/downloads/kibana](https://www.elastic.co/downloads/kibana)

####2)Start Elastic search
Open Terminal and go to Elasticsearch Directory and run elasticsearch

`./bin/elasticsearch`

Note the publish address in http row. Genrally it is `127.0.0.1:9200` (`localhost:9200`).

![Publish address screenshot](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/1.png "Elasticseach publish address")

we can check elasticsearch by hitting publish address in browser.

####3)Configure and start Topbeat

Configuration file of Topbeat is topbeat.yml 
Check the host in topbeat.yml. It must be same as publish address of Elasticsearch.

![Topbeat Configuration](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/2.png "Topbeat Configuration")

####4)Start Kibana

Go to the Kibana Directory on Terminal 
and hit `./bin/kibana`

![Kiban Server IP](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/3.png "Kiban Server IP")

Note the ip at which kibana is running genrally it id http://0.0.0.0:5601

####5)Load Beats dashboard
Open Terminal and navigate to beat-dashboards 
To load the dashboards, execute the script pointing to the Elasticsearch HTTP URL:

    # Unix
    ./load.sh -url "http://localhost:9200"

    # Windows
    .\load.ps1 -url "http://localhost:9200"`
    
    
If you want to use HTTP authentication for Elasticsearch, you can specify the credentials as a second parameter:

     `# Unix
    ./load.sh -url "http://localhost:9200" -user "admin:secret"

    # Windows
    .\load.ps1 -url "http://localhost:9200" -user "admin:secret"`
    

Where "http://localhost:9200" is publish address of elasticsearch. If it is different then replace it with appropriate address.

####6)Go To Kibana Dashboard 
Go to the ip address of kibana server (`http://0.0.0.0:5601`)

![Kiban Dashboard](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/4.png "Kiban Dashboard")

Now go to:

`Dashboard=>load saved dashboard=>Topbeat Dashboard `

Now All the server Metrics will visualize in your browser.

![Kiban Dashboard](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/5.png "Kiban Dashboard")

![Kiban Dashboard](https://github.com/sunnygkp10/Collect-System-Metrics/blob/master/screenshots/6.png "Kiban Dashboard")


