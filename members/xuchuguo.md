## 1. 2024/03/24
### 环境要求
``` js
Node.js: >= 18
Next.js: 14.0.1
TyepScripte: ^5
```
1. 使用`Next` + `wagmi` + `Viem` 搭建demo
2. 翻阅文章 [MetaMask 是怎么保存你的钱包秘钥的？](https://www.wispwisp.com/index.php/2020/12/25/how-metamask-stores-your-wallet-secret/) 

## 2. 2024/03/31
1. 了解智能合约`Solidity`
2. 使用`Remix` 运行`Solidity`合约
3. 学习`Solidity`的变量类型：
   ```
   1.值类型(Value Type)：包括布尔型，整数型等等，这类变量赋值时候直接传递数值。
   2.引用类型(Reference Type)：包括数组和结构体，这类变量占空间大，赋值时候直接传递地址（类似指针）。
   3.映射类型(Mapping Type): Solidity中存储键值对的数据结构，可以理解为哈希表
   ```
   常用类型有
    ```
    1. 布尔型
      // 布尔值
      bool public _bool = true;

    2. 整型
      // 整型
      int public _int = -1; // 整数，包括负数
      uint public _uint = 1; // 正整数
      uint256 public _number = 20240331; // 256位正整数

    3.地址类型
      address: 存储一个 20 字节的值（以太坊地址的大小）
      address payable: 比普通地址多了 transfer 和 send 两个成员方法，用于接收转账

    4.定长字节数组(字节数组分为定长和不定长两种)
    5.枚举
    
  

  ## 3. 2024/04/08
  1. 学习`Solidity`的函数

      ```
      函数可见性说明符
      public：内部和外部均可见
      private：只能从本合约内部访问，继承的合约也不能使用
      external：只能从合约外部访问（但内部可以通过 this.f() 来调用，f是函数名）
      internal: 只能从合约内部访问，继承的合约可以用
      ```
  2. 了解Solidity`pure`和`view`关键字(合约中非`pure`/`view`函数调用`pure`/`view` 函数时需要付gas)`
      ```
      view 函数可以读取状态变量，但不能改写；
      pure 函数既不能读取也不能改写状态变量。
      ```