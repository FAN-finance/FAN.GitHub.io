## 数据读取合约

- 合约名：Rate

- 类型：预言机 - 提供房贷利率信息
- 合约源码

### 1.概述

预言机合约。接受其他合约调用读取美国10大城市房产抵押贷款利率数据。

### 2.合约细节

#### 合约存储

- wards
- getPurchase
- getRefinance

#### 公共方法

##### 管理员方法

- rely / deny ：增加或移除一个被授权的用户。

##### 订阅读取方法

- getPurchase(uint city, uint product) ：返回新购房产抵押利率

- getRefinance(uint city, uint product) ：返回再融资房产抵押利率

##### 订阅更新方法

- setPurchase(uint city, uint product, uint _rate, uint _apr)  external note auth returns(bool)

- setRefinance(uint city, uint product, uint _rate, uint _apr) external note auth returns(bool)

### 3.相关参数

#### 函数参数

| 参数    | 类型 | 说明     |
| ------- | ---- | -------- |
| city    | uint | 城市     |
| product | uint | 产品     |
| _rate   | uint | 基准利率 |
| _apr    | uint | 平均利率 |

#### 参数对应表1

| city          | value |
| ------------- | ----- |
| New York      | 1     |
| Los Angeles   | 2     |
| Chicago       | 3     |
| Houston       | 4     |
| Philadelphia  | 5     |
| Detroit       | 6     |
| San Francisco | 7     |
| Boston        | 8     |
| Pittsburgh    | 9     |
| Atlanta       | 10    |

#### 参数对应表2

| product                 | value |
| ----------------------- | ----- |
| 15 year fixed refinance | 1     |
| 15 year jumbo refinance | 2     |
| 10/1 ARM refinance      | 3     |

### 4.调用示例

```javascript
var Web3 = require('web3');

var rateContractAddr = '0x4b724A99a247993e0133d34Ec6AbfD4939812F79'; // kovan测试网络合约地址
var web3 = new Web3(new Web3.providers.HttpProvider("https://kovan.infura.io/v3/88ae15efc1c04e35bcc227e4d3284676"));

var rateContract = new web3.eth.Contract([{"inputs":[],"payable":false,"stateMutability":"nonpayable","type":"constructor"},{"anonymous":true,"inputs":[{"indexed":true,"internalType":"bytes4","name":"sig","type":"bytes4"},{"indexed":true,"internalType":"address","name":"usr","type":"address"},{"indexed":true,"internalType":"bytes32","name":"arg1","type":"bytes32"},{"indexed":true,"internalType":"bytes32","name":"arg2","type":"bytes32"},{"indexed":false,"internalType":"bytes","name":"data","type":"bytes"}],"name":"LogNote","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"internalType":"uint256","name":"city","type":"uint256"},{"indexed":true,"internalType":"uint256","name":"product","type":"uint256"},{"indexed":false,"internalType":"uint256","name":"rate","type":"uint256"},{"indexed":false,"internalType":"uint256","name":"apr","type":"uint256"}],"name":"SetOracle","type":"event"},{"constant":false,"inputs":[{"internalType":"address","name":"guy","type":"address"}],"name":"deny","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"internalType":"uint256","name":"","type":"uint256"},{"internalType":"uint256","name":"","type":"uint256"}],"name":"getPurchase","outputs":[{"internalType":"uint256","name":"rate","type":"uint256"},{"internalType":"uint256","name":"apr","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[{"internalType":"uint256","name":"","type":"uint256"},{"internalType":"uint256","name":"","type":"uint256"}],"name":"getRefinance","outputs":[{"internalType":"uint256","name":"rate","type":"uint256"},{"internalType":"uint256","name":"apr","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"internalType":"address","name":"guy","type":"address"}],"name":"rely","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"internalType":"uint256","name":"city","type":"uint256"},{"internalType":"uint256","name":"product","type":"uint256"},{"internalType":"uint256","name":"_rate","type":"uint256"},{"internalType":"uint256","name":"_apr","type":"uint256"}],"name":"setPurchase","outputs":[{"internalType":"bool","name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"internalType":"uint256","name":"city","type":"uint256"},{"internalType":"uint256","name":"product","type":"uint256"},{"internalType":"uint256","name":"_rate","type":"uint256"},{"internalType":"uint256","name":"_apr","type":"uint256"}],"name":"setRefinance","outputs":[{"internalType":"bool","name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"internalType":"address","name":"","type":"address"}],"name":"wards","outputs":[{"internalType":"uint256","name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"}], rateContractAddr);

var gasLimit = 300000;

var city = 1;
var product = 1;

rateContract.methods.getRefinance(city, product).call({},(err,res)=>console.log)
```



## 数据写入合约

- 合约名：setRate
- 类型：预言机 - 节点提交利率信息

setRate.sol

### 2.主要方法及变量

### 3.调用方式