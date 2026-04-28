## 新机配置

对于新的Windows系统，以下几个设置需要进行调整：
1. 防火墙关闭
2. 杀毒软件配置
3. 电源选项配置

## 杀毒软件配置
首先需要了解自己安装的系统版本，通过按下`Windows+R`组合键调出运行窗口，输入`winver`；即可查看具体版本；
家庭版和专业版的操作是不一样的；
![image-20210401204011466](https://cdn.jsdelivr.net/gh/FAQUS/CDN//img/image-20210401204011466.png)

#### 专业版
如果是专业版，
1. 运行**Windows+R**，输入`gpedit.msc`回车，
2. 打开策略组，在策略组定位到在策略组定位到"**计算机配置** >**管理模板** >**Windows组件** >**Windows Defender防病毒程序**"，如下图；
3. 启用 **关闭Windows Defender 防病毒程序**
![](https://cdn.jsdelivr.net/gh/FAQUS/CDN//img/image-20210401204249737.png)


#### 家庭版
1. `Windows+R`打开运行，输入`“regedit”`回车，打开注册表;
2. 在注册表定位到**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender**
3. 在右侧将DisableAntiSpyware项的数值改为1

关于没有该值修改，可以通过以下两种方式：
方法一：复制：`reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v "DisableAntiSpyware" /d 1 /t REG_DWORD /f`命令，在管理员命令提示符窗口中右键点击空白处；
方法二：在注册表编辑器中新建DisableAntiSpyware的DWORD（32位）值 ，可以彻底禁用Windows10系统的Windows Defender。
1. 进入注册表编辑器，复制：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender当HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender注册表路径粘贴到地址栏中后，按下键盘上的回车键，即定位到Windows Defender键，
2. 在Windows Defender右侧窗口中，右键点击空白处 - 新建 - DWORD（32位）值
![Snipaste_2021-04-08_10-40-22](https://cdn.jsdelivr.net/gh/FAQUS/CDN//img/Snipaste_2021-04-08_10-40-22.png)


## 电源配置
电源配置主要设置睡眠、屏幕熄灭和硬盘；
- 关闭盖子不操作，不进入睡眠
- 关闭显示器，都设置永不
![image-20210401204714742](https://cdn.jsdelivr.net/gh/FAQUS/CDN//img/image-20210401204714742.png)

还有一个保护硬盘操作，设置为0就行；
![image-20210401204912998](https://cdn.jsdelivr.net/gh/FAQUS/CDN//img/image-20210401204912998.png)


## 快捷键冲突
> Ctrl+Shift+F

微软拼音>按键>热键