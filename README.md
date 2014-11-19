monitor-shinken
===============
Step 1: Install python on centos 6.5

yum install python

Step 2: Install pip for python

curl https://raw.github.com/pypa/pip/master/contrib/get-pip.py | python -

Step 3: Add new user on System for Shinken

adduser shinken

Step 4: Install shinken using pip

pip install shinken

Step 5: Start shinken

/etc/init.d/shinken start

Step 6: You need install some software, the first you must su to shinken user:

su - shinken

shinken --init


shinken install linux-ssh

shinken install webui

then restart services

/etc/init.d/shinken restart

![Alt text](http://i.imgur.com/YFUfR7I.png "Restart Shinken")

Step 7: Config webgui for shinken

enable webgui on shinken

sed -i "s/modules/modules          webui/g" /etc/shinken/brokers/broker-master.cfg

install authen password for webgui

shinken install auth-cfg-password

sed -i "s/modules/ modules    auth-cfg-password/g" /etc/shinken/modules/auth_cfg_password.cfg

Step 8:

restart to shinken

/etc/init.d/shinken restart

Step 9: Sigin to Webgui

URL: http://IP.ADD:7767/

user: admin

pass: admin (default)

