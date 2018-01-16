# 链书

## 简介

[链书](https://github.com/b3log/chainbook)（Chainbook）是 B3 社区的去中心化书籍共享服务，通过数字货币 [B3T](TBD) 实现共享激励与价值链。

## 使用流程

* x：存书奖励 x 个 B3T，x 为定值 `100`
* y：分享书奖励 y 个 B3T，y 为定值 `20`

1. 用户 A 存入 a 书：获取 x 个冻结的 B3T
2. 用户 B 向 A 需求 a 书：
3. A 快递 a 书给 B（A 支付快递费，填写快递单号）
4. B 签收后 A 解冻 x 个 B3T，并获得系统奖励的 y 个 B3T
5. B 冻结 x 个 B3T
6. B 看完书后写好书评把 a 书进行分享
7. 用户 C 向 B 索取 a 书，以此类推 1-7

## 技术设计



## 关于 B3T

B3T（B3log Token）是 B3 社区在以太坊上发行的 ERC20 令牌，可用于支付 B3 社区上提供的各类应用和服务，为 B3 社区在更大范围的使用实现基础价值的统一。

B3T 的发行总量是 20 亿个，具体的分配比例如下：

* 3% 早期用户：按[黑客派](https://hacpai.com)注册时间、邀请数、积分余额等数据进行计算并直接赠送
* 7% 团队持有：主要用于社区服务的开发和调试
* 10% 社区激励：用于奖励为社区发展创造价值的用户，例如分享书籍
* 80% 认购：目前暂不对外公开认购

## 发展历程

* 2016 年萌生原始创意[疯狂的想法 C：书籍共享计划](https://hacpai.com/article/1483240295087)
* 2017 年通过微信小程序实现[客户端](https://github.com/b3log/symphony-weapp)并上线[书单计划](https://hacpai.com/tag/book_share)
* 2018 年通过以太坊区块链解决信任问题，实现书籍共享激励与价值链

## 开源协议

链书使用 GPLv3 作为开源授权协议，请尽量遵循，即使是在中国。

## 鸣谢

链书的诞生离不开以下项目：

* [Ethereum Project](https://www.ethereum.org)：运行智能合约的去中心化平台
* [OpenZeppelin](https://github.com/OpenZeppelin/zeppelin-solidity)：安全的智能合约基础库