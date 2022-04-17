### 1. Channel 接口

基本的IO操作(bind, connect, read, write)依赖于网络底层传输所提供的原语. 在Java网络编程中, 其基本结构是class Socket. 

netty大大降低了直接使用Socket的复杂性.



### 2. EventLoop接口

EventLoop用于处理连接的生命周期中所发生的事情. 

![image-20220417152251619](https://github.com/shitianer/images/blob/master/image-20220417152251619.png?raw=true)

(1) 一个EventLoopGroup包含一个或者多个EventLoop

(2) 一个EventLoop在它的生命周期内只和一个Thread绑定

(3) 所有由EventLoop处理的IO事件都将在它专有的Thread上被处理

(4) 一个Channel在它的生命周期内只注册于一个EventLoop

(5) 一个EventLoop可能会被分配给一个或多个Channel



### 3. ChannelFuture

netty中所有的IO操作都是异步的, 一个操作可能不会立即返回, 所以需要一种用于在之后的某个时间点确定其结果的方法. 

为此提供了ChannelFuture接口.

