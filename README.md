# win10ltsc2019-bilibili-ubw
关于win10ltsc2019安装bilibili ubw版的问题
  
这是我的系统版本：  
![win10ltsc2019](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/75d0af9ec027a44f6dfe15bc9fcb1280.png)  
  
设备是surface pro4，由于网页版b站使用稍微有些卡顿，所以折腾了一中午这东西(
  
以下是我尝试过的几个版本的，但只有一个成功。  

---

## **1.Bibi-release**  
  
```shell
https://github.com/cotaku/Bibi-Release
```  
  
这个是唯一成功的一个版本，因为系统内部版本为17763所以大部分安装不上  
但是尝试了通过AppxManifest.xml修改最低内部版本限制后解决了这个问题  

### 我的操作方式： 
(1)将下载的UWP安装包改成压缩包，解压后打开文件内的AppxManifest.xml  
(2)将TargetDeviceFamily行的MinVersion中的版本改成当前系统版本，或是10.0.10240.0之后保存  

**如图所示**  
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/5c7d0b6ac5f6b29408ee70ee755a27c0.png)  
  
之后在文件夹运行powershell，输入这串东西就可以了
``` shell
shellAdd-AppxPackage -register .\AppxManifest.xml
```

**如图**
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/e119ac2a46992e82208be39c61cac9fb.png)  

---
 以下三个是我尝试过后有各种问题安装不上的几个版本  
## **2.Bilicopliot 哔哩助理**  
  
  ```shell
  https://github.com/Richasy/Bili.Copilot
  ```
(不得不说这个UI设计是真不错)  
   
## **3.Bililite**
  
  ```shell
  https://github.com/ywmoyue/biliuwp-lite
  ```
这是我遇到的问题：  
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/ff8234e4800b51f68f41efab5df5c136.png)  
喂给deepseek说是缺少WinUI框架，但是我也没搞定，这就涉及到另一个问题我的surface pro4的微软商店用不了这件事（  

## **4.哔哩**  
一个已经似了好久的软件，签名只支持到2024，但是可以通过修改电脑时间来签名  
```shell
https://github.com/Richasy/Bili.Uwp
```


---
另一个就是安装过后的问题。  
安装Bibi后硬解发生黑屏现象只要安装一个HEVC就好了，当然微软商店要花7元钱不过压根就打不开  
所以在浏览器下载  
``` shell
https://www.free-codecs.com/
```
下载后是AppxBundle文件，如果双击安装不了就直接通过文件路径打开powershell  
之后输入并改成你自己的HEVC的文件路径  
``` shell
Add-AppxPackage -Path "D:\Path\Filename.AppxBundle"
```
就能安装下来了
![AppxManifest.xml](https://github.com/Schwarz233/win10ltsc2019-bilibili-ubw/blob/main/picture/dd28344eb779fed306157d70362d72e0.png)
---
至此就结束了，希望能帮到同样用surface pro4和ltsc2019的用户  
这也是我第一次上传github，有做得不好的地方希望大佬们多多包涵
