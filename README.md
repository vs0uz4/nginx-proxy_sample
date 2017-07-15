# nginx-proxy_sample
Sample Repository for Nginx Proxy (https://github.com/jwilder/nginx-proxy)

# prepare for run

579/5000
Add in the local hosts file the domains whoami.local and caddy.local pointing them to the address 127.0.0.1

The location of the hosts file will depend a lot on the operating system you are using. To illustrate, we will demonstrate the location of the file on two well-known and widely used operating systems, Windows and Linux.

- In linux the file can be found in (/ etc / hosts) and should at least have the following content:
```
#
# /etc/hosts: static lookup table for host names
#

#<ip-address>	<hostname.domain.org>	<hostname>
127.0.0.1	localhost.localdomain	localhost
::1		localhost.localdomain	localhost

#host names for docker containers
127.0.0.1   whoami.local
127.0.0.1   caddy.local
::1         whoami.local
::1         caddy.local

# End of file
```


- In Windows, it can be found in (C: \ Windows \ System32 \ drivers \ etc \ hosts) and should at least have the following content:
```
# Copyright (c) 1993-2006 Microsoft Corp.
#
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.
#
# This file contains the mappings of IP addresses to host names. Each
# entry should be kept on an individual line. The IP address should
# be placed in the first column followed by the corresponding host name.
# The IP address and the host name should be separated by at least one
# space.
#
# Additionally, comments (such as these) may be inserted on individual
# lines or following the machine name denoted by a '#' symbol.
#
# For example:
#
#      102.54.94.97     rhino.acme.com          # source server
#       38.25.63.10     x.acme.com              # x client host

127.0.0.1       localhost
::1             localhost 

# hostnames for docker containers applications
127.0.0.1       whoami.local
127.0.0.1       caddy.local
::1             whoami.local
::1             caddy.local
```

# run
docker-compose up

# open in browser
http://whoami.local or http://caddy.local

** It should be noted that there are differences in the way docker containers run on Linux and Windows, so I was not able to find out if this code works 100% in the Windows environment, if it does not work, it probably will be because of that difference.