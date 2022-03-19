# 金刚矿工 - 免费构建挖矿安全隧道
金刚矿工安全隧道使用的是 http+tls 的协议，目的是伪装成普通的网页流量访问，让流量特征监控失效。    

简易使用教程：下载win安装包，解压，点击对应矿池加密脚本，修改挖矿地址，完成。  

使用金刚矿工构建加密隧道实现安全挖矿  

stratum协议是目前最常用的矿机和矿池之间的TCP通讯协议，只有在挖矿场景才会用到。  

常用的是有stratum+tcp和stratum+SSL两种，有些朋友以为用了stratum+SSL就是安全的，无法监测得到，这种想法是错误的。  

stratum+tcp和stratum+SSL只是内容数据包有没有加密的区别，但是用了SSL只是数据明文变成了加密数据，其外部特征不变的，且该协议特征明显，只有挖矿才会用到，所以经过大量数据训练，通过机器学习，该协议非常容易就能够被识别。  

举个例子，就像一辆汽车，TCP就是没有拉上窗帘，外面的人一眼就可以看到车里面的人，SSL就像拉上了窗帘，外面的人是看不到车里的人，但是还是可以一眼就看得出这是一辆汽车，而且这种车型，只有挖矿的数据才会乘坐。    

金刚矿工加密隧道介绍：    
金刚矿工安全隧道使用的是 http+tls 的协议，目的是伪装成普通的网页流量访问，让流量特征监控失效。      
![image](https://github.com/jaed52403/jingang/blob/main/JinGang%E9%98%B2%E6%8A%A4%E5%8E%9F%E7%90%86%E5%9B%BE.png)


官网在这里 https://github.com/jaed52403/jingang  
最新版下载在这里 https://github.com/jaed52403/jingang/releases  

金刚矿工3.0稳定版本重磅更新  
1，支持构建ETH/ETC矿池的加密隧道。  
2，调整了加密方法极大提高稳定性。  
3，加入了分布式节点增强了挖矿的安全和隐秘性。  
4，一键启动支持常用国内外矿池。  
5，长期支持版本，放心使用。  
6，分布式节点，保持稳定挖矿。  

免责协议：请您务必在当地法律法规允许的前提下进行  

使用方法（windows系统）：  

解压erha-miner.zip，右击编辑start.bat脚本，配置好本地端口和矿池IP  
脚本例子：erha-miner.exe -L=6666 -P=asia2.ethermine.org:5555  
参数含义：  
-L ： 本地端口，默认为6666  
-P : 挖矿地址，目前支持E池,鱼池,币印,凤池,欧易,币安,蚂蚁,hive 池,2miners,独角兽,ezil ,支持SSL方式，格式：域名+端口  
  
配置好bat文件之后，双击运行，保留窗口开启  
按文件夹里面配置好开启自动启动  
![image](https://github.com/jaed52403/jingang/blob/main/k-%E7%AE%80%E6%98%93%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B.png)

2、挖矿脚本调整：  

挖矿脚本需要调整为执行本地/局域网IP+本地端口进行加密隧道中转，本质来说就是替换原本矿池Ip，指向到本地加密去特征码后转发，达到安全的环境（因为走的是本地内网，只需要配置为TCP模式即可）  

NBminer:  
nbminer.exe -a ethash -o stratum+tcp://127.0.0.1:6666 -u YOUR_WALLET_ADDRESS.RIG_ID  
![image](https://github.com/jaed52403/jingang/blob/main/k-%E8%BD%BB%E6%9D%BE%E7%9F%BF%E5%B7%A5%E8%AE%BE%E7%BD%AE%E7%A4%BA%E4%BE%8B.png)


局域网内其他矿机加密隧道设置： 如果你有多台矿机，或者Hiveos等系统， 可以在其中一台windows矿机上运行并记录下该台机器的内网IP如192.168.1.88， 其他矿机挖矿地址填写   192.168.1.88:6666 即可统一通过隧道加密流量出去  

目前仅支持ETH矿机和ETC矿机使用，看使用量再决定是否新增BTC/LTC矿机加密隧道中转 仅供学习，请勿用于非法用途  

如果你的矿池暂时还没支持，可以去Github提交issue，我们会尽快加上  
或者进入我们的Telegram社区 => https://t.me/+YBTIqVCuU3U5YmRh  

win10系统如何设置开机自启动  
1，打开文件夹，输入C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp  
2，把bat脚本生成快捷方式，然后拉到这个启动目录下面（需要管理员权限）  
