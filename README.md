# pkg

```
 ipset create switch hash:ip
 ipset add switch 192.168.31.110
 iptables -A INPUT -p tcp -s 192.168.31.110 -j REDIRECT --to-port 1081


ipset -N gfwlist iphash -!
iptables -t nat -A PREROUTING -p tcp -s 192.168.31.110 -j REDIRECT --to-port 1081
iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081



ipset -N gfwlist iphash -!
ipset create switch hash:net
ipset add switch 192.168.31.110
iptables -t nat -A PREROUTING -p tcp -m set --match-set switch src -j REDIRECT --to-port 1081
iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081





ok
ipset -N gfwlist iphash -!
iptables -t nat -A PREROUTING -p tcp -s 192.168.31.110 -j REDIRECT --to-port 1081
iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081


```
