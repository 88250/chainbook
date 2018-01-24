# 链书

## 简介

[链书](https://github.com/b3log/chainbook)（Chainbook）是 B3 社区提供的去中心化纸质书共享服务，通过社区发行的以太坊令牌 [B3T](https://etherscan.io/address/0xe249e7a6f5a9efee03b4c5090c77245ef6fe0f5e) 实现共享激励与价值链。

链书主要通过如下组件实现服务：

* [社区小程序](https://github.com/b3log/symphony-weapp)：扫 ISBN 进行存书，扫快递单号进行书籍共享
* [黑客派](https://hacpai.com)：B3 社区的线上论坛，实现书籍、B3T 管理
* [B3T 合约](https://etherscan.io/token/0xe249e7a6f5a9efee03b4c5090c77245ef6fe0f5e)：B3 社区令牌合约，实现 B3T 发行、转账等以太坊 ERC20 令牌的功能

## 使用流程

### 注册黑客派

[黑客派](https://hacpai.com)是 B3 社区的线上论坛，要使用链书服务必须先注册黑客派。

### 链书服务

存书与分享奖励：

* x：存书奖励 x 个 B3T，x 为定值 `100`
* y：分享书奖励 y 个 B3T，y 为定值 `20`

存书与分享：

1. 用户 A 使用小程序扫书 ISBN 存入书 a，获取 x 个冻结的 B3T
2. 用户 B 向 A 需求 a 书
3. A 快递 a 书给 B：A 支付快递费并使用小程序扫描快递单号
4. B 签收后系统将冻结 B 的 x 个 B3T 解冻 A 的 x 个 B3T 并获得奖励 y 个 B3T

### 站内交易

* 目前大多数情况下 B3T 会在 B3 社区**站内**围绕具体服务场景（例如链书）进行交易流转
* 可以对 B3T 进行充值或提现
* 后续可能会引入[雷电网络](https://raiden.network)来支持实时交易

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

详情浏览：**[B3log 社区币 B3T 发布](https://hacpai.com/article/1516547810228)**

目前 B3T 已经进入募集阶段：

1. 第一阶段：2018 年 1 月 25 日至 2018 年 2 月 25 日；1 ETH = 100000 B3T；2000 硬顶，占 10% B3T
2. 第二阶段：2018 年 3 月 1 日至 2018 年 6 月 15 日；1 ETH = 50000 B3T；8000 硬顶，占 20% B3T
3. 第三阶段：2018 年 7 月 1 日至 2019 年 1 月 15 日，1 ETH = 10000 B3T；占 50% B3T

B3 社区募集到的 ETH 用途分配如下：

* 35% 市场营销、地推及培训
* 20% 产品设计和技术开发
* 20% 法务，例如各地政策咨询、专利申请
* 15% 基础设施开支，例如购书
* 10% 社区流动资金

**目前暂不对外公开募集，详情请加 [B3 电报群](https://t.me/b3logcoin) 联系管理员。**

请注意，充值 B3T 不是投资，并且不能将其视为投资。B3T 由社区用户拥有，早期的支持者将是 B3log 未来远见的卓识者。

## 联系方式

* [社区论坛](https://hacpai.com/tag/B3T)
* [QQ 群 618817478](https://shang.qq.com/wpa/qunwpa?idkey=774db3af72d630c1ab91550763f55265e4b3e8c4b8d953dd51070561b114afef)
* [电报群](https://t.me/b3logcoin)

## 鸣谢

链书的诞生离不开以下项目：

* [Ethereum Project](https://www.ethereum.org)：运行智能合约的去中心化平台
* [OpenZeppelin](https://github.com/OpenZeppelin/zeppelin-solidity)：安全的智能合约基础库
* [INFURA](https://infura.io)：为以太坊、IPFS 提供安全、可靠和可伸缩的区块链基础设施

### 总结

链书旨在为旧书创造一个全新的共享平台，让旧书发挥其最大的社会价值。技术上基于区块链实现高效互信的数据共享和价值传递，并通过 B3T 实现社区基础价值的统一。

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
