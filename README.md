# <img src="https://b3log.org/images/brand/chainbook-32.png"> [链书](https://github.com/b3log/chainbook)

* [简介](#简介)
* [动机](#动机)
* [使用流程](#使用流程)
  * [微信登录](#微信登录)
  * [交易书籍](#交易书籍)
  * [细节规则](#细节规则)
* [技术实现](#技术实现)
  * [架构设计](#架构设计)
  * [ERC20 令牌](#erc20-令牌)
  * [路线图](#路线图)
* [关于 B3T](#关于-b3t)
* [总结](#总结)
* [鸣谢](#鸣谢)
* [附录](#附录)
  * [B3log 开源社区](#b3log-开源社区)
  * [B3log 开源社区简史](#b3log-开源社区简史)

## 简介

[链书](https://github.com/b3log/chainbook)（Chainbook）是 B3log 开源社区提供的区块链纸质书交易平台，通过 [B3T](https://hacpai.com/article/1516547810228) 实现共享激励与价值链。

链书主要通过如下组件实现服务：

* 链书社：微信小程序，扫 ISBN 进行书籍上架、购买书籍、快递预约等业务操作
* [黑客派](https://hacpai.com)：链书社服务端，实现账号系统、书籍管理、B3T 转账、社区论坛等
* [B3T](https://hacpai.com/article/1516547810228)：B3log 开源社区币，以太坊 ERC20 令牌

![链书社](https://img.hacpai.com/file/2018/06/a49850df84a8461ea75be8245ea1e11b_image.png)

## 动机

* 让闲置书籍继续发挥社会价值
* 做一个真实落地的区块链应用
* 为 B3T 赋值，扩大 B3log 开源社区影响力

## 使用流程

### 微信登录

* 如果没有[黑客派](https://hacpai.com)账号，直接通过链书社小程序登录即可
* 如果已有黑客派账号，需要先到个人设置账号中绑定微信，然后再通过链书社小程序登录

### 交易书籍

1. 卖家使用小程序扫书 ISBN 并设定 x 个 B3T 上架，标明寄付或到付
2. 买家需求下单：冻结买家的 x 个 B3T
3. 卖家快递书给买家：通过系统联系快递上门取件进行寄送
4. 买家签收后系统将 x 个冻结 B3T 解冻并转账给卖家

在这个交易过程中：

* 卖家主要成本是发快递的人力时间成本，寄付的话还需要支付快递费，收益是获得 x 个自定价的 B3T
* 买家主要成本是支付 x 个 B3T，到付的话还需要支付快递费，收益是获得书

### 细节规则

卖家：

* 相同的书籍只能有一本处于在架状态
* B3T 定价区间 \[1, 10240\]

买家：

* B3T 可用余额满足书籍定价
* 最多只能同时需求下单 3 本书

系统：

* 撤销超过 3 天没有快递发货的订单，书籍回到在架状态，解冻买家 B3T
* 撤销超过 15 天仍处于快递中的订单，书籍回到在架状态，解冻买家 B3T

## 技术实现

### 架构设计

![Arch](https://img.hacpai.com/file/2018/06/f570d30abd16450686c354bf1a26605b_chainbook_arch.png)

### ERC20 令牌

* B3T 是完整实现 ERC20 标准的以太坊令牌，基础部分使用 [OpenZepplin](https://openzeppelin.org) 开源的合约库
* 遵循 [ConsenSys](https://consensys.net) 发布的[智能合约最佳实践](https://github.com/ConsenSys/smart-contract-best-practices)进行开发

### 路线图

* [x] M1 社区站内交易
* [ ] M2 以太坊链上交易
* [ ] M3 B3log Coin 主网  

## 关于 B3T

* [B3log 开源社区币 B3T 发布](https://hacpai.com/article/1516547810228)
* [关于 B3T 提币开放的公告](https://hacpai.com/article/1520475188028)

## 总结

链书旨在为闲置书籍创造一个全新的交易平台，让有价值的闲置书籍发挥其最大的社会价值。链书基于区块链技术，实现了高效互信的书籍共享和价值传递，最终通过 B3T 实现 B3log 开源社区基础价值的完整统一。

## 鸣谢

链书的诞生离不开以下项目：

* [Ethereum Project](https://www.ethereum.org)：运行智能合约的去中心化平台
* [OpenZeppelin](https://github.com/OpenZeppelin/zeppelin-solidity)：安全的智能合约基础库
* [INFURA](https://infura.io)：为以太坊、IPFS 提供安全、可靠和可伸缩的区块链基础设施
* [WePY](https://github.com/Tencent/wepy)：小程序组件化开发框架

----

## 附录

### B3log 开源社区

* 首页：https://b3log.org
* 黑客派：https://hacpai.com
* GitHub：https://github.com/b3log
* Twitter：https://twitter.com/b3logos
* Telegram ：https://t.me/b3log
* 微信公众号：b3logos
* 微博：https://weibo.com/2778228501

### B3log 开源社区简史

* 2009 年萌生 [B3log 构思](http://88250.b3log.org/articles/2009/12/09/1260370800000.html) 
* 2010 年发布开源博客系统 [Solo](https://github.com/b3log/solo)
* 2012 年上线 B3log 开源社区线上论坛[黑客派](https://hacpai.com)，并将其[开源](https://github.com/b3log/symphony)
* 2014 年上线 Go 语言在线开发环境 [Wide](https://wide.b3log.org)，并将其[开源](https://github.com/b3log/wide)
* 2015 年完成黑客派众筹，B3log 开源社区开始尝试商业化发展
* 2016 年萌生[书籍共享计划](https://hacpai.com/article/1483240295087)，通过微信小程序实现并开源[客户端](https://github.com/b3log/symphony-weapp)，上线[书单](https://hacpai.com/tag/book_share)
* 2017 年上线博客平台 [Pipe](http://pipe.b3log.org)，并将其[开源](https://github.com/b3log/pipe)
* 2018 年在以太坊平台上发行 [B3T](https://etherscan.io/token/0xe249e7a6f5a9efee03b4c5090c77245ef6fe0f5e)，实现 B3log 开源社区基础价值的统一，上线链书

----

<p align = "center">
<strong>区块链上的纸质书交易平台，为未来而构建</strong>
<br><br>
<img src="https://b3log.org/images/brand/chainbook-128.png">
</p>
