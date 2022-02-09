# HRProxy-for-RDP-CyberArk
Load balancer for CyberArk PSM servers

Pre work

yum install -y open-vm-tools vim net-tools

yum update -y 

reboot

yum install haproxy -y

reboot

firewall-cmd --zone=public --add-port=3389/tcp  --permanent

firewall-cmd --reload

systemctl enable haproxy.service

systemctl start haproxy && systemctl status haproxy

systemctl status haproxy

mv /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg-back

touch /etc/haproxy/haproxy.cfg (add content from haproxy.cfg) or copy haproxy.cfg file to /etc/haproxy/

systemctl restart haproxy && systemctl status haproxy

systemctl status haproxy

If it dose not stay running, run the below

setsebool -P haproxy_connect_any=1

systemctl restart haproxy && systemctl status haproxy

systemctl status haproxy
