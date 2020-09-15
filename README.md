# Uniswap Interface

An open source interface for Uniswap -- a protocol for decentralized exchange of Ethereum tokens.

- Website: [uniswap.org](https://uniswap.org/)
- Interface: [app.uniswap.org](https://app.uniswap.org)
- Docs: [uniswap.org/docs/](https://uniswap.org/docs/)
- Twitter: [@UniswapProtocol](https://twitter.com/UniswapProtocol)
- Reddit: [/r/Uniswap](https://www.reddit.com/r/Uniswap/)
- Email: [contact@uniswap.org](mailto:contact@uniswap.org)
- Discord: [Uniswap](https://discord.gg/Y7TF6QA)
- Whitepaper: [Link](https://hackmd.io/C-DvwDSfSxuh-Gd4WKE_ig)

## 一.deploy smart contract

##  二. Accessing the Uniswap Interface

To access the Uniswap Interface, use an IPFS gateway link from the
[latest release](https://github.com/Uniswap/uniswap-interface/releases/latest), 
or visit [app.uniswap.org](https://app.uniswap.org).

## Listing a token

Please see the
[@uniswap/default-token-list](https://github.com/uniswap/default-token-list) 
repository.

## Development

### 1.Install Dependencies

```bash
yarn
```

### 2. replace data
全局查找替换掉uniswap合约数据（前端项目引用了uniswap的sdk,工厂合约，code是硬编码在sdk中的）
```bash
--合约信息（uniswap官方）
factory:0x5C69bEe701ef814a2B6a3EDD4B1652CB9cc5aA6f
router:0x7a250d5630B4cF539739dF2C5dAcb4c659F2488D
code:0x96e8ac4277198ff8b6f785478aa9a39f403cb768dd02cbee326c3e7da348845f
 ```
替换成自己发布的合约信息 如：
```bash
--ropsten测试网络
factory:0xe543c636ee1e1712d71d2f2e2c794734ed065fb6
router:0x75189c2e3b88169f36459fbcc8ccfd6c05233233
byteCode:0x47057720542d8658992f8b0f3b976a1cd82407175676c361c74a89386ff84547
```
替换路由合约地址（src\constants\index.ts文件中）
```bash
export const ROUTER_ADDRESS = '0x75189c2e3b88169f36459fbcc8ccfd6c05233233'
替换成自己的发布的路由合约地址
```

### Run

```bash
yarn start
```

### Configuring the environment (optional)

To have the interface default to a different network when a wallet is not connected:

1. Make a copy of `.env` named `.env.local`
2. Change `REACT_APP_NETWORK_ID` to `"{YOUR_NETWORK_ID}"`
3. Change `REACT_APP_NETWORK_URL` to e.g. `"https://{YOUR_NETWORK_ID}.infura.io/v3/{YOUR_INFURA_KEY}"` 

Note that the interface only works on testnets where both 
[Uniswap V2](https://uniswap.org/docs/v2/smart-contracts/factory/) and 
[multicall](https://github.com/makerdao/multicall) are deployed.
The interface will not work on other networks.

## Contributions

**Please open all pull requests against the `master` branch.** 
CI checks will run against all PRs.

## Accessing Uniswap Interface V1

The Uniswap Interface supports swapping against, and migrating or removing liquidity from Uniswap V1. However,
if you would like to use Uniswap V1, the Uniswap V1 interface for mainnet and testnets is accessible via IPFS gateways 
linked from the [v1.0.0 release](https://github.com/Uniswap/uniswap-interface/releases/tag/v1.0.0).
