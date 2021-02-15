# Useful linux stuff

Port forward TCP/UDP
```
iptables -t nat -A PREROUTING -p tcp --dport 1630:1641 -j DNAT --to-destination 10.8.0.2:1630-1641
iptables -t nat -A PREROUTING -p udp --dport 1630:1641 -j DNAT --to-destination 10.8.0.2:1630-1641
```

Start OpenVPN detached from terminal
```
sudo -b openvpn filename.ovpn
```

Check cron logs
```
grep CRON /var/log/syslog
```
