# ros-aliddns

#start a python httpservice with cgi
#my service is in lede.
#login in first

opkg update
opkg install python3-pip
pip3 install -U pip
pip3 install aliyun-python-sdk-alidns

mkdir -p /root/pythonwww/cgi-bin
cd /root/pythonwww
nohup python3 -m http.server 18888 --cgi &

#copy the file ddns.py into /root/pythonwww/cgi-bin

chmod 755 /root/pythonwww/cgi-bin/ddns.py



#create ros scripts with the ros-ddns-template
#change some variable
