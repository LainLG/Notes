# DNS

<h3>Instalacion de paquetes<h3>

```bash
apt install bind9 bind9-dnsutils bind9-utils
cd /etc/bind
nano named.conf.local
zone "Wired"{
        type master;
        file "/etc/bind/db.Wired";
};


```bash
nano db.Wired


$TTL 3d

@ IN SOA dns.Wired.org. root.Wired.org. (
	2013031301	; Serial
	3600	; Refresh 1h
	600	; Retry 10m
	2419200	; Expiry 4w
	7200	; Minimum 2h
)

;
; Name Server
;
	IN NS dns.Wired.org.
; Delegation
;
dns.Wired.org. IN A 10.0.0.4
Connect.Wired.org. IN A 10.38.45.3

```