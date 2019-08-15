
CenturyLink 6rd related config items
====================================

Firewall items
--------------

```
set firewall name WAN_IN rule 100 source address 205.171.2.64
set firewall name WAN_IN rule 100 protocol 41
set firewall name WAN_IN rule 100 action accept
```


Router interface settings
-------------------------

```
set interfaces switch switch0 ipv6 dup-addr-detect-transmits 1
set interfaces switch switch0 ipv6 router-advert cur-hop-limit 64
set interfaces switch switch0 ipv6 router-advert link-mtu 1452
set interfaces switch switch0 ipv6 router-advert managed-flag false
set interfaces switch switch0 ipv6 router-advert max-interval 30
set interfaces switch switch0 ipv6 router-advert other-config-flag false
set interfaces switch switch0 ipv6 router-advert prefix '::/64' autonomous-flag true
set interfaces switch switch0 ipv6 router-advert prefix '::/64' on-link-flag true
set interfaces switch switch0 ipv6 router-advert prefix '::/64' valid-lifetime 600
set interfaces switch switch0 ipv6 router-advert reachable-time 0
set interfaces switch switch0 ipv6 router-advert retrans-timer 0
set interfaces switch switch0 ipv6 router-advert send-advert true
```


MSS Clamping
------------

```
set firewall options mss-clamp interface-type all
set firewall options mss-clamp mss 1452
set firewall options mss-clamp6 interface-type all
set firewall options mss-clamp6 mss 1412
```


ip-up and ip-down scripts
-------------------------

```
mkdir -p /config/scripts/ppp/ip-up.d
mkdir -p /config/scripts/ppp/ip-down.d
```

Then copy the related files from the 6rd folder structure into the router


References
----------

- https://www.sosdg.org/edgerouter
- https://github.com/cpcowart/ubiquiti-scripts/blob/master/centurylink-6rd.md
- https://odensc.me/2019/05/01/centurylink-6rd/
