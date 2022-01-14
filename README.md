# kernel

* https://elinux.org/Debugging_by_printing#Printk_from_userspace

## cat kernel message
```
iptables -t filter -A OUTPUT  -p udp --dport 53 -j LOG --log-prefix 'dns request: output'

cat /proc/kmsg 
<4>[6583889.873254] dns request: outputIN= OUT=ens192 SRC=192.168.x.x DST=192.168.0.254 LEN=59 TOS=0x00 PREC=0x00 TTL=64 ID=35501 DF PROTO=UDP SPT=51962 DPT=53 LEN=39 
<4>[6583889.873359] dns request: outputIN= OUT=ens192 SRC=192.168.x.x DST=192.168.0.254 LEN=59 TOS=0x00 PREC=0x00 TTL=64 ID=35502 DF PROTO=UDP SPT=51962 DPT=53 LEN=39 
<4>[6583889.886450] dns request: outputIN= OUT=ens192 SRC=192.168.x.x DST=192.168.0.254 LEN=118 TOS=0x00 PREC=0x00 TTL=64 ID=35506 DF PROTO=UDP SPT=43396 DPT=53 LEN=98


```

## kernel restriction
* https://www.stigviewer.com/stig/red_hat_enterprise_linux_8/2020-11-25/finding/V-230269

```
kernel.dmesg_restrict = 1
sudo grep -r kernel.dmesg_restrict /etc/sysctl.conf /etc/sysctl.d/*.conf

```
