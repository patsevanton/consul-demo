# consul-demo

On consul-backend:
```
setenforce 0
wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
yum install -y git rpmdevtools mc apache-maven
git clone https://github.com/patsevanton/consul-demo.git
cd consul-demo
mvn clean package
yum install -y backend/target/rpm/consul-backend/RPMS/noarch/consul-backend-0.0.1-1.noarch.rpm
```

On consul-client:
```
setenforce 0
wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
yum install -y git rpmdevtools mc apache-maven
git clone https://github.com/patsevanton/consul-demo.git
cd consul-demo
mvn clean package
yum install backend/target/rpm/consul-backend/RPMS/noarch/consul-backend-0.0.1-1.noarch.rpm 
```
