# 链书

## 简介

[链书](https://github.com/b3log/chainbook)（Chainbook）是 B3 社区的去中心化书籍共享服务，通过数字货币 [B3T](TBD) 实现共享激励与价值链。

## 使用流程

### 注册黑客派

[黑客派](https://hacpai.com)是 B3 社区的线上论坛，要使用链书服务必须先注册黑客派。

### 链书服务

* x：存书奖励 x 个 B3T，x 为定值 `100`
* y：分享书奖励 y 个 B3T，y 为定值 `20`
* 用户 A 使用小程序扫书 ISBN 存入书 a，获取 x 个冻结的 B3T
* 用户 B 向 A 需求 a 书：
  1. B 提供真实地址和电话给 A
  2. A 快递 a 书给 B（A 支付快递费，使用小程序扫描录入快递单号）
  3. 系统冻结 B 的 x 个 B3T 同时解冻 A 的 x 个 B3T，并获得奖励 y 个 B3T
  4. B 看完书后把 a 书进行分享
  5. 用户 C 向 B 索取 a 书，以此类推 1-5

### 站内交易

* 目前大多数情况下 B3T 会在 B3 社区**站内**围绕具体服务场景（例如链书）进行交易流转
* 可以对 B3T 进行充值或提现
* 后续可能会引入[雷电网络](https://raiden.network)来支持实时交易

## 技术实现

### 技术架构



### 智能合约

* B3T 是完整实现 ERC20 标准的以太坊令牌，基础部分使用 [OpenZepplin](https://openzeppelin.org) 开源的合约库
* 遵循 [ConsenSys](https://consensys.net) 发布的[智能合约最佳实践](https://github.com/ConsenSys/smart-contract-best-practices)进行开发

### 平台扩展性

* 具备后续对接 QTUM、NEO 等其他平台的能力
* 多平台发布令牌后的互操作性
* 去中心化的 B3log Coin 主网  

## 关于 B3T

B3T（B3log Token）是 B3 社区在以太坊上发行的 ERC20 令牌，可用于：

* 支付 B3 社区内提供的各类应用和服务，例如个人自媒体内容发布服务
* 支付 B3 社区内其他用户提供的实物商品，例如书籍、二手物品
* 打赏 B3 社区内其他用户创造的网络内容，例如帖子打赏

B3T 为 B3 社区在更大范围内的影响实现了基础价值的统一。

B3T 的其发行总量是 20 亿个，具体的分配比例如下：

* 3% 早期用户：按[黑客派](https://hacpai.com)注册时间、邀请数、积分余额、活跃度等历史数据进行计算并赠送排名前 5000 的用户
* 7% 团队持有：主要用于社区服务的开发和调试
* 10% 社区激励：用于奖励为社区发展创造价值的用户
* 80% 认购：目前暂不对外公开认购

## 提币流程

1. 输入钱包地址、提现金额及 gas
2. 人工审核（提现申请表）成功后，把 B3T 从社区银行账户转入用户输入的地址上
3. 更新社区该用户 B3T 站内可用余额

## 冲币流程

1. 通过 DApp 把 ETH 兑换为对应平台的 B3T
   1. 打 ETH 到指定合约地址
   2. 该合约将 B3T 存入社区银行账户
2. 更新社区该用户 B3T 站内可用余额

1 ETH = 10000 B3T

* 35% 市场营销、地推及培训 
* 20% 产品设计和技术开发
* 20% 法务，例如各地政策咨询、专利申请） 
* 15% 社区服务基础，例如购书
* 10% 社区基金 

**目前暂不对外公开认购**。

## 开源协议

链书使用 GPLv3 作为开源授权协议，请尽量遵循，即使是在中国。

## 鸣谢

链书的诞生离不开以下项目：

* [Ethereum Project](https://www.ethereum.org)：运行智能合约的去中心化平台
* [OpenZeppelin](https://github.com/OpenZeppelin/zeppelin-solidity)：安全的智能合约基础库
* [INFURA](https://infura.io)：为以太坊、IPFS 提供安全、可靠和可伸缩的区块链基础设施

----

## 附录

### B3 社区简史

* 2009 年萌生 [B3log 社区构思](http://88250.b3log.org/articles/2009/12/09/1260370800000.html) 
* 2010 年发布开源的个人独立博客产品 [Solo](https://github.com/b3log/solo)
* 2012 年上线 B3 社区线上论坛[黑客派](https://hacpai.com)，并以 [Sym](https://github.com/b3log/symphony) 作为产品名开源
* 2014 年上线 Go 语言在线开发环境 [Wide](https://wide.b3log.org)，并将其[开源](https://github.com/b3log/wide)
* 2015 年完成黑客派众筹，B3 社区开始尝试商业化发展
* 2016 年萌生原始创意[疯狂的想法 C：书籍共享计划](https://hacpai.com/article/1483240295087)
* 2017 年通过微信小程序实现[客户端](https://github.com/b3log/symphony-weapp)并上线[书单计划](https://hacpai.com/tag/book_share)
* 2018 年通过区块链解决信任问题，实现书籍共享激励与价值传递
