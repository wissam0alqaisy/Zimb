# Zimb
Zimbra Install
1: Edit your host file vi /etc/hosts and make sure that you have FQDN entry in it (e.g. 192.168.124.32 mail.zimbracentos.lan zimbracentos.lan)


yum -y install bind bind-utils*
nano /etc/named.conf

zone "example.com" IN {
	type master;
	file "example.com.zone";
	allow-update { none; };
};

nano /etc/named.rfc1912.zones
rev
cd /var/named
cp named.empty zimbracentos.zone.
nano zimbracentos.zone

@       IN SOA  ns1.storeak.net. your.email.here. (
                                        0       ; serial
                                        1D      ; refresh
                                        1H      ; retry
                                        1W      ; expire
                                        3H )    ; minimum
@       IN      NS      ns1.storeak.net.
@       IN      MX      0 mailos.storeak.net.
ns1     IN      A       10.0.0.4
mail    IN      A       10.0.0.4

cp named.loopback zimbracentos.rev

nano zimbracentos.rev.

@       IN SOA  storeak.net. your.admin.email.here. (
                                        1       ; serial
                                        1D      ; refresh
                                        1H      ; retry
                                        1W      ; expire
                                        3H )    ; minimum
@       IN      NS      ns1.storeak.net.
@       IN      A       10.0.0.4
32      IN      PTR     mail..


 Run the command "chgrp named zimbracentos.zone" and "chgrp named zimbracentos.rev". 
systemctl start named
systemctl enabel named
"named-checkconf -z
 /etc/named.conf" = This will check your conf file for possible error. This will also show if you have error on your zone file.

"named-checkzone zonefilename.zone /var/named/zonefilename.zone" = This will check error on the zone file.
"named-checkzone zonefilename.zone /var/named/zonefilename.rev" 
systemctl restart named
cat /etc/resolv.conf
named-checkzone zonefilename.zone /var/named/zonefilename.zone
ping to ip

hostneam -f
cat /etc/hosts
systemctl status named

yum -y install perl-core libaio unzip nmap-ncat sysstat openssh-clients

https://files.zimbra.com/downloads/8.8.5_GA/zcs-8.8.5_GA_1894.RHEL7_64.20171026035615.tgz

scp /opt/zimbra.tgz
tar xvf zimbra.tgz
cat /etc/resolv.conf

systemctl status
systemctl stop postfix
systemctl stop postfix

7
4
r
a

systemctl status firw

firewall-cmd --add-port=7071/tcp --permanent --zone=public
firewall-cmd  --permanent --zone=public --add-service{http.https}
firewall-cmd reload

su - zimbra
zmprov gs `zmhostname` -zimbraServiceInstalled dnscache  -zimbraServiceEnabled
zmcontorl status
