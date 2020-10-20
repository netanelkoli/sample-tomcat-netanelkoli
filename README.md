# sample-tomcat-netanelkoli
A simple helm chart sample to deploy tomcat with initial apache-tomcat8 app with monitoring.

# Repository content:

1. Sample tomcat8 "hello-world" .war app.
2. Build.sh to build docker image and deploy to Dockerhub
3. Helm chart to create deployment and service reosurce, exposed publicly.
4. Monitoring system, prometheus-operator, deployed on the cluster.

# Deployment steps:

1. Create a dokcerhub.conf file as stated in build.sh file.
2. Run ./build.sh script to build docker image and upload to Dockerhub repository.
3. Run the following command to deploy the helm chart to the GKE cluster:
  helm upgrade --install sample-tomcat-netanelkoli . -f values.yaml
4. Follow the README.md file in prometheus folder to deploy prometheus-operator monitoring system.
