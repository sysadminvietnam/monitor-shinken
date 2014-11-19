monitor-shinken
===============
Step 1: Install python on centos 6.5

yum install python

Step 2: Install pip for python

curl https://raw.githubusercontent.com/pypa/pip/master/contrib/get-pip.py | python -

Step 3: Add new user on System for Shinken

adduser shinken

Step 4: Install shinken using pip

pip install shinken
