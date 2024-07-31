# 基于android9.0的binder机制详解
 android进程间通信方式：

1.Broadcast Receiver:

广播接收器,用于监听并响应系统广播或者自定义广播消息。通过注册Broadcast Receiver，可以实现在应用内或跨应用之间进行通信和数据传递,底层实现是binder。

2.Content Provider:

内容提供者,是用于管理和共享应用程序数据的组件。通过Content Provider，应用程序可以对数据进行增删改查操作，并且可以让其他应用程序通过URI来访问这些数据，
实现数据共享,Android系统提供的一些默认Content Provider来访问系统数据，如联系人、媒体库等，底层实现是binder。

Socket编程：可以使用Socket套接字进行网络通信，通过建立Socket连接在不同设备之间传输数据实现进程间通信。

3.文件：

 3.1.Shared Preferences：SharedPreferences是Android提供的轻量级的数据存储机制，可以保存和读取键值对数据，也可以用来实现简单的数据共享,不安全。
 3.2.File API,通过文件读写实现，不安全。

4.AIDL:
Android Interface Definition Language (AIDL) 是一种IDL (Interface Definition Language) 用于生成可以在Android设备上两个进程之间进行进程间通信(IPC)的代码，
底层实现是binder。

5.Messenger:
Messenger是一种轻量级的进程间通信机制，基于AIDL，Handler和Message。通过Messenger，可以在不同进程之间发送消息，实现简单的进程间通信,底层实现是binder。

6.Intent
可以通过Intent传递数据和消息，但是只能传递一些简单的数据类型，比如字符串、整数等。
从一个应用程序启动其它进程(应用)应用程序的界面(Activity)并携带数据数据,从一个服务启动其它进程(应用)的服务(Service),并携带数据数据,底层实现是binder。
