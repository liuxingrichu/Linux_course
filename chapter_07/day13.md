### 网关 ###
网关(Gateway)又称网间连接器、协议转换器。网关在网络层以上实现网络互连，是复杂的网络互连设备，仅用于两个高层协议不同的网络互连。网关既可以用于广域网互连，也可以用于局域网互连。

网关是一种充当转换重任的计算机系统或设备。使用在不同的通信协议、数据格式或语言，甚至体系结构完全不同的两种系统之间，网关是一个翻译器。与网桥只是简单地传达信息不同，网关对收到的信息要重新打包，以适应目的系统的需求。

通常使用IP地址的最后一位为1或254，配置网关。特殊情况下，也会使用IP地址的最后一位为2，进行网关配置。若未配置网关，通过ipconfig查询，其网关信息为IPV6信息。

在不知道实际网关情况下，可以通过traceroute进行路由跟踪，或者进行网关配置测试网络是否正常，若正常，则该网关就是刚配置的网关信息。

### 广播地址 ###
广播地址(Broadcast Address)是专门用于同时向网络中所有工作站进行发送的一个地址。

在使用TCP/IP 协议的网络中，主机标识段host ID 为全1 的IP 地址为广播地址，广播的分组传送给host ID段所涉及的所有计算机。

例如，对于10.1.1.0 （255.255.255.0 ）网段，其广播地址为10.1.1.255 （255 即为2 进制的11111111 ），当发出一个目的地址为10.1.1.255 的分组（封包）时，它将被分发给该网段上的所有计算机。