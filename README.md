# Allow All Squid

다 받아 주는 squid proxy

``` sh
$ cat squid.conf
# https://stackoverflow.com/a/42901717
# allow all requests
acl all src 0.0.0.0/0
http_access allow all
http_access deny all
http_port 3128
coredump_dir /var/spool/squid
refresh_pattern ^ftp:		1440	20%	10080
refresh_pattern ^gopher:	1440	0%	1440
refresh_pattern -i (/cgi-bin/|\?) 0	0%	0
refresh_pattern (Release|Packages(.gz)*)$      0       20%     2880
refresh_pattern .		0	20%	4320
```
