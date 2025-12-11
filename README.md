# win10ltsc2019-bilibili-ubw
关于win10ltsc2019安装bilibili ubw版的问题
  
这是我的系统版本：  
![win10ltsc2019](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/75d0af9ec027a44f6dfe15bc9fcb1280.png)  
  
设备是surface pro4，由于网页版b站使用稍微有些卡顿，所以折腾了一中午这东西(
  
以下是我尝试过的几个版本的，但只有一个成功。  
**1.Bibi-release**  
```shell
git clone https://github.com/cotaku/Bibi-Release
```  
  
这个是唯一成功的一个版本，因为系统内部版本为17763所以大部分安装不上  
但是尝试了通过AppxManifest.xml修改最低内部版本限制后解决了这个问题  
我的操作方式：将下载的UWP安装包改成压缩包，解压后打开文件内的AppxManifest.xml  
将TargetDeviceFamily行的MinVersion中的版本改成当前系统版本，或是10.0.10240.0之后保存  
**如图所示**  
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/5c7d0b6ac5f6b29408ee70ee755a27c0.png)  
  
之后在文件夹运行powershell，输入 Add-AppxPackage -register .\AppxManifest.xml 后就安装成功了  
**如图**
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/e119ac2a46992e82208be39c61cac9fb.png)  

---
 
  **2.Bilicopliot 哔哩助理**  
  
  ```shell
  https://github.com/Richasy/Bili.Copilot
  ```
(不得不说这个UI设计是真不错)  
  **3.Bililite**
  
  ```shell
  https://github.com/ywmoyue/biliuwp-lite
  ```

  4.
