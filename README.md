# 链书

## 简介

[链书](https://github.com/b3log/chainbook)（Chainbook）是 B3 社区提供的去中心化纸质书共享应用，通过社区发行的以太坊令牌 [B3T](https://hacpai.com/article/1516547810228) 实现共享激励与价值链。

链书主要通过如下组件实现服务：

* B3log开源链书：微信小程序，扫 ISBN 进行书籍共享，通过 B3T 对书籍定价和交易
* [黑客派](https://hacpai.com)：B3 社区的线上论坛，实现账号系统、书籍管理、B3T 转账等
* [B3T 合约](https://etherscan.io/token/0xe249e7a6f5a9efee03b4c5090c77245ef6fe0f5e)：B3 社区令牌合约，实现 B3T 发行、转账等以太坊 ERC20 令牌的功能

## 使用流程

### 注册黑客派

[黑客派](https://hacpai.com)是 B3 社区的线上论坛，要使用链书必须先注册黑客派，小程序实现了通过微信登录授权注册账号。

### 到付模式

1. 用户 A 使用小程序扫书 ISBN 并设定 x 个 B3T 分享
2. 用户 B 向 A 需求书：冻结 B 的 x 个 B3T
3. A 使用到付快递书给 B
4. B 签收后系统将 B 的 x 个冻结 B3T 解冻并转账给 A

在这个交易过程中：

* A 主要成本是发快递的人力时间成本，收益是获得 x 个自定价的 B3T
* B 主要成本是支付快递费并支付给 x 个 B3T给 A，收益是获得书

### 寄付模式

TBD

* x：存书奖励 x 个 B3T，x 为定值 `100`
* y：分享书奖励 y 个 B3T，y 为定值 `20`

1. 用户 A 使用小程序扫书 ISBN 存入书，获取 x 个冻结的 B3T
2. 用户 B 向 A 需求书
3. A 快递书给 B：A 支付快递费并使用小程序扫描快递单号
4. B 签收后系统将冻结 B 的 x 个 B3T，解冻 A 的 x 个 B3T 并获得奖励 y 个 B3T

### 站内交易

* 大多数情况下 B3T 会在 B3 社区**站内**围绕具体应用场景（例如链书）进行交易流转
* 可以对 B3T 进行充值或提现

## 技术实现

### 架构设计

![Arch](https://user-images.githubusercontent.com/873584/35210948-37f3f3d6-ff8f-11e7-916c-fc754841c870.png)

### 智能合约

* B3T 是完整实现 ERC20 标准的以太坊令牌，基础部分使用 [OpenZepplin](https://openzeppelin.org) 开源的合约库
* 遵循 [ConsenSys](https://consensys.net) 发布的[智能合约最佳实践](https://github.com/ConsenSys/smart-contract-best-practices)进行开发

### 平台扩展性

* 具备后续对接 QTUM、NEO 等其他平台的能力
* 多平台发布令牌后的互操作性
* 去中心化的 B3log Coin 主网  

## 关于 B3T

* [B3log 社区币 B3T 发布](https://hacpai.com/article/1516547810228)
* [关于 B3T 提币开放的公告](https://hacpai.com/article/1520475188028)

## 联系方式

* [社区论坛](https://hacpai.com/tag/B3T)
* [QQ 群 618817478](https://shang.qq.com/wpa/qunwpa?idkey=774db3af72d630c1ab91550763f55265e4b3e8c4b8d953dd51070561b114afef)
* [电报群](https://t.me/b3log)

## 总结

链书旨在为闲置书籍创造一个全新的共享平台，让有价值的闲置书籍发挥其最大的社会价值。链书基于区块链技术，实现了高效互信的数据共享和价值传递，最终通过 B3T 实现社区基础价值的完整统一。

## 鸣谢

链书的诞生离不开以下项目：

* [Ethereum Project](https://www.ethereum.org)：运行智能合约的去中心化平台
* [OpenZeppelin](https://github.com/OpenZeppelin/zeppelin-solidity)：安全的智能合约基础库
* [INFURA](https://infura.io)：为以太坊、IPFS 提供安全、可靠和可伸缩的区块链基础设施
* [WePY](https://github.com/Tencent/wepy)：小程序组件化开发框架

----

## 附录

### B3 社区简史

* 2009 年萌生 [B3log 社区构思](http://88250.b3log.org/articles/2009/12/09/1260370800000.html) 
* 2010 年发布开源的个人独立博客产品 [Solo](https://github.com/b3log/solo)
* 2012 年上线 B3 社区线上论坛[黑客派](https://hacpai.com)，并将其[开源](https://github.com/b3log/symphony)
* 2014 年上线 Go 语言在线开发环境 [Wide](https://wide.b3log.org)，并将其[开源](https://github.com/b3log/wide)
* 2015 年完成黑客派众筹，B3 社区开始尝试商业化发展
* 2016 年萌生[书籍共享计划](https://hacpai.com/article/1483240295087)，通过微信小程序实现并开源[客户端](https://github.com/b3log/symphony-weapp)，上线[书单](https://hacpai.com/tag/book_share)
* 2017 年上线博客平台 [Pipe](http://pipe.b3log.org)，并将其[开源](https://github.com/b3log/pipe)
* 2018 年在以太坊平台上发行 [B3T](https://etherscan.io/token/0xe249e7a6f5a9efee03b4c5090c77245ef6fe0f5e)，实现 B3 社区基础价值的统一，上线链书
