# 准备软件
- Charles
- iTunes 12.6.3
# Charles安装证书
下载好Charles安装好之后，需要安装一个SSL证书。具体步骤如下
![1](https://github.com/user-attachments/assets/5295a917-eb28-401c-8422-6514b360df1d)
![2](https://github.com/user-attachments/assets/c3f39fbd-f6f5-443b-a7da-eb17b3ac04df)
# 抓包步骤
1. 关闭系统的代理，打开Charles。
2. 打开iTunes下载一个软件，我这里以有道词典为例
![Pasted image 20241222221132](https://github.com/user-attachments/assets/f1e76b3e-5346-46d6-8581-2af21477d776)
3. 右击这个域名，选择**Enable SSL Proxying**。然后我们切回到iTunes，重新下载该软件。
![Pasted image 20241222221152](https://github.com/user-attachments/assets/a9e207bc-f15f-4ef1-a50b-ef106e235da9)
4. 点击展开域名**WebObjects/MZBuy.woa/wa/buyProduct**，右侧信息栏中，点击**Context**>>**选择XML Text格式**
![Pasted image 20241222223143](https://github.com/user-attachments/assets/27a04a61-5bd6-4afa-9eb9-a4cfe2fa1185)
5. [通过appID获取所有版本](https://api.unlimapps.com/v1/apple_apps/[你获得的appID]/versions)  可以查看所有版本和日期。通过抓包也是可以获取到版本号信息。位于**<array></array>**中间就是版本号。
![Pasted image 20241222223230](https://github.com/user-attachments/assets/4dbdd5ea-4495-48b3-bd05-067797a76c20)
appID获取可以通过iTunes复制应用连接获取到appID
![Pasted image 20241222223253](https://github.com/user-attachments/assets/d22a82a1-10fc-4583-818b-da50b1948995)
![Pasted image 20241222223307](https://github.com/user-attachments/assets/ba55f3bb-3336-40c3-90cc-5f50f908f352)
下载的ipa文件可以通过资料库查看，确实是老版本iTunes。
![Pasted image 20241222223351](https://github.com/user-attachments/assets/ba07b850-a085-4ddf-b3df-43b09f6c1be5)
# 流程梳理
1. Charles安装SSL证书
2. iTunes第一次下载app，注意域名“p(xx)-buy.itunes.apple.com”，开启”Enable SSL Proxying“
3. iTunes第二次下载app,查看版本号信息，打断点”breakpoint“
4. iTunes第三次下载app，修改”appExtVrsId“值，即版本号
5. iTunes资料库获取 ipa文件
# ipa如何安装
- 利用iTunes 安装到iPhone
- 通过第三方软件安装
- 利用一些脚本软件或者捷径等安装ipa
# 抓包旧版App好处
- 旧版本可能存在一些好用的功能，比如追书神器这类app
- 旧版本可能存在买断版本，lifetime等等
- 或者新版本用的不舒服，想换回老版本
