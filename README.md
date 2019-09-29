
### react application to show how to use redis, postgres, nginx together

also to apply the containization


use travis to build images and then push to docker.io

create aws redis database

create aws postgres database

create the beanstalk and apply the environments, to specifiy the redis and postgres hostname, userid and password



---

### install vim
```
sudo yum install vim -y
```

### install redis centos
```
sudo yum install epel-release yum-utils
sudo yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
sudo yum-config-manager --enable remi

sudo yum install redis

sudo systemctl start redis
sudo systemctl enable redis

edit /etc/redis.conf for the address bind
```
check redis port
```
ss -an | grep 6379
```

example to allow 192.168.121.0/24 to connect to redis
```
sudo firewall-cmd --new-zone=redis --permanent
sudo firewall-cmd --zone=redis --add-port=6379/tcp --permanent
sudo firewall-cmd --zone=redis --add-source=192.168.121.0/24 --permanent
sudo firewall-cmd --reload
```

### install postgres

sudo yum install postgresql-server postgresql-contrib

sudo postgresql-setup initdb

sudo systemctl start postgresql

sudo systemctl enable postgresql




