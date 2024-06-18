### Install docker
1. yum update
2. sudo yum update
3. sudo yum install -y docker
4. sudo service docker start
5. sudo usermod -a -G docker $USER
6. docker --version
7. sudo service docker start
8. sudo systemctl enable docker
9. sudo systemctl status docker

### Install logstash
docker run -d --name logstash-filebeat -p 5044:5044  -p 9601:9600 docker.elastic.co/logstash/logstash:7.11.0-arm64

### Copy Confige file inside container
docker cp /home/ec2-user/cleanup-logstash-periodically/logstash.conf logstash-filebeat:/usr/share/logstash/pipeline/
