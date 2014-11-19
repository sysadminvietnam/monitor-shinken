monitor-shinken
===============
Step 1: Install python on centos 6.5

yum install python

Step 2: Install pip for python

curl https://raw.githubusercontent.com/pypa/pip/master/contrib/get-pip.py | python -

![alt tag](http://i.imgur.com/8XtsKiO.png)

Step 3: Add new user on System for Shinken

adduser shinken

Step 4: Install shinken using pip

pip install shinken

![alt tag](http://i.imgur.com/JMenIx2.png)

Step 5: Start shinken

/etc/init.d/shinken start

![alt tag](http://i.imgur.com/JV906Ak.png)

Step 6: You need install some software, the first you must su to shinken user:

su - shinken

shinken --init

shinken install linux-ssh

shinken install webui

![alt tag](http://i.imgur.com/gs5qzbW.png)

then restart services

/etc/init.d/shinken restart

![Alt text](http://i.imgur.com/YFUfR7I.png "Restart Shinken")

Step 7: Config webgui for shinken

enable webgui on shinken

sed -i "s/modules/modules          webui/g" /etc/shinken/brokers/broker-master.cfg

install authen password for webgui

shinken install auth-cfg-password

sed -i "s/modules/ modules    auth-cfg-password/g" /etc/shinken/modules/auth_cfg_password.cfg

![alt tag](http://i.imgur.com/TJ5OqbD.png)

Step 8:

restart to shinken

/etc/init.d/shinken restart

Step 9: Sigin to Webgui

URL: http://IP.ADD:7767/

user: admin

pass: admin (default)

