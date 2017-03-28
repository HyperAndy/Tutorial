# HTTP学习笔记 
## TCP协议提供可靠的面向连接服务，采用三次握手建立连接。
+ 第一次握手：建立连接时，客户端发送SYN包(syn=j)到服务器，并进入SYN_SEND状态，等待服务器确认；
+ 第二次握手：服务器收到SYN包，向客户端返回ACK（ack=j+1），同时自己也发送一个SYN包（syn=k），即SYN+ACK包，此时服务器进入SYN_RCVD状态；
+ 第三次握手：客户端收到服务器的SYN＋ACK包，向服务器发送确认包ACK(ack=k+1)，此包发送完毕，客户端和服务器进入ESTABLISHED状态，完成三次握手。</br>
完成三次握手，客户端与服务器开始传送数据，也就是ESTABLISHED状态。

## 终止连接
   采用四次挥手断开双向连接。
1. TCP客户端发送一个FIN，用来关闭客户到服务器的数据传送。
2. 服务器收到这个FIN，它发回一个ACK，确认序号为收到的序号加1。和SYN一样，一个FIN将占用一个序号。
3. 服务器关闭客户端的连接，发送一个FIN给客户端。
4. 客户端发回ACK报文确认，并将确认序号设置为收到序号加1。
