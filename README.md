rpm -i telet.rpm // install telnet appplication
rpm -e telnet // unsistall
rpm -q telnet //querry
yum list ansible
yum --showduplicates list ansile
sudo 
/etc/sudoers
ls or cat /etc/*release*

cd /etc/systemd/system
vim myapp.service

[Unt]
Description=My Python web application
[service]
ExecStart=/usr/bin/python3 /opt/code/my_app.py

[Install]
WantedBy=multi-user.target
systemctl daemon-reload
systemctl start my_app
systemctl status my_app
systemctl stop my_app

Use below command to see what is default editor.
update-alternatives --display editor

/usr/lib/systemd/system/app.service
[Unit]
Description=My python web application

[Service]
ExecStart=/usr/bin/python3 /opt/code/my_app.py
ExecStartPre=/bin/bash /opt/code/configure_db.sh
ExecStartPost=/bin/bash /opt/code/email_status.sh
Restart=always

[Install]
WantedBy=multi-user.target



# sudo systemctl cat app.service


app.py
import os
from flask import Flask
app = Flask(__name__)

@app.route("/")
def main():
    return "Welcome!"

@app.route('/how are you')
def hello():
    return 'I am good, how about you?'

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=8081)













     sudo pip intall -r requirements.txt 
