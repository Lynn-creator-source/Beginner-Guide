# 新人指南
### 文档说明
* 文档目的：帮助新人进行办公/开发所需要的软件安装与配置，了解软件的基本操作及技术文档的写作语法，确保入职后正常开展工作
* 适用人群：CamThink 项目组全员
* 版本说明：V1.0
## 一、安装前准备
### 1.1 设备检查
* 确认办公设备型号（台式机 / 笔记本）及系统版本（Windows 10/11）
* 检查设备存储空间：建议预留至少50GB空余空间
* 网络环境要求：需连接公司VPN网络（附：VPN权限申请及连接指南）
### 1.2 软件下载路径
* **需从官方网站下载（附：官方网站链接汇总）**
* **注意事项：严禁安装任何非官方渠道的软件（防病毒风险提示）**
## 二、项目软件安装
### 2.1 node.js
1. 打开官网 [Node.js](https://nodejs.org/zh-cn/ "访问官网")
2. 点击下载按钮 ![跳转页面](node/node-Homepage-Download-Guide.png)
3. 点击Windows 安装程序 ![跳转页面](node/node-Windows-Installer.png)
4. 点击下载箭头（红圈内），打开下载的node 安装包 ![跳转页面](node/Package.png)
5. 跟随安装指引，点击next 
### 2.2 Visual Studio Code
1. 打开官网 [Visual Studio Code](https://code.visualstudio.com/ "访问官网")
2. 点击下载按钮 ![跳转页面](vscode/Vscode-homepage-Download-Guide.png)
3. 点击Windows按钮 ![跳转页面](vscode/Vscode-Windows-Installer.png)
4. 点击下载箭头（红圈内），打开下载的Visual Studio Code 安装包 ![跳转页面](vscode/Vscode-Installation-Package.png)
### 2.3 全局安装yarn
1. 通过npm安装yarn,确保电脑已经安装了Node.js
2. win+R 打开命令行窗口
3. 执行以下命令安装 Yarn：
```npm install -g yarn```
4. 安装完成后，可以输入以下命令验证是否安装成功：
```yarn --version```
若显示版本号，说明安装成功
### 2.4 安装yarn install 依赖包
1. 通过npm安装yarn,确保电脑已经安装了Node.js
2. win+R 打开命令行窗口
3. 使用cd命令导航到你的项目根目录（即包含 package.json 文件的文件夹）
例如：
```cd C:\Users\你的用户名\项目文件夹名称\```
4. 在项目目录下输入以下命令：
```yarn install```
5. 在文件管理器中查看项目根目录是否存在 node_modules，输入
```dir node_modules ```
若出现文件夹名称（如各种依赖包名称），说明依赖包安装成功
## 三、账户注册
### 3.1 GitHub账户
1. 打开官网 [GitHub](https://github.com/ "访问官网")
2. 创建账户![跳转页面](GitHub/GitHub-account.png)
3. 填写账户信息，包括邮箱（用于账号验证，使用公司分配邮箱地址），密码，用户名，填写完成后点击create account 按钮 ![跳转页面](GitHub/GitHub-Account-Information.png)
4. 填写邮件收到的GitHub验证码 ![跳转页面](GitHub/Verification-Code-Page.png)
5. 填写用户名和密码，登录 ![跳转页面](GitHub/sign-in.png)
## 四、GitHub基础操作
#### 在本地创建仓库
##### 在GitHub上拥有一个仓库（两种途径）
* 创建github仓库
1. 登录账号，点击右上角＋号，创建new repository ![跳转页面](GitHub/new-repository.png)
2. 根据箭头指示，依次填写仓库名、描述、根据需求选择是否公开，默认公开，add README 选择on，最后点击创建仓库 ![跳转页面](GitHub/new-repository-description.png)
* fork github仓库
1. 登录账户，在顶部搜索框输入"camthink-ai/wiki-documents（要复制的仓库路径）" ![跳转页面](GitHub/new-repository-description.png)
2. 点击仓库右上角的fork按钮，将仓库复制到自己账号 ![跳转页面](GitHub/new-repository-description.png) 
##### 将已有的GitHub仓库克隆到本地
1. 在GitHub进入你要克隆的仓库，点击右上角code按钮 ![跳转页面](GitHub/code.png)
2. 点击复制按钮，复制仓库的url ![跳转页面](GitHub/url.png )
3. win+R ，输入cmd 打开命令行窗口 ```cd 你想要存放仓库的本地文件夹地址```
4. 在项目目录下输入以下命令：
```git clone 你复制的仓库的url地址```
5. 在存放仓库的文件夹查找，是否新增你克隆仓库名的文件夹，若有，clone 成功
6. 如果你之前复制过该仓库，在github网页更新了内容，想要把远程更新同步到本地，执行以下操作:
* ```cd 你的仓库本地地址```
* ```git pull origin main #执行 git pull 命令，将 GitHub 上的最新 Wiki 内容同步到本地```
* 如果你的默认分支是master ，则执行```git pull origin master```
##### 本地修改仓库
1. 创建新分支专门用于本次修改！
*  ```cd 克隆的仓库本地地址```
* ```git checkout -b 新分支名（如new-feather）```
2. 本地修改代码后，完成并保存
3. 本地运行项目:
```yarn start```
4. 中英文转换：
先运行```yarn build ```，再运行```npm run serve```
##### 将本地修改内容上传至GitHub
```git add . #上传所有修改的文件```
```git commit -m "描述你的修改，比如，修改产品说明" #提交说明```
```git push origin 新分支名 #推送到自己fork 的仓库的新分支```
##### 在GitHub上创建PR（Pull Request，拉取请求）
###### 作用
* 向仓库提交修改：如果你对某个仓库（比如开源项目或团队仓库）做了修改，通过 PR 可以把你的代码 “推” 给仓库维护者
* 代码审核：仓库维护者可以在 PR 中查看你的修改内容、提出意见、讨论问题，确保代码质量
* 协作记录：PR 会完整记录修改过程和讨论，方便后续追溯
###### 操作过程
1. 打开自己fork的仓库页面 
2. 页面会提示"刚刚推送了新分支"，点击旁边的Compare & pull request 按钮
3. 在 PR 页面填写信息：标题：简要说明 PR 的目的（如 “修复登录验证码错误”），描述：详细说明你做了什么修改、为什么这样改，方便审核者理解
4. 确认 PR 的目标分支（通常是原仓库的 main 或 master 分支），点击 Create pull request 完成创建
##### 后续：处理审核意见
1. 仓库维护者会查看你的 PR，可能会提出修改意见（在 PR 页面评论）
2. 你可以在本地修改后，再次通过 git add → git commit → git push 推送到同一个分支，PR 会自动更新
3. 审核通过后，维护者会点击 Merge pull request 将你的代码合并到原仓库，你的贡献就成功啦！