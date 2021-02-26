# MQTT
## 1. 简介
简介原帖：https://blog.csdn.net/qq_28877125/article/details/78325003  
  MQTT（Message Queuing Telemetry Transport，消息队列遥测传输协议），是一种基于发布/订阅（publish/subscribe）模式的"轻量级"通讯协议，该协议构建于TCP/IP协议上，由IBM在1999年发布。MQTT最大优点在于，可以以极少的代码和有限的带宽，为连接远程设备提供实时可靠的消息服务。作为一种低开销、低带宽占用的即时通讯协议，使其在物联网、小型设备、移动应用等方面有较广泛的应用。  
  MQTT是一个基于客户端-服务器的消息发布/订阅传输协议。MQTT协议是轻量、简单、开放和易于实现的，这些特点使它适用范围非常广泛。在很多情况下，包括受限的环境中，如：机器与机器（M2M）通信和物联网（IoT）。其在，通过卫星链路通信传感器、偶尔拨号的医疗设备、智能家居、及一些小型化设备中已广泛使用。  
## 2. 设计规范
由于物联网的环境是非常特别的，所以MQTT遵循以下设计原则：  

（1）精简，不添加可有可无的功能；  

（2）发布/订阅（Pub/Sub）模式，方便消息在传感器之间传递；  

（3）允许用户动态创建主题，零运维成本；  

（4）把传输量降到最低以提高传输效率；  

（5）把低带宽、高延迟、不稳定的网络等因素考虑在内；  

（6）支持连续的会话控制；  

（7）理解客户端计算能力可能很低；  

（8）提供服务质量管理；  
 
