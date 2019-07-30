# ros-aliddns

#start a python httpservice with cgi  
#my service is in lede.  
#login in first  
  
opkg update  
opkg install python3-pip  
pip3 install -U pip  
pip3 install aliyun-python-sdk-alidns  
mkdir -p /root/pythonwww/cgi-bin  
cd /etc/init.d  
wget https://raw.githubusercontent.com/plutohiyo/ros-aliddns/master/pythonhttp  
chmod +x /etc/init.d/pythonhttp  
/etc/init.d/pythonhttp enable  
echo "0 5 * * * /etc/init.d/pythonhttp restart" >> /etc/crontabs/root  
  
#copy the file ddns.py into /root/pythonwww/cgi-bin  
cd /root/pythonwww/cgi-bin  
wget https://raw.githubusercontent.com/plutohiyo/ros-aliddns/master/ddns.py  
chmod 755 /root/pythonwww/cgi-bin/ddns.py  
  
  
#create ros scripts with the ros-ddns-template  
#change some variable  
  
