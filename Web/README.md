Web Demo 是基于 IM TUIKit 实现，TUIKit 中包含会话、聊天、群组、个人资料管理等功能，基于 TUIKit 您可以像搭积木一样快速搭建起自己的业务逻辑。

## 效果展示

### 会话管理

| 发起会话 | 会话列表 | 会话列表管理 |
| --- | --- | --- |
| [![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/search.png)](https://camo.githubusercontent.com/abb48b90448d4ec1c6ec449ad47697821d5d7f6c246caf6ae284c0bcb09e6f29/68747470733a2f2f71636c6f7564696d672e74656e63656e742d636c6f75642e636e2f7261772f30313831653232316264393936663935396139643530313637366130373539612e706e67) | ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/conversationList.png) | [![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/conversationManage.png)](https://camo.githubusercontent.com/08a3ba2375ca499388552089a882e541a3330b8ad63a639ebcb4ff9282bdec56/68747470733a2f2f71636c6f7564696d672e74656e63656e742d636c6f75642e636e2f7261772f61663634353263313166613563653537343162636262316461323138333564652e706e67) |

### 聊天管理

| 消息列表 | 消息发送 | 群聊管理 |
| --- | --- | --- |
| ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/chat.png) | ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/chat-send.png) | ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/group-manage.png) |

### 群组管理

| 群聊通知 | 我的群聊 | 搜索加入新的群聊 |
| --- | --- | --- |
| ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/group-system.png) | ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/group-list.png) | ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/group-search.png) |

### 个人资料管理

| 个人资料管理 |
| --- |
| ![](https://web.sdk.qcloud.com/im/demo/TUIkit/document-image/profile.png) |

| 功能  | 说明  |
| --- | --- |
| 会话管理 | 1. 用于用户发起单人/多人会话<br/>2. 用于展示用户的会话列表<br/>3. 用于用户会话列表的管理 |
| 聊天管理 | 1. 用于消息列表的展示<br/>2. 用于消息发送<br/>3. 用于群聊管理 |
| 群组管理 | 1. 用于展示群聊通知<br/>2. 用于展示和管理用户所在和所拥有的群聊<br/>3. 用于搜索加入新的群聊 |
| 个人资料管理 | 主要用于展示和更新个人资料 |

## 跑通步骤

### 步骤1：下载源码

根据您的实际业务需求，下载 SDK 及配套的 [Demo 源码](https://cloud.tencent.com/document/product/269/36887)。

``` shell
# 命令行执行
git clone https://github.com/tencentyun/TIMSDK.git

# 进入 Web 项目

cd TIMSDK/Web/Demo

# 安装 demo 依赖
yarn install

cd TIMSDK/Web/Demo/src/TUIKit

# 安装 TUIKit 依赖
yarn install
```

### 步骤2：初始化

1. 打开终端目录的工程，找到对应的 `GenerateTestUserSig` 文件，路径为：/debug/GenerateTestUserSig.js
2. 设置`GenerateTestUserSig`文件中的相关参数，其中 SDKAppID 和密钥等信息，可通过 [即时通信 IM 控制台](https://console.cloud.tencent.com/im) 获取，单击目标应用卡片，进入应用的基础配置页面。 [![](https://qcloudimg.tencent-cloud.cn/raw/e435332cda8d9ec7fea21bd95f7a0cba.png)](https://camo.githubusercontent.com/20575292024f27b76db87d6688e57f16d38b579b249054466668b596975dd30e/68747470733a2f2f71636c6f7564696d672e74656e63656e742d636c6f75642e636e2f7261772f65343335333332636461386439656337666561323162643935663761306362612e706e67)
  
3. 在**基本信息**区域，单击**显示密钥**，复制并保存密钥信息至 `GenerateTestUserSig` 文件。 [![](https://main.qcloudimg.com/raw/e7f6270bcbc68c51595371bd48c40af7.png)](https://camo.githubusercontent.com/d3e2ecc55db7a3c14ba0ba84c7cb92e18618028006c6f7fa304ba5ef01f0b6be/68747470733a2f2f6d61696e2e71636c6f7564696d672e636f6d2f7261772f65376636323730626362633638633531353935333731626434386334306166372e706e67)
  

> !本文提到的获取 UserSig 的方案是在客户端代码中配置 SECRETKEY，该方法中 SECRETKEY 很容易被反编译逆向破解，一旦您的密钥泄露，攻击者就可以盗用您的腾讯云流量，因此**该方法仅适合本地跑通 Demo 和功能调试**。 正确的 UserSig 签发方式是将 UserSig 的计算代码集成到您的服务端，并提供面向 App 的接口，在需要 UserSig 时由您的 App 向业务服务器发起请求获取动态 UserSig。更多详情请参见 [服务端生成 UserSig](https://cloud.tencent.com/document/product/269/32688#GeneratingdynamicUserSig)。

### 步骤3: 启动

``` shell
# 启动项目
cd TIMSDK/Web/Demo
yarn serve
```

- [SDK API 手册](https://web.sdk.qcloud.com/im/doc/zh-cn/SDK.html)
- [SDK 更新日志](https://cloud.tencent.com/document/product/269/38492)
- [Demo 源码](https://github.com/tencentyun/TIMSDK/tree/master/Web/Demo)