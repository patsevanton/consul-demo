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
В файле /opt/backend/bootstrap.yml host: ${CONSUL_HOST} меняем на host: DNS-или-IP-адрес-сервера-Consul
systemctl start backend
systemctl status backend
journalctl --full --no-pager -u  backend
```

On consul-client:
```
setenforce 0
wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
yum install -y git rpmdevtools mc apache-maven
git clone https://github.com/patsevanton/consul-demo.git
cd consul-demo
mvn clean package
yum install -y client/target/rpm/consul-client/RPMS/noarch/consul-client-0.0.1-1.noarch.rpm
В файле /opt/client/bootstrap.yml host: ${CONSUL_HOST} меняем на host: DNS-или-IP-адрес-сервера-Consul
systemctl start client
systemctl status client
journalctl --full --no-pager -u  client
```

![](https://habrastorage.org/webt/dk/75/vn/dk75vniggodr4tp4bcgslrmijcs.png)

![](https://habrastorage.org/webt/li/dz/er/lidzerjeidr2fmb7bnrv7y9ls-k.png)

![](https://habrastorage.org/webt/tu/rk/gn/turkgnmvdtrad7hqtjrul_iqgng.png)
