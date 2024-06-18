### Install docker
yum update
sudo yum update
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker $USER
docker --version
sudo service docker start
sudo systemctl enable docker
sudo systemctl status docker

### Install logstash
docker run -d --name logstash-filebeat -p 5044:5044  -p 9601:9600 docker.elastic.co/logstash/logstash:7.11.0-arm64

### Copy Confige file inside container
docker cp /home/ec2-user/cleanup-logstash-periodically/logstash.conf logstash-filebeat:/usr/share/logstash/pipeline/
