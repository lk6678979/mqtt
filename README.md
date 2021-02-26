# MQTT
## 1. 简介
简介原帖：https://blog.csdn.net/qq_28877125/article/details/78325003  
&emsp;&emsp;MQTT（Message Queuing Telemetry Transport，消息队列遥测传输协议），是一种基于发布/订阅（publish/subscribe）模式的"轻量级"通讯协议，该协议构建于TCP/IP协议上，由IBM在1999年发布。MQTT最大优点在于，可以以极少的代码和有限的带宽，为连接远程设备提供实时可靠的消息服务。作为一种低开销、低带宽占用的即时通讯协议，使其在物联网、小型设备、移动应用等方面有较广泛的应用。  
&emsp;&emsp;MQTT是一个基于客户端-服务器的消息发布/订阅传输协议。MQTT协议是轻量、简单、开放和易于实现的，这些特点使它适用范围非常广泛。在很多情况下，包括受限的环境中，如：机器与机器（M2M）通信和物联网（IoT）。其在，通过卫星链路通信传感器、偶尔拨号的医疗设备、智能家居、及一些小型化设备中已广泛使用。  
### 1.1. 设计规范
由于物联网的环境是非常特别的，所以MQTT遵循以下设计原则：  

（1）精简，不添加可有可无的功能；  

（2）发布/订阅（Pub/Sub）模式，方便消息在传感器之间传递；  

（3）允许用户动态创建主题，零运维成本；  

（4）把传输量降到最低以提高传输效率；  

（5）把低带宽、高延迟、不稳定的网络等因素考虑在内；  

（6）支持连续的会话控制；  

（7）理解客户端计算能力可能很低；  

（8）提供服务质量管理；  
 
（9）假设数据不可知，不强求传输数据的类型与格式，保持灵活性。
### 1.2. 主要特性
MQTT协议工作在低带宽、不可靠的网络的远程传感器和控制设备通讯而设计的协议，它具有以下主要的几项特性：  

（1）使用发布/订阅消息模式，提供一对多的消息发布，解除应用程序耦合。  

 这一点很类似于XMPP，但是MQTT的信息冗余远小于XMPP，,因为XMPP使用XML格式文本来传递数据。  

（2）对负载内容屏蔽的消息传输。  

（3）使用TCP/IP提供网络连接。  

 主流的MQTT是基于TCP连接进行数据推送的，但是同样有基于UDP的版本，叫做MQTT-SN。这两种版本由于基于不同的连接方式，优缺点自然也就各有不同了。  

（4）有三种消息发布服务质量：  

 “至多一次”，消息发布完全依赖底层TCP/IP网络。会发生消息丢失或重复。这一级别可用于如下情况，环境传感器数据，丢失一次读记录无所谓，因为不久后还会有第二次发送。这一种方式主要普通APP的推送，倘若你的智能设备在消息推送时未联网，推送过去没收到，再次联网也就收不到了。  

 “至少一次”，确保消息到达，但消息重复可能会发生。  

 “只有一次”，确保消息到达一次。在一些要求比较严格的计费系统中，可以使用此级别。在计费系统中，消息重复或丢失会导致不正确的结果。这种最高质量的消息发布服务还可以用于即时通讯类的APP的推送，确保用户收到且只会收到一次。  

（5）小型传输，开销很小（固定长度的头部是2字节），协议交换最小化，以降低网络流量。

 这就是为什么在介绍里说它非常适合“在物联网领域，传感器与服务器的通信，信息的收集”，要知道嵌入式设备的运算能力和带宽都相对薄弱，使用这种协议来传递消息再适合不过了。

（6）使用Last Will和Testament特性通知有关各方客户端异常中断的机制。

Last Will：即遗言机制，用于通知同一主题下的其他设备发送遗言的设备已经断开了连接。

Testament：遗嘱机制，功能类似于Last Will。

