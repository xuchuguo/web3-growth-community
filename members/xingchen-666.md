## 1. 2024-03-24

- 去中心化、开放性和提高消费者实用性的基本理念构成了Web3.0的基础
- 什么是区块链？
  - 计算机网络节点之间共享的去中心化数据库。
  - 可以轻松收集、集成和共享来自众多来源的交易数据。
  - 能确保数据完整性，区块链使用单一事实来源来消除数据重复并提高安全性 。
  - 可以防止欺诈和数据篡改，因为未经各方节点许可，数据无法更改。
- 区块链的工作原理是什么？
  - 记录交易
  - 达成共识
  - 对区块链进行链接
  - 共享分类账
-  构建区块链学习的知识体系合集，汇聚各种区块链资源(https://github.com/Eternaldeath/BlockchainHome)
- web3-react(https://github.com/Uniswap/web3-react) 。

## 2. 2024-03-31

-  Web3、全栈 Solidity、智能合约和区块链-初学者到专家终极课程JavaScript版(https://github.com/smartcontractkit/full-blockchain-solidity-course-js)
   - 视频链接：https://www.youtube.com/watch?v=gyMwXuJrbJQ
-  web3指南(https://learnblockchain.cn/article/4478)
-  如何将使用Metamask连接到智能合约
   -  1.在浏览器中使用Metamask，先安装Metamask，打印window.ethereum(Metamask文档:https://docs.metamask.io/wallet/how-to/use-sdk/#the-provider-window-ethereum)
   -  2.创建标准的HTML文档，添加一个（connect）按钮和script标签，并创建一个JavaScript函数，寻找window.ethereum，并发出连接请求
        <!DOCTYPE html>
            <head>
              <title>Javascript Test</title>
            </head>
            <body>
                <button id="connectButton" onclick="connect()">Connect</button>
            </body>
            <script>
                async function connect() {
                  if (typeof window.ethereum !== "undefined") {
                    try {
                      await window.ethereum.request({ method: "eth_requestAccounts" });
                    } catch (error) {
                      console.log(error);
                    }
                }}
            </script>
         </html>
   -  3.使用ethersjs和web3js等包来进行连接，发送一个交易，在JavaScript中执行一个函数/发送一个交易的JavaScript，代码如下
      const etheres = require("ethers")
      contractAddress = "0x5FbDB2315678afecb367f032d93F642f64180aa3";
      const abi = // some big javascript ABI here...
      
      const provider = new ethers.providers.JsonRpcProvider(/* alchemy or infura */)
      const wallet = new ethers.Wallet(/* Private key */, provider)
     
      const contract = new ethers.Contract(contractAddress, abi, wallet)
      const contractWithSigner = contract.connect(wallet)
      const transactionResponse = contract.someFunction()

    - 4.在浏览器中发送交易的唯一区别是，我们将提供者改为window.ethereum，通过wallet将直接来provider。由于Metamask即是我们的提供者也是钱包（或签名者），代码如下：
      const etheres = require("ethers")
      contractAddress = "0x5FbDB2315678afecb367f032d93F642f64180aa3";
      const abi = // some big javascript ABI here...

      const provider = new ethers.providers.Web3Provider(window.ethereum)
      const signer = provider.getSigner();

      const contract = new ethers.Contract(contractAddress, abi, signer)
      const contractWithSigner = contract.connect(wallet)
      const transactionResponse = contract.someFunction()

    - 5.中间的两行改变了，现在从window.ethereum获得钱包，我们的签名者（signer）来自提供者（即metamask）。
  
## 3. 2024-04-06
- 1.通过NestJS项目来熟悉Web3
   - 1.1.使用本地Hardhat区块链和合约
   - 1.2.使用本地区块链设置MetaMask
   - 1.3.使用Ethers工具与基于EVM的区块链应用程序连接到钱包(Walletconnect)
   - 1.4.了解Web3Modal、区块链等的一些前沿的前端使用，能查看Scaffold-ETH。
   - 1.5.了解Moralis(react-moralis)，是第一个包含上下文管理组件的软件包，实现组件之间轻松共享状态
   - 1.6.了解web3-react。这是被Uniswap、Aave和Compound等顶级项目最广泛使用的包之一