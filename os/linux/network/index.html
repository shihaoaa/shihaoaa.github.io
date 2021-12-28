传送门：[[试试Linux下的ip命令，ifconfig已经过时了](https://linux.cn/article-3144-1.html)]  
传送门：[[linux网络配置命令之ifconfig、ip和route](http://chrinux.blog.51cto.com/6466723/1188108)]  
传送门：[[linux网络工具iproute2的使用简介](http://www.linuxdiyf.com/linux/23935.html)]  
传送门：[[iproute基本介绍](https://segmentfault.com/a/1190000000638244)]  
传送门：[[iproute2手册](https://baturin.org/docs/iproute2/)]  
***
&nbsp;&nbsp;&nbsp;&nbsp;iproute2是一个linux下管理控制 TCP/IP 网络和流量控制的工具包，用以替代老的net-tools。在一些常用的Linux发行版本中，默认的网络管理工具已经是iproute2取代了net-tools，如果要使用ifconfig、route、netstat等命令需要自行安装net-tools包。存在即合理，将iproute2熟悉的好。
&nbsp;&nbsp;&nbsp;&nbsp;无论iproute2还是net-tools进行的配置都是临时，重启系统后都会丢失。永久保存需要写入配置文件，配置文件相关自行search。另一种方法是自己写开机脚本。redhat系有nmcli管理命令是命令行执行的同时会写入配置文件，有时间了写下。本文以Debian系Ubuntu为例。

net-tools vs iproute2部分命令对比![](https://github.com/shihaoaa/shihaoaa.github.io/blob/main/doc/img/iproute2VsNet-Tools)
下面是一些常用网口管理功能对比

iproute2 | net-tools
网卡连接信息
```
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
root@ubuntu:~#
```
```
root@ubuntu:~# ifconfig
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.182.128  netmask 255.255.255.0  broadcast 192.168.182.255
        inet6 fe80::20c:29ff:fe19:bddd  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:19:bd:dd  txqueuelen 1000  (Ethernet)
        RX packets 1021  bytes 297363 (297.3 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 771  bytes 91454 (91.4 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 112  bytes 8904 (8.9 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 112  bytes 8904 (8.9 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```
IP 地址查看，iproute2命令几乎都可以简写
```
root@ubuntu:~# ip a s
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
    inet 192.168.182.128/24 brd 192.168.182.255 scope global dynamic ens33
       valid_lft 1453sec preferred_lft 1453sec
    inet6 fe80::20c:29ff:fe19:bddd/64 scope link
       valid_lft forever preferred_lft forever
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
    inet 192.168.182.128/24 brd 192.168.182.255 scope global dynamic ens33
       valid_lft 1451sec preferred_lft 1451sec
    inet6 fe80::20c:29ff:fe19:bddd/64 scope link
       valid_lft forever preferred_lft forever
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip a s ens38
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff

```
```
root@ubuntu:~# ifconfig ens33
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.182.128  netmask 255.255.255.0  broadcast 192.168.182.255
        inet6 fe80::20c:29ff:fe19:bddd  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:19:bd:dd  txqueuelen 1000  (Ethernet)
        RX packets 1209  bytes 311641 (311.6 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 896  bytes 104238 (104.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
两者功能就不一一对比了，主要看下iproute2的相关功能和命令使用
iproute2
```
root@ubuntu:~# ip help
Usage: ip [ OPTIONS ] OBJECT { COMMAND | help }
       ip [ -force ] -batch filename
where  OBJECT := { link | address | addrlabel | route | rule | neigh | ntable |
                   tunnel | tuntap | maddress | mroute | mrule | monitor | xfrm |
                   netns | l2tp | fou | macsec | tcp_metrics | token | netconf | ila |
                   vrf | sr | nexthop }
       OPTIONS := { -V[ersion] | -s[tatistics] | -d[etails] | -r[esolve] |
                    -h[uman-readable] | -iec | -j[son] | -p[retty] |
                    -f[amily] { inet | inet6 | mpls | bridge | link } |
                    -4 | -6 | -I | -D | -M | -B | -0 |
                    -l[oops] { maximum-addr-flush-attempts } | -br[ief] |
                    -o[neline] | -t[imestamp] | -ts[hort] | -b[atch] [filename] |
                    -rc[vbuf] [size] | -n[etns] name | -N[umeric] | -a[ll] |
                    -c[olor]}

```
```
	ip link
		网络设备配置命令，启用、禁用设备，修改mtu、mac等
	ip addr
		网络设备配置ipv4/ipv6地址
	ip route
		路由表管理
	ip rule
		路由策略管理
	ip netigh
		令居/arp表管理
	ip tnable
		令居表配置
	ip tunnel
		隧道配置
	ip tuntap
		tun/tap设备管理
	ip netns
		net namespace
	。。。。。。。。。。啾，到这吧，还有的不常用。'''主要是不了解(～￣▽￣)～'''
```
演示用的网络结构图
![20210519211022.png](https://upload-images.jianshu.io/upload_images/26372764-8b938042f928dbcc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

***
ip link /查看网卡链路，修改网口状态、配置，添加接口
```
root@ubuntu:~# ip link help
Usage: ip link add [link DEV] [ name ] NAME 											##添加链路口
                    [ txqueuelen PACKETS ]
                    [ address LLADDR ]
                    [ broadcast LLADDR ]
                    [ mtu MTU ] [index IDX ]
                    [ numtxqueues QUEUE_COUNT ]
                    [ numrxqueues QUEUE_COUNT ]
                    type TYPE [ ARGS ]
        ip link delete { DEVICE | dev DEVICE | group DEVGROUP } type TYPE [ ARGS ]		##删除链路口
        ip link set { DEVICE | dev DEVICE | group DEVGROUP }							##配置链路口
                        [ { up | down } ]
                        [ type TYPE ARGS ]
                [ arp { on | off } ]
                [ dynamic { on | off } ]
                [ multicast { on | off } ]
                [ allmulticast { on | off } ]
                [ promisc { on | off } ]
                [ trailers { on | off } ]
                [ carrier { on | off } ]
                [ txqueuelen PACKETS ]
                [ name NEWNAME ]
                [ address LLADDR ]
                [ broadcast LLADDR ]
                [ mtu MTU ]
                [ netns { PID | NAME } ]
                [ link-netns NAME | link-netnsid ID ]
                        [ alias NAME ]
                        [ vf NUM [ mac LLADDR ]
                                 [ vlan VLANID [ qos VLAN-QOS ] [ proto VLAN-PROTO ] ]
                                 [ rate TXRATE ]
                                 [ max_tx_rate TXRATE ]
                                 [ min_tx_rate TXRATE ]
                                 [ spoofchk { on | off} ]
                                 [ query_rss { on | off} ]
                                 [ state { auto | enable | disable} ] ]
                                 [ trust { on | off} ] ]
                                 [ node_guid { eui64 } ]
                                 [ port_guid { eui64 } ]
                        [ { xdp | xdpgeneric | xdpdrv | xdpoffload } { off |
                                  object FILE [ section NAME ] [ verbose ] |
                                  pinned FILE } ]
                        [ master DEVICE ][ vrf NAME ]
                        [ nomaster ]
                        [ addrgenmode { eui64 | none | stable_secret | random } ]
                        [ protodown { on | off } ]
                        [ gso_max_size BYTES ] | [ gso_max_segs PACKETS ]
        ip link show [ DEVICE | group GROUP ] [up] [master DEV] [vrf NAME] [type TYPE]
        ip link xstats type TYPE [ ARGS ]
        ip link afstats [ dev DEVICE ]
        ip link property add dev DEVICE [ altname NAME .. ]
        ip link property del dev DEVICE [ altname NAME .. ]
        ip link help [ TYPE ]
TYPE := { vlan | veth | vcan | vxcan | dummy | ifb | macvlan | macvtap |
           bridge | bond | team | ipoib | ip6tnl | ipip | sit | vxlan |
           gre | gretap | erspan | ip6gre | ip6gretap | ip6erspan |
           vti | nlmon | team_slave | bond_slave | bridge_slave |
           ipvlan | ipvtap | geneve | vrf | macsec | netdevsim | rmnet |
           xfrm }
```
链路显示

```
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~#

```
up/down 网口
```
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link set dev ens38 up
root@ubuntu:~# ip a s ens38
3: ens38: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
    inet6 fe80::20c:29ff:fe19:bde7/64 scope link
       valid_lft forever preferred_lft forever
root@ubuntu:~# ip link set dev ens38 down
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~#
```
配置网口（示例：修改mtu,开启网卡混杂模式）
```
root@ubuntu:~# ip link show ens38
3: ens38: <BROADCAST,MULTICAST> mtu 1500 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link set dev ens38 mtu 5000
root@ubuntu:~# ip link show ens38
3: ens38: <BROADCAST,MULTICAST> mtu 5000 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link set dev ens38 promisc on
root@ubuntu:~# ip link show ens38
3: ens38: <BROADCAST,MULTICAST,PROMISC> mtu 5000 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~#
```
添加|删除 链路网口 (示例：vlan、bridge、bond)
有点多，先来history
```
ip link add bond0 type bond mode balance-rr miimon 10
ip link show
ip link set dev ens38 master bond0
ip link show
ip link add  name bond0.100 link bond0  type vlan id 100
ip link show
ip link add name br-0 type bridge
ip link show
ip link add veth1 type veth peer name veth1-peer
ip link show
ip link set dev bond0.100 master br-0
ip link set dev veth1-peer  master br-0
ip link show
cat /proc/net/bonding/bond0
history
apt-get install bridge-utils
brctl show
history
```
继续测试效果
```
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC> mtu 5000 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link add bond0 type bond mode balance-rr miimon 10
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC> mtu 5000 qdisc fq_codel state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether f2:3d:6a:86:db:b9 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link set dev ens38 master bond0
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link add  name bond0.100 link bond0  type vlan id 100
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link add name br-0 type bridge
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
11: br-0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 12:3b:29:27:da:c9 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link add veth1 type veth peer name veth1-peer
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
11: br-0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 12:3b:29:27:da:c9 brd ff:ff:ff:ff:ff:ff
12: veth1-peer@veth1: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 9a:0e:42:85:a8:f2 brd ff:ff:ff:ff:ff:ff
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip link set dev bond0.100 master br-0
root@ubuntu:~# ip link set dev veth1-peer  master br-0
root@ubuntu:~# ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
11: br-0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
12: veth1-peer@veth1: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN mode DEFAULT group default qlen 1000
    link/ether 9a:0e:42:85:a8:f2 brd ff:ff:ff:ff:ff:ff
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN mode DEFAULT group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# cat /proc/net/bonding/bond0
Ethernet Channel Bonding Driver: v3.7.1 (April 27, 2011)

Bonding Mode: load balancing (round-robin)
MII Status: down
MII Polling Interval (ms): 10
Up Delay (ms): 0
Down Delay (ms): 0
Peer Notification Delay (ms): 0

Slave Interface: ens38
MII Status: down
Speed: 1000 Mbps
Duplex: full
Link Failure Count: 0
Permanent HW addr: 00:0c:29:19:bd:e7
Slave queue ID: 0

root@ubuntu:~# brctl show
bridge name     bridge id               STP enabled     interfaces
br-0            8000.000c2919bde7       no              bond0.100
                                                        veth1-peer

```
***
ip addr / 配置IP地址增加、删除
```
root@ubuntu:~# ip addr help
Usage: ip address {add|change|replace} IFADDR dev IFNAME [ LIFETIME ] [ CONFFLAG-LIST ] 	##网口配置|修改|替换IP地址
       ip address del IFADDR dev IFNAME [mngtmpaddr]										##网口删除IP地址
       ip address {save|flush} [ dev IFNAME ] [ scope SCOPE-ID ]
                            [ to PREFIX ] [ FLAG-LIST ] [ label LABEL ] [up]				##网口配置保存|刷新，Ubuntu如果修改网络配置文件，重启网络后会出现原有的地址还存在，这时候用flush就可以清空网卡当前配置
       ip address [ show [ dev IFNAME ] [ scope SCOPE-ID ] [ master DEVICE ]				##网口配置信息显示
                         [ type TYPE ] [ to PREFIX ] [ FLAG-LIST ]
                         [ label LABEL ] [up] [ vrf NAME ] ]
       ip address {showdump|restore}

```
```
root@ubuntu:~# ip a s
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff
    inet 192.168.182.128/24 brd 192.168.182.255 scope global dynamic ens33
       valid_lft 1327sec preferred_lft 1327sec
    inet6 fe80::20c:29ff:fe19:bddd/64 scope link
       valid_lft forever preferred_lft forever
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
11: br-0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff
12: veth1-peer@veth1: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN group default qlen 1000
    link/ether 9a:0e:42:85:a8:f2 brd ff:ff:ff:ff:ff:ff
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff
root@ubuntu:~# ip addr add 192.168.182.129/24 dev veth1
root@ubuntu:~# ip a s veth1
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff
    inet 192.168.182.129/24 scope global veth1
       valid_lft forever preferred_lft forever
```
网口数据包网口类型查看，刚好之前创建几个不同类型虚拟网卡
```
root@ubuntu:~# ip -s a s veth1
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff
    inet 192.168.182.129/24 scope global veth1
       valid_lft forever preferred_lft forever
    RX: bytes  packets  errors  dropped overrun mcast
    0          0        0       0       0       0
    TX: bytes  packets  errors  dropped carrier collsns
    0          0        0       0       0       0
root@ubuntu:~# ip -d a s
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00 promiscuity 0 minmtu 0 maxmtu 0 numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:dd brd ff:ff:ff:ff:ff:ff promiscuity 0 minmtu 46 maxmtu 16110 numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
    inet 192.168.182.128/24 brd 192.168.182.255 scope global dynamic ens33
       valid_lft 1206sec preferred_lft 1206sec
    inet6 fe80::20c:29ff:fe19:bddd/64 scope link
       valid_lft forever preferred_lft forever
3: ens38: <BROADCAST,MULTICAST,PROMISC,SLAVE,UP,LOWER_UP> mtu 1500 qdisc fq_codel master bond0 state UP group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff promiscuity 1 minmtu 46 maxmtu 16110
    bond_slave state ACTIVE mii_status DOWN link_failure_count 0 perm_hwaddr 00:0c:29:19:bd:e7 queue_id 0 numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
9: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff promiscuity 0 minmtu 68 maxmtu 65535
    bond mode balance-rr miimon 10 updelay 0 downdelay 0 peer_notify_delay 0 use_carrier 1 arp_interval 0 arp_validate none arp_all_targets any primary_reselect always fail_over_mac none xmit_hash_policy layer2 resend_igmp 1 num_grat_arp 1 all_slaves_active 0 min_links 0 lp_interval 1 packets_per_slave 1 lacp_rate slow ad_select stable tlb_dynamic_lb 1 numtxqueues 16 numrxqueues 16 gso_max_size 65536 gso_max_segs 65535
10: bond0.100@bond0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff promiscuity 1 minmtu 0 maxmtu 65535
    vlan protocol 802.1Q id 100 <REORDER_HDR>
    bridge_slave state disabled priority 32 cost 100 hairpin off guard off root_block off fastleave off learning on flood on port_id 0x8001 port_no 0x1 designated_port 32769 designated_cost 0 designated_bridge 8000.0:c:29:19:bd:e7 designated_root 8000.0:c:29:19:bd:e7 hold_timer    0.00 message_age_timer    0.00 forward_delay_timer    0.00 topology_change_ack 0 config_pending 0 proxy_arp off proxy_arp_wifi off mcast_router 1 mcast_fast_leave off mcast_flood on mcast_to_unicast off neigh_suppress off group_fwd_mask 0 group_fwd_mask_str 0x0 vlan_tunnel off isolated off numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
11: br-0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:0c:29:19:bd:e7 brd ff:ff:ff:ff:ff:ff promiscuity 0 minmtu 68 maxmtu 65535
    bridge forward_delay 1500 hello_time 200 max_age 2000 ageing_time 30000 stp_state 0 priority 32768 vlan_filtering 0 vlan_protocol 802.1Q bridge_id 8000.0:c:29:19:bd:e7 designated_root 8000.0:c:29:19:bd:e7 root_port 0 root_path_cost 0 topology_change 0 topology_change_detected 0 hello_timer    0.00 tcn_timer    0.00 topology_change_timer    0.00 gc_timer    0.00 vlan_default_pvid 1 vlan_stats_enabled 0 vlan_stats_per_port 0 group_fwd_mask 0 group_address 01:80:c2:00:00:00 mcast_snooping 1 mcast_router 1 mcast_query_use_ifaddr 0 mcast_querier 0 mcast_hash_elasticity 16 mcast_hash_max 4096 mcast_last_member_count 2 mcast_startup_query_count 2 mcast_last_member_interval 100 mcast_membership_interval 26000 mcast_querier_interval 25500 mcast_query_interval 12500 mcast_query_response_interval 1000 mcast_startup_query_interval 3124 mcast_stats_enabled 0 mcast_igmp_version 2 mcast_mld_version 1 nf_call_iptables 0 nf_call_ip6tables 0 nf_call_arptables 0 numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
12: veth1-peer@veth1: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop master br-0 state DOWN group default qlen 1000
    link/ether 9a:0e:42:85:a8:f2 brd ff:ff:ff:ff:ff:ff promiscuity 1 minmtu 68 maxmtu 65535
    veth
    bridge_slave state disabled priority 32 cost 2 hairpin off guard off root_block off fastleave off learning on flood on port_id 0x8002 port_no 0x2 designated_port 32770 designated_cost 0 designated_bridge 8000.0:c:29:19:bd:e7 designated_root 8000.0:c:29:19:bd:e7 hold_timer    0.00 message_age_timer    0.00 forward_delay_timer    0.00 topology_change_ack 0 config_pending 0 proxy_arp off proxy_arp_wifi off mcast_router 1 mcast_fast_leave off mcast_flood on mcast_to_unicast off neigh_suppress off group_fwd_mask 0 group_fwd_mask_str 0x0 vlan_tunnel off isolated off numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
13: veth1@veth1-peer: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 72:68:8a:68:b2:a7 brd ff:ff:ff:ff:ff:ff promiscuity 0 minmtu 68 maxmtu 65535
    veth numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535
    inet 192.168.182.129/24 scope global veth1
       valid_lft forever preferred_lft forever

```
***
ip route 路由配置
```
root@ubuntu:~# ip route help
Usage: ip route { list | flush } SELECTOR
       ip route save SELECTOR
       ip route restore
       ip route showdump
       ip route get [ ROUTE_GET_FLAGS ] ADDRESS
                            [ from ADDRESS iif STRING ]
                            [ oif STRING ] [ tos TOS ]
                            [ mark NUMBER ] [ vrf NAME ]
                            [ uid NUMBER ] [ ipproto PROTOCOL ]
                            [ sport NUMBER ] [ dport NUMBER ]
       ip route { add | del | change | append | replace } ROUTE

```
```
root@ubuntu:~# ip  r s
default via 192.168.182.2 dev ens33 proto dhcp src 192.168.182.128 metric 100
192.168.182.0/24 dev ens33 proto kernel scope link src 192.168.182.128
192.168.182.2 dev ens33 proto dhcp scope link src 192.168.182.128 metric 100
root@ubuntu:~# ip route add 10.0.0.0/8 via 192.168.182.1 dev ens33
root@ubuntu:~# ip r s
default via 192.168.182.2 dev ens33 proto dhcp src 192.168.182.128 metric 100
10.0.0.0/8 via 192.168.182.1 dev ens33
192.168.182.0/24 dev ens33 proto kernel scope link src 192.168.182.128
192.168.182.2 dev ens33 proto dhcp scope link src 192.168.182.128 metric 100
root@ubuntu:~# ip route add default via 192.168.182.1 dev ens33
root@ubuntu:~# ip r s
default via 192.168.182.1 dev ens33
default via 192.168.182.2 dev ens33 proto dhcp src 192.168.182.128 metric 100
10.0.0.0/8 via 192.168.182.1 dev ens33
192.168.182.0/24 dev ens33 proto kernel scope link src 192.168.182.128
192.168.182.2 dev ens33 proto dhcp scope link src 192.168.182.128 metric 100
root@ubuntu:~# ping www.baidu.com
PING www.a.shifen.com (14.215.177.38) 56(84) bytes of data.

--- www.a.shifen.com ping statistics ---
6 packets transmitted, 0 received, 100% packet loss, time 5112ms

root@ubuntu:~# ip route del default via 192.168.182.1 dev ens33
root@ubuntu:~# ping www.baidu.com
PING www.a.shifen.com (14.215.177.38) 56(84) bytes of data.
64 bytes from 14.215.177.38 (14.215.177.38): icmp_seq=1 ttl=128 time=35.2 ms
64 bytes from 14.215.177.38 (14.215.177.38): icmp_seq=2 ttl=128 time=34.7 ms
64 bytes from 14.215.177.38 (14.215.177.38): icmp_seq=3 ttl=128 time=35.4 ms
64 bytes from 14.215.177.38 (14.215.177.38): icmp_seq=4 ttl=128 time=35.9 ms

--- www.a.shifen.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3005ms
rtt min/avg/max/mdev = 34.709/35.287/35.909/0.432 ms
root@ubuntu:~#

```
后续详情再补充
ip rule 路由策略配置，目前在多网卡多路由中有遇到配合ip route一起使用，如多公网中。
```
root@ubuntu:~# ip ru s
0:      from all lookup local
32766:  from all lookup main
32767:  from all lookup default
root@ubuntu:~# ip rule show  table main
32766:  from all lookup main
root@ubuntu:~# ip  route show table  main
default via 192.168.182.2 dev ens33 proto dhcp src 192.168.182.128 metric 100
10.0.0.0/8 via 192.168.182.1 dev ens33
192.168.182.0/24 dev ens33 proto kernel scope link src 192.168.182.128
192.168.182.2 dev ens33 proto dhcp scope link src 192.168.182.128 metric 100
root@ubuntu:~# ip  route show table  local
broadcast 127.0.0.0 dev lo proto kernel scope link src 127.0.0.1
local 127.0.0.0/8 dev lo proto kernel scope host src 127.0.0.1
local 127.0.0.1 dev lo proto kernel scope host src 127.0.0.1
broadcast 127.255.255.255 dev lo proto kernel scope link src 127.0.0.1
broadcast 192.168.182.0 dev ens33 proto kernel scope link src 192.168.182.128
local 192.168.182.128 dev ens33 proto kernel scope host src 192.168.182.128
local 192.168.182.129 dev veth1 proto kernel scope host src 192.168.182.129
broadcast 192.168.182.255 dev ens33 proto kernel scope link src 192.168.182.128

```
ip tuntap tun/tap设备管理  虚拟机一般使用的是tun/tap设备，容器一般使用veth或者macvlan
ip netns  net namespace管理，例如容器使用veth对设备我们只看到一个网口，另一个是通过net ns隔离，所以默认看不到。
ss ss命令用于显示socket状态
```
root@ubuntu:~# ss -anptl
State                 Recv-Q                Send-Q                               Local Address:Port                                Peer Address:Port                Process
LISTEN                0                     4096                                 127.0.0.53%lo:53                                       0.0.0.0:*                    users:(("systemd-resolve",pid=793,fd=13))
LISTEN                0                     128                                        0.0.0.0:22                                       0.0.0.0:*                    users:(("sshd",pid=1382,fd=3))
LISTEN                0                     128                                      127.0.0.1:6010                                     0.0.0.0:*                    users:(("sshd",pid=1420,fd=10))
LISTEN                0                     128                                           [::]:22                                          [::]:*                    users:(("sshd",pid=1382,fd=4))
LISTEN                0                     128                                          [::1]:6010                                        [::]:*                    users:(("sshd",pid=1420,fd=9))
root@ubuntu:~#

```
