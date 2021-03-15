https://www.programmersought.com/article/7345829720/


Centos build ssr+bbr

PlayUnmute
Fullscreen
VDO.AI
Centos build ssr+bbr
Deploy ssr

Run the following command with one click.

wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh

chmod +x shadowsocksR.sh

./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
1
2
3
4
5
then

set password 
 Set the port (the firewall should remember to open)
 Set encryption default
 Set protocol plugin 3
 Set confusion plugin 6
 Automatic deployment
 Write down the account password and other information after completion.
1
2
3
4
5
6
7
Deploy bbr to speed up vps servers

wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh

chmod +x bbr.sh

./bbr.sh
1
2
3
4
5
Press any key to continue and restart the server, the server ends here.
If the client detects that the 500 status code is returned, the server ssr port is not enabled.

Open a port and run the following command

iptables -A INPUT -p tcp --dport 19566 -j ACCEPT
iptables -A OUTPUT -p tcp --sport 19566 -j ACCEPT

service iptables save
1
2
3
4
Common command

Start: service shadowsocks start
 Stop: service shadowsocks stop
 Restart: service shadowsocks restart
 Status: service shadowsocks status
1
2
3
4
There are also such commands to open the service (refer to)

The front desk is running:

ssserver -c /etc/shadowsocks.json
1
Background process:

ssserver -c /etc/shadowsocks.json -d start

ssserver -c /etc/shadowsocks.json -d stop
1
2
3

Golang tcp forwarding remoteAddr error
VDO.AI
Intelligent Recommendation
OpenVZ VPS installs BBR to accelerate SSR
In general, VPS providers also integrate KVM with BBR, but like many students who are as poor as me, many times they are not very expensive to buy KVM, only openVZ. But this does not change the kernel...


Build an SSR
Build an SSR First, you have to have a server first. for example I am this CentOS 7 x64 Second, build the Shadowsocks server side It is now ready to use! ! ! Third, accelerate only supports CentOS6 x6...


SSR build
I used v2ray before, but the CPU usage exceeded 100% at one time. I seriously doubted whether I was a miner, so I found SSR again. Reference original link:https://www.salivawar.com/panel/2019/11/06/18...

BBR Acceleration Centos
What is BBR? BBR is a new congestion control algorithm proposed by Google that enables Linux servers to significantly increase throughput and reduce TCP connection latency. BBR project address https:/...

CentOS open BBR
Step1： 1, yum system updates 2. Check system version As said output has been upgraded to 7.6 3, install and upgrade the kernel elrepo 4, after installation use the following command to view the curren...