Microservices Runtime Sample for monitoring with Prometheus and Grafana. Instructions below is a quick setup if you are not running inside Docker container.

Once webMethods Microservices Runtime or Integration Server with Microservices is started, you can access metrics from http://localhost:5555/metrics 

This metrics can be redirected to Promethus and Grafana to create dashboard for the metrics supplied by webMethods Microservices Runtime.

Prometheus Installation and Configuration
--

Follow steps below for the Installation and Configuration of Prometheus Server

1.	Install Prometheus Server from https://prometheus.io/download/

2.	For windows, you can download zip file from https://github.com/prometheus/prometheus/releases/download/v2.5.0/prometheus-2.5.0.windows-amd64.tar.gz 

3.	Once downloaded, extract the content on your local machine – e.g. C:\applications\prometheus-2.5.0

4.	Copy [prometheus.yml](../prometheus/prometheus.yml) file from prometheus directory into C:\applications\prometheus-2.5.0 directory. Make sure you edit this file to point to your running instance of webMethods Microservices Runtime. By default, template points to localhost:5555

5.	Start Prometheus Server by executing  C:\applications\prometheus-2.5.0\prometheus.exe

6.	In Web Browser, Login to Prometheus Server at http://localhost:9090 and make sure that you are able to view various metrics that starts with “sag_is”

Grafana Installation and Configuration
--

Follow steps below for the Installation and Configuration of Grafana

1.	Install Grafana from http://docs.grafana.org/installation/

2.	For windows, you can download zip file from https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.3.4.windows-amd64.zip

3.	Once downloaded, extract the content on your local machine – e.g. c:\applications\grafana-5.3.4

4.	Start Grafana by executing C:\applications\grafana-5.3.4\bin\grafana-server.exe

5.	In Web Browser, Login to Grafana Server at http://localhost:3000 using default user/password – admin/admin. [You will be prompted to change the password].

6.	Create Datasource of type Prometheus from http://localhost:3000/datasources. Provide URL for Prometheus as used in step #6 above i.e. http://localhost:9090

7.	Import the template from http://localhost:3000/dashboard/import, selecting Prometheus Datasource that you created in step above. Default template for Microservices runtime is located [here](../grafana/dashboards).

8.	Once imported, you can view metrics of webMethods Microservices Runtime in Grafana. You can edit the Dashboard as per your requirements.



