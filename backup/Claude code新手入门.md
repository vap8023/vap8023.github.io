## 安装
Claude Code是一个智能编码工具，可以在终端运行，通过自然语言交互，完成代码编写、调试等工作。

### 环境依赖
安装node.js，版本大于18.x版本即可；推荐使用nvm安装，切换版本方便。
安装git 默认安装即可；
```shell 
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```
安装claude code
```shell
npm install -g @anthropic-ai/claude-code
```

<img width="1140" height="317" alt="Image" src="https://github.com/user-attachments/assets/93cbeb72-c509-4080-a4ca-69f3faabda6f" />
## 申请大模型API Key 
智谱地址：https://www.bigmodel.cn/glm-coding?ic=MRPLCUAPZA
登录后，点击右上角个人图标，点击API Key,创建一个新的API Key

<img width="2172" height="762" alt="Image" src="https://github.com/user-attachments/assets/1c717544-ac58-46c2-84a9-6d51e276a0bf" />

## 安装CC Switch
CC Switch是一个开源桌面工具，管理大模型API配置与切换。
地址：https://github.com/farion1231/cc-switch/releases
配置API Key 

<img width="1799" height="1200" alt="Image" src="https://github.com/user-attachments/assets/b27129b5-f90a-4c60-8731-45800da9b38c" />

## Claude Code配置
用户目录下 **.claude.json** 文件配置（如果没有则新建）
新增配置 **hasCompletedOnboarding** 参数 = true;
然后重新打开命令行窗口；输入 claude 出现下载截图就配置完成。

<img width="2346" height="1221" alt="Image" src="https://github.com/user-attachments/assets/034160f5-2802-46d2-a6e6-d57bbf06d640" />


这样claude code就配置好了；
## Claude code 命令
- @ 引用文件或文件夹
- ！执行shell 命令

## Skills
anthropics/skills 是官方开源的Skills；
```shell
# 添加Anthropic插件市场
/plugin marketplace add anthropics/skills
# 添加Skills
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```
document-skills 处理文档技能包；
example-skills 示例机能包，可以处理MCP构建 网页测试 等；

obra/superpowers 是一个专为编程智能体
```shell
# 添加Superpower 插件市场
/plugin marketplace add obra/superpowers-marketplace 
# 添加skills
/plugin install superpowers@superpowers-marketplace 
```

## 配置MCP
```shell
claude mcp add chrome-devtools -- npx chrome-devtools-mcp@latest
```
配置完成后，重新进入claude 

<img width="1397" height="756" alt="Image" src="https://github.com/user-attachments/assets/fd663fe5-d347-4bdb-b7e7-e7408a02dfd1" />

