# OYchain

## 社区链简介
OYchain是基于以太坊源代码开发的，高性能和去中心化的公链，**目的是为解决目前公链出现的诸如性能底下，成本过高等问题，从而提供给社区用户更加高速便捷并且低成本的区块链使用体验**。

OYchain具有如下特性：
- 完全兼容以太坊和ERC20智能合约，迁移成本极低
- 以OY作为链的gas费，交易成本极低
- 每3秒出一个块，交易确认更快，链性能更高
- Proof of Staked Authority(PoSA)共识算法，效率高，安全稳定

## 使命

促进价值在全球自由流动。

## 风险提示

- OYchain官方不会发布任何Swap项目，因为所有项目都是由社区开发的，所以OYchain对这些项目造成的问题不承担任何责任。此外，OYchain不为相关项目提供客户服务；
- 在任何加密货币,Defi相关领域有任何操作前，请首先DYOR(Do your own research)；
- 所有用户及开发者都可以免费参与OYchain的测试环境与后续阶段，不存在收费场景；
- 大家务必区分好测试环境和主网环境，测试环境所产生的资产不具备任何价值，谨防假币诈骗；
- OYchain将通过官方社交平台公布授权、推介等合作，开发者和用户谨慎核对，以免造成损失；
- 请认准官方网址，避免出现私钥被钓鱼等情况。

## 免责声明
尊敬的用户（以下称“您”）：

OYchain（以下简称“OYchain”或“我们”）是一个去中心化公链，全球开发者都可以在OYchain上部署应用，所有用户可以在OYchain上可以读取、发送和交易。由于去中心化的特性，我们特向您提醒第三方DAPP风险如下：
- 您在任何平台、钱包、第三方Dapp有任何操作前，请首先DYOR(Do your own research)；
- 无论您通过任何交易平台、钱包参与或使用OYchain上的DAPP，均为您个人的自由选择行为，我们并不向您推荐使用；
- 我们不对任何第三方DAPP负有审核责任，也不对其服务所涉及的技术及信息的有效性、准确性、正确性、可靠性、质量、稳定、完整和及时性作出任何承诺和保证；
- 您自行承担使用第三方DAPP服务产生的全部责任；
- 第三方DAPP服务等是否符合您所在管辖区的法律法规或相关政策要求，请您自行判断与评估，我们不提供任何评估意见，但请您务必严格遵守您所在管辖地的法律；
- 您因使用第三方DAPP而涉及的包括但不限于合法问题、合同责任问题、经济损失问题等，均由您与第三方DAPP自行解决，我们不对此承担责任；
- OYchain不会与任何第三方DAPP共享您的个人信息，除非获得您的明确同意。在获得您明确同意后而因第三方DAPP 获取您个人信息产生的一切法律责任、纠纷，仍由您自行承担并与第三方DAPP自行解决。
- OYchain无权向您提供任何第三方DAPP开发者的个人信息，除非获得对方的同意或相关部门的要求，我们会尽力协助但无法保证能有效及时获取对方信息。
  最后，我们再次提醒您：我们不推荐、建议、引导您使用任何第三方DAPP服务。

# 网络参数
社区用户可以使用任何以太坊的钱包，并配置OYchain链的网络参数，如 [metamask](https://metamask.io/), [myetherwallet](https://www.myetherwallet.com/), [imtoken](https://token.im/), [TokenPocket](https://www.tokenpocket.pro/) 等。

## 主网
```
网络名称: OYchain Mainnet
链ID: 126
符号: OY
RPC地址: https://rpc.mainnet.oychain.io
浏览器地址: https://explorer.oychain.io/
WebSocket RPC地址: ws://ws.mainnet.oychain.io
```

*主网和测试网公开节点的访问限频策略为300/10s.*

*开发者也可以使用 [https://explorer.oychain.io/](https://explorer.oychain.io/) 浏览器*

## 测试网
```
网络名称: OYchain Testnet
链ID: 125
符号: OY
RPC地址: https://rpc.testnet.oychain.io
浏览器地址: https://explorer.testnet.oychain.io/
WebSocket RPC地址: ws://ws.testnet.oychain.io

水龙头: https://faucet.oychain.io (仅测试用，无价值)
```
# 开发者

## 运行节点
### 二进制文件
直接访问[https://github.com/NFT-mall/oychain/releases](https://github.com/NFT-mall/oychain/releases)下载最新版本的二进制文件。

### Docker
也可以使用docker进行快速部署和测试。(正在发布中)
([关于如何使用Docker？](https://docs.docker.com/get-started/))

### 编译
#### 编译要求
- Linux or Mac
- golang >= 1.13
- git

golang安装和配置请参考 [https://golang.org/doc/install](https://golang.org/doc/install)

#### 编译步骤
```
git clone -b oychain --single-branch https://github.com/NFT-mall/oychain.git
cd oychain
make geth
```
#### 启动
启动参数配置和以太坊类似，可以通过`./build/bin/geth --help`查看所有的参数配置，可以通过`geth --testnet`加入测试网。

### 部署

#### 推荐配置
```
4核
8G内存
200G并且可扩容的SSD
公网IP并开启TCP/UDP:30303端口
```

#### 启动命令
```
./geth #主网
./geth --testnet #测试网

部分常用参数示例：
/data/oychain/geth \
--datadir /data/.oychain/testnet \ #自定义数据目录
--testnet \ #测试网
--http \ #开启http rpc
--http.addr 0.0.0.0 \ #http rpc监听地址
--http.vhosts * \ #vhosts
--http.corsdomain * \ #http corsdomain
--ws \ #开启ws rpc
--ws.addr 0.0.0.0 \ #ws rpc监听地址
--syncmode full \ #同步模式
--gcmode archive #gc模式
```

可以使用`nohup`,`supervisor`,`systemd`等，使`geth`在后台常驻运行。

参考文档：

- [supervisor](http://supervisord.org/)
- [systemd](https://wiki.debian.org/systemd)

## SDKs

可以使用以下的SDK和OYchain的RPC API进行交互。

- [Js: web3.js](https://github.com/ChainSafe/web3.js) Ethereum JavaScript API
- [Java: web3j](https://github.com/web3j/web3j) Web3 Java Ethereum Ðapp API
- [PHP: web3.php](https://github.com/sc0Vu/web3.php) A php interface for interacting with the Ethereum blockchain and ecosystem.
- [Python: Web3.py](https://github.com/ethereum/web3.py) A Python library for interacting with Ethereum, inspired by web3.js.
- [Golang: go-ethereum](https://github.com/ethereum/go-ethereum)

## 工具
- [合约开发语言：solidity](https://docs.soliditylang.org/en/latest/)
- [合约开发工具：remix](https://remix.ethereum.org/)
- [合约开发套件: truffle](https://www.trufflesuite.com/docs/truffle/overview)
- [合约开发套件: hardhat](https://hardhat.org/)
- [水龙头: faucet](https://faucet.oychain.io)
- [浏览器: explorer](https://explorer.oychain.io)

## 跨链桥
- [OYchain-Bridge](https://)
- [AnySwap](https://anyswap.exchange/bridge)

## 共识
OYchain采用PoSA共识机制，具有成本低、性能高、出块稳的特点，支持最多29个验证人节点；

PoSA结合了PoS和PoA，想要成为验证人，需要先创建节点并提交提案，等待其他活跃的验证人进行投票，半数以上通过之后，则有资格成为验证人。任意地址均可对有资格成为验证人的地址进行质押，当验证人的质押量排名进入前29位之后，则会在下一个epoch成为活跃验证人。

所有的活跃验证人按照预定规则排序，轮流进行出块。如果有验证人在自己的出块轮次没能及时出块，则在过去n/2(n为活跃验证人的数量)个块内，没有参与过出块操作的活跃验证人，随机进行出块。最少n/2+1个活跃验证人正常工作，即可保证区块链的正常运行。

正常产块时，区块的难度值为2，未按照预定顺序进行产块时，区块的难度值为1。当区块链发生分叉时，区块链按照累计最大难度选择对应分叉。

### 内置合约
OYchain在genesis文件中内置了PoSA共识相关的合约，
合约源代码fork自heco，可在[https://github.com/NFT-mall/oychain-genesis-contracts](https://github.com/NFT-mall/oychain-genesis-contracts)查看。

目前验证人的管理，均由系统合约完成，目前的系统合约有：
- proposal 负责管理验证人的准入资格，管理验证人提案和投票；
- validators 负责对验证人进行排名管理、质押和解质押操作、分发区块奖励等；
- punish 负责对不正常工作的活跃验证人进行惩罚操作；

区块链调用系统合约：
- 每个块结束的时候，会调用validators合约，将区块中所有交易的手续费分发给active validator;
- 发现validator没有正常工作的时候，会调用punish合约，对validator进行惩罚；
- 每个epoch结束的时候，会调用validators合约，根据排名，更新active validator；

### 质押
用户可以调用validator合约的`stake`方法，对任意节点进行质押，每个validator的最小质押量是32 OY。

### 解质押
如果用户想取回质押的OY，需要先调用validators合约的`unstake`方法进行解质押，然后在86400个块之后(3天)，再调用validators合约的`withdrawStaking`方法才能把质押的OY取回到可用余额。

### 惩罚
如果验证人没有按照预定规则进行出块，就会在这个块结束时，自动调用punish合约，对验证人进行计数。当计数达到24次时，罚没验证人的所有收入。当计数达到48次时，将验证人移除出活跃验证人列表，同时取消验证人资格。

## TheGraph
Graph Node是一个使用GraphQL在以太坊和IPFS上快速构建去中心化应用(dApps)的协议。




**如果需要使用服务，请填写[申请表单](https://forms.office.com/r/DQawaDHtnF)**

**由于性能问题，我们建议你按照[TheGraph官方文档](https://thegraph.com/docs/)进行私有化部署，并部署自己的全节点。**


# 社区治理

## 建议&问题&讨论

我们欢迎社区的任何建议、问题和讨论，并建立了通用的Github渠道：

[建议和问题](https://github.com/NFT-mall/any-advice-issue/issues)

[讨论](https://github.com/NFT-mall/any-advice-issue/discussions)

关于某一个具体项目的问题，请移步到具体的项目中开启`issue`。


## OIPs
OYchain Improvement Proposals

OIP是oychain改进提议的缩写，任何社区用户都可以在这里发起有关OYchain及相关应用的提议，
参与讨论并执行。

提议地址：[https://github.com/NFT-mall/KIPs](https://github.com/NFT-mall/KIPs)

# FAQ
1.OYchain的共识机制是什么？

>OYchain采用PoSA共识机制，具有成本低、性能高、出块稳的特点，支持最多29个验证人节点；

2.如何成为OYchain验证人节点

>想要成为验证人，需要先创建节点并提交提案，等待其他活跃的验证人进行投票，半数以上通过之后，则有资格成为验证人。任意地址均可对有资格成为验证人的地址进行质押，当验证人的质押量排名进入前29位之后，则会在下一个epoch成为活跃验证人。

3.OYchain是否支持EVM？

>OYchain完全支持以太坊EVM，对以太坊开发者完全友好。

4.OYchain使用什么sdk?

>OYchain高度兼容 Ethereum，因此使用 Ethereum 的 sdk，例如 web3js， web3j 等。

5.我想在OYchain测试网进行一些操作与测试，去哪可以获得测试代币？

>可以访问我们的测试网水龙头：https://faucet.oychain.io.

6.如何对合约节点进行质押？

>用户可以调用validator合约的stake方法，对任意节点进行质押，每个validator的最小质押量是32 OY。

7.如何进行解质押？

>如果用户想取回质押的OY，需要先调用validators合约的unstake方法进行解质押，然后在86400个块之后(3天)，再调用validators合约的withdrawStaking方法才能把质押的OY取回到可用余额。

8.使用METAMASK卡顿（包括但不限于转账卡顿、延迟，数据显示等问题）

>使用插件的 expand view（扩展视图）模式全屏展示更稳定；
>选择“加速”，将gaslimt和gasPrice调高。

9.如何使用OYchain Bridge进行资产跨链？

>可以参考我们的视频教程：https://www.youtube.com/watch?v=kZdX1V2Tgnc

>更多教程欢迎订阅我们的Youtube频道：https://www.youtube.com/channel/UCZhWm40SuAApnLqqq3F9o1w

10.如果我们将Tether发送到不支持OYchain的地址时使用的是ERC20而不是OYchain会发生什么？代币会在一段时间后返还到原钱包地址吗？

>如果目标地址是您的个人地址，则操作非常简单。 把钱包网络改成OYchain，导入你的地址和你的OYchain-USDT合约地址，就可以看到USDT余额了。

>如果您的目标地址是交易所或中心化钱包，您需要联系他们的客户支持，让他们支持 OYchain 或将其退款到您的原始地址。

>因此，我们建议我们的用户清楚他们为什么要进行代币转移，因为区块链具有不可变性，这意味着任何转移一旦发送就无法回滚，所以我们建议您先用较小的金额进行尝试。

## 如何配置 MetaMask 钱包

使用 Chrome 浏览器打开 MetaMask [安装地址](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=zh-CN)

根据页面提示创建以太坊钱包，**备份好私钥及助记词**；

切换到 OYchain 主网

(1) 打开 MetaMask，可以看到钱包被默认设置成【以太坊主网】。

<img width="170" alt="C1" src="https://user-images.githubusercontent.com/13411690/121639732-8e4e6a00-cabf-11eb-8c81-a7ac380bd2b9.png">



点击【以太坊主网】，在下拉菜单中点击【自定义 RPC】

<img width="170" alt="C2" src="https://user-images.githubusercontent.com/13411690/121639736-90b0c400-cabf-11eb-93ab-794d99bf28d9.png">


![metamask-mainnet-cn.png](https://github.com/nfttoken/oychain-docs/blob/main/metamask-mainnet-cn.png)



(2) 切换到 OYchain 测试网请在表单中填入下列数据：

    网络名称：OYchain Testnet
    
    RPC URL：https://rpc.testnet.oychain.io
    
    ChainID: 125
    
    符号：OY
    
    浏览器链接:https://explorer.testnet.oychain.io/

<img width="170" alt="C3" src="metamask1.jpg">

![metamask-testnet-cn.png](https://github.com/nfttoken/oychain-docs/blob/main/metamask-testnet-cn.png)

成功

<img width="170" alt="C4" src="metamask2.jpg">

## 如何处理MetaMask卡住的交易？
[[视频]How to Unstuck Stuck Transactions on MetaMask (OYchain)](https://)

## 如何在MetaMask添加OYchain上的资产?
[[视频]How to add a custom token to your MetaMask wallet (OYchain)](https://)



