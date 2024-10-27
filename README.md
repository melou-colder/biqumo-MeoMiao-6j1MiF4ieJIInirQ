## 思维导航

* [前言](https://github.com)
* [特色功能](https://github.com)
* [功能导图](https://github.com)
* [功能模块](https://github.com)
* [支持框架](https://github.com)
* [支持环境](https://github.com)
* [项目源代码](https://github.com)
* [简单使用示例](https://github.com)
* [项目源码地址](https://github.com)
* [优秀项目和框架精选](https://github.com)

## 前言


最近有不少同学问：`.NET网络通信框架有什么好推荐的吗？`今天大姚给大家分享一款基于Apache License开源的一个整合性、功能丰富的.NET(包括 C\# 、VB.Net、F\#)网络通信框架：TouchSocket。


:[wgetCloud机场](https://tabijibiyori.org)## 特色功能


一键解决TCP黏分包问题，提供协议模板，支持快速实现固定包头、固定长度、区间字符等数据报文解析。


![](https://img2024.cnblogs.com/blog/1336199/202410/1336199-20241026090013686-741105456.png)


## 功能导图


![](https://img2024.cnblogs.com/blog/1336199/202410/1336199-20241026090032215-1298677196.png)


## 功能模块


集成了socket、TCP、UDP、SSL、namedPipe、HTTP、WebSocket、RPC、JsonRPC、WebAPI、XMLRPC、Modbus等多种通信模块。


![](https://img2024.cnblogs.com/blog/1336199/202410/1336199-20241026090045140-1629108797.png)


## 支持框架


Console、WPF、Winform、Blazor Server、Xamarin、MAUI、Avalonia、Mono、Unity 3D（除WebGL）等。


## 支持环境


.NET Framework 4\.5及以上，.NET 6\.0及以上，.NET Standard 2\.0及以上。


## 项目源代码


![](https://img2024.cnblogs.com/blog/1336199/202410/1336199-20241026090059612-162550784.png)


## 简单使用示例


### TcpService



```
TcpService service = new TcpService();service.Connecting = (client, e) => {return EasyTask.CompletedTask; };//有客户端正在连接service.Connected = (client, e) => {return EasyTask.CompletedTask; };//有客户端连接service.Disconnected = (client, e) => {return EasyTask.CompletedTask; };//有客户端断开连接service.Received = (client, e) =>{    //从客户端收到信息    string mes = e.ByteBlock.ToString();    Console.WriteLine($"已从{client.Id}接收到信息：{mes}");    return EasyTask.CompletedTask;};service.Start(7789);//启动
```

### TcpClient



```
TcpClient tcpClient = new TcpClient();tcpClient.Connected = (client, e) => {return EasyTask.CompletedTask; };//成功连接到服务器tcpClient.Disconnected = (client, e) => {return EasyTask.CompletedTask; };//从服务器断开连接，当连接不成功时不会触发。tcpClient.Received = (client, e) =>{    //从服务器收到信息    string mes = Encoding.UTF8.GetString(e.ByteBlock.Buffer, 0, e.ByteBlock.Len);    Console.WriteLine($"接收到信息：{mes}");    return EasyTask.CompletedTask;};tcpClient.Connect("127.0.0.1:7789");tcpClient.Send("RRQM");
```

## 项目源码地址


更多项目实用功能和特性欢迎前往项目开源地址查看👀，别忘了给项目一个Star支持💖。


* 开源地址：[https://gitee.com/RRQM\_Home/TouchSocket](https://github.com)
* 在线文档：[https://touchsocket.net/docs/current/startguide](https://github.com)


## 优秀项目和框架精选


该项目已收录到C\#/.NET/.NET Core优秀项目和框架精选中，关注优秀项目和框架精选能让你及时了解C\#、.NET和.NET Core领域的最新动态和最佳实践，提高开发工作效率和质量。坑已挖，欢迎大家踊跃提交PR推荐或自荐（让优秀的项目和框架不被埋没🤞）。


* GitHub开源地址：[https://github.com/YSGStudyHards/DotNetGuide/blob/main/docs/DotNet/DotNetProjectPicks.md](https://github.com)
* Gitee开源地址：[https://gitee.com/ysgdaydayup/DotNetGuide/blob/main/docs/DotNet/DotNetProjectPicks.md](https://github.com)


