# MQTT
## 1. 简介
MQTT(消息队列遥测传输)是ISO 标准(ISO/IEC PRF 20922)下基于发布/订阅范式的消息协议。它工作在TCP/IP协议族上，是为硬件性能低下的远程设备以及网络状况糟糕的情况下而设计的发布/订阅型消息协议，为此，它需要一个消息中间件。  
MQTT是一个基于客户端-服务器的消息发布/订阅传输协议。MQTT协议是轻量、简单、开放和易于实现的，这些特点使它适用范围非常广泛。在很多情况下，包括受限的环境中，如：机器与机器（M2M）通信和物联网（IoT）。其在，通过卫星链路通信传感器、偶尔拨号的医疗设备、智能家居、及一些小型化设备中已广泛使用。
## 2. MQTT特点
MQTT协议是为大量计算能力有限，且工作在低带宽、不可靠的网络的远程传感器和控制设备通讯而设计的协议，它具有以下主要的几项特性：
1、使用发布/订阅消息模式，提供一对多的消息发布，解除应用程序耦合；  
2、对负载内容屏蔽的消息传输；  
3、使用 TCP/IP 提供网络连接；  
4、有三种消息发布服务质量：  
5、小型传输，开销很小（固定长度的头部是 2 字节），协议交换最小化，以降低网络流量；  
6、使用 Last Will 和 Testament 特性通知有关各方客户端异常中断的机制。  
