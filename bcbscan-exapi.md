# BCBScan APIs


## 概览
BCBScan


### 版本信息
*版本* : 1.0
#### 获取地址信息
```
GET /bcbscan/address/info/{address}
```


##### 请求参数

|参数名称|是否必填|说明|类型|
|---|---|---|---|
|address|必填|地址|string|

##### 返回字段

| 字段名          | 类型   | 说明         |
| --------------- | ------ | ------------ |
| status          | string | 状态         |
| code            | string | 200表示成功  |
| message         | string | 错误信息     |
| data            |        |              |
| └─balance       | string | 余额         |
| └─dolar         | string | 价值         |
| └─count         | int    | 交易笔数     |
| └─coinCode      | string | 币种         |
| └─balanceDollar | string | bcb价值      |
| └─coinBalances  |        |              |
| └─contractAddr  | string | 代币合约地址 |
| └─amount        | string | 代币金额     |
| └─symbol        | string | 代币符号     |
| └─name          | string | 代币名称     |


##### HTTP请求示例

```
/bcbscan/address/info/bcbFG9SVLBcoeUNQD2cgEzm2PnRVhFe7FVCJ
```


##### HTTP响应示例

```
{
	"status": "ok",
	"code": "200",
	"message": "请求成功",
	"data": {
		"balance": "1.100133642",
		"dolar": "4.268",
		"count": 616,
		"balanceDollar": "4.695370384056",
		"coinBalances": [{
			"contractAddr": "bcbQHfswgqQwtwc3z94Z5reJmSSPMmJaoArc",
			"amount": "1.9",
			"symbol": "BUKY",
			"name": "BUKY"
		}, {
			"contractAddr": "bcbPc8XxVCoMftDthcCb2g4LMaWW4HqnERKe",
			"amount": "5.0",
			"symbol": "OMG",
			"name": "OMG"
		}, {
			"contractAddr": "bcbPZ3x8gvng1S8YVb7joCWi6WXhXWGK15GL",
			"amount": "0.0",
			"symbol": "1wbg",
			"name": "1woh",
		}, {
			"contractAddr": "bcbMdHapwhKgfXURphx435wGx5caGF7GKJ23",
			"amount": "10.0",
			"symbol": "SOC",
			"name": "SOC"
		}, {
			"contractAddr": "bcbMLpC7HFd8JCm6RXQiu1t7aX4GaiW5c4Cm",
			"amount": "0.0",
			"symbol": "USDX",
			"name": "USDX"
		}, {
			"contractAddr": "bcbMLKQ83Zxq2Z124W52c5YAucKRppVjJiqx",
			"amount": "8.0",
			"symbol": "QCash",
			"name": "QCash"
		}, {
			"contractAddr": "bcbLz1pEPbHnPcMd6BuyFuqMKJCqG6Hh7c6N",
			"amount": "10.0",
			"symbol": "ETEH",
			"name": "ETEH"
		}, {
			"contractAddr": "bcbLVgb3odTfKC9Y9GeFnNWL9wmR4pwWiqwe",
			"amount": "1.100133642",
			"symbol": "BCB",
			"name": "BCB"
		}, {
			"contractAddr": "bcbFPsQdpvDHgQxWLHvqrGvEuGaiQyyERudp",
			"amount": "0.0",
			"symbol": "ZIL",
			"name": "ZIL"
		}, {
			"contractAddr": "bcbDXYei2kgCsdzb7v8t3mBrT2zkPVzc7ZSC",
			"amount": "4.0",
			"symbol": "KHR",
			"name": "KHR"
		}, {
			"contractAddr": "bcbCsRXXMGkUJ8wRnrBUD7mQsMST4d53JRKJ",
			"amount": "0.014391828",
			"symbol": "DC",
			"name": "Diamond Coin"
		}, {
			"contractAddr": "bcbBtMbA6Y1Hu7W3PymfHfduNwPYGL2ABL8v",
			"amount": "5.0",
			"symbol": "tcl",
			"name": "tcl"
		}, {
			"contractAddr": "bcbBV3hkzjYDgVkUq43FDXQenDNm2Mgv8Z5Q",
			"amount": "4.0",
			"symbol": "PSY",
			"name": "PSY"
		}, {
			"contractAddr": "bcb7YkM3oi6yx1zfumq24mdURM2vTJFjM8PZ",
			"amount": "4.0",
			"symbol": "taz",
			"name": "taz"
		}, {
			"contractAddr": "bcb5VoPNmLFAVV33ir6HYCTZEyzkWuAKNU8p",
			"amount": "5.0",
			"symbol": "INE",
			"name": "INE"
		}, {
			"contractAddr": "bcb46S1M4FGssqjQ2xrdguoBSbybBg9zJWgp",
			"amount": "5.0",
			"symbol": "PSX",
			"name": "PSX"
		}, {
			"contractAddr": "bcb3jG6s8decMHDspc3xTH1ngohbPQkzHmas",
			"amount": "4.0",
			"symbol": "THBY",
			"name": "THBY"
		}, {
			"contractAddr": "bcb2oTPDU5B2ZJyKazdQ38waBpYkjyMLqFCy",
			"amount": "5.0",
			"symbol": "VET",
			"name": "VET"
		}],
		"coinCode": "BCB"
	}
}
```


#### 区块详情
```
GET /bcbscan/block/{blockHeightOrHash}
```
##### 请求参数

|参数名称|是否必填|说明|类型|
|---|---|---|---|
|blockHeightOrHash|必填|区块高度/区块hash|string|
##### 返回字段

| 字段名            | 类型   | 说明                   |
| ----------------- | ------ | ---------------------- |
| status            | string | 状态                   |
| code              | string | 200表示成功            |
| message           | string | 错误信息               |
| data              |        |                        |
| └─validators      | list   |                        |
| └─validatorAddr   | string | 见证者节点             |
| └─_round          | string | _round                 |
| └─detail          | obj    |                        |
| └─blockHeight     | long   | 区块高度               |
| └─blockHash       | string | 区块hash               |
| └─domainTxCount   | int    | 本区块含有的交易笔数   |
| └─tokenTxCount    | int    | 合约交易数             |
| └─parentHash      | string | parentHash             |
| └─gasLimit        | int    | 燃料消耗               |
| └─timestamp       | string | 交易时间               |
| └─timeDesc        | string | 交易时间戳             |
| └─blockTime       | string | 区块时间               |
| └─proposerAddress | string | 生产者                 |
| └─blockSize       | string | 区块的大小，单位为字节 |
| └─lastMining      | double | 挖矿奖励               |
| └─coinCode        | string | 币种                   |




##### HTTP请求示例

```
/bcbscan/block/30257971
```


##### HTTP响应示例

```
{
	"status": "success",
	"code": "200",
	"message": "请求成功",
	"data": {
		"validators": [{
			"validatorAddr": "bcbASX7yURtV7yTRHjF6HMtef5SdverDw1ee",
			"_round": "0"
		}, {
			"validatorAddr": "bcbCUh7Zsb7PBgLwHJVok2QaMhbW64HNK4FU",
			"_round": "0"
		}, {
			"validatorAddr": "bcbG6WixauSd9RZ6iLCygSYZdZ7bttmhQ2zh",
			"_round": "0"
		}, {
			"validatorAddr": "bcbGMKrue1tabboHwokE2WDshAhVD98XbJjH",
			"_round": "0"
		}, {
			"validatorAddr": "bcbHS2RUcXpKVLSK4djJzzXmX25mdskgxpes",
			"_round": "0"
		}, {
			"validatorAddr": "bcbJofNo2NYSv1wZA2dwQa59MCGxaBSEkRgh",
			"_round": "0"
		}, {
			"validatorAddr": "bcbK1gpGpeWcydGM3Lpure4JiYjnwa7xj5Bm",
			"_round": "0"
		}, {
			"validatorAddr": "bcbKVNSGbPEC6PULyJDAc2s4aUQ6oDPAArNX",
			"_round": "0"
		}, {
			"validatorAddr": "bcbNUjCm1i8RcoW2kVTbDw4vKW6jzfMxewJH",
			"_round": "0"
		}, {
			"validatorAddr": "bcbNt6gNp1C6mSZzkCspqnu99wD7TAbtS7Ug",
			"_round": "0"
		}],
		"detail": {
			"blockHeight": 30257971,
			"blockHash": "0x4862886AFCCE9E930D1CC99E6262B3EE093ACE70",
			"domainTxCount": 0,
			"tokenTxCount": 1,
			"parentHash": "0x890ABFEEFD022F692F250E66B7D1D404222EC069",
			"gasLimit": 100000,
			"blockTime": "Tue Jan 14 02:50:37 UTC 2020",
			"timestamp": "Jan-14-2020 02:50:37 AM +UTC",
			"timeDesc": "23 hrs 17 mins ago",
			"proposerAddress": "bcb5rzgE1tSJbJuegEj4vbAkotmwRkxwiSyV",
			"blockSize": "2763",
			"lastMining": 0.15,
			"coinCode": "BCB"
		}
	}
}
```


#### 交易详情
```
GET /bcbscan/tx/{txHash}
```


##### 请求参数

|参数名称|是否必填|说明|类型|
|:-:|:-:|:-:|:-:|
|txHash|必填|交易hash|string|

##### 返回字段

| 字段名         |  类型  |              说明              |
| :------------- | :----: | :----------------------------: |
| status         | string |              状态              |
| code           | string |          200表示成功           |
| message        | string |            错误信息            |
| data           |        |                                |
| └─txid         | string |            交易hash            |
| └─blockHeight  | string |            区块高度            |
| └─_from        | string |             发送方             |
| └─_to          | string |             接收方             |
| └─contractAddr | string |          代币合约地址          |
| └─amount       | string |            交易数量            |
| └─amountDollar | string |            交易金额            |
| └─gasLimit     | string |            燃料总量            |
| └─fee          | string |             手续费             |
| └─feeDollar    | string |           手续费金额           |
| └─methodId     | string |             方法ID             |
| └─timestamp    | string |            交易时间            |
| └─timeDesc     | string |           交易时间戳           |
| └─status       |  int   | 交易状态 1:交易成功,0:交易失败 |
| └─confirmBlock |  int   |       block confirmation       |
| └─nonce        |  int   |             nonce              |
| └─note         | string |              备注              |
| └─inputData    | string |          方法调用信息          |
| └─resultData   | string |          方法输出信息          |
| └─isDoman      | string |            合约类型            |
| └─tokenAmount  | string |          tokenAmount           |
| └─feeCoinType  | string |           手续费币种           |
| └─coinCode     | string |            交易币种            |
| └─gasUsed      | string |            燃料消耗            |

##### HTTP请求示例
```
/bcbscan/tx/0xe4da08829b1c0ee3ec57f76b82dff920595012c2195c48a176feef09559b86f9
```
##### HTTP响应示例
```
{
	"status": "ok",
	"code": "200",
	"message": "请求成功",
	"data": [{
		"txid": "0xe4da08829b1c0ee3ec57f76b82dff920595012c2195c48a176feef09559b86f9",
		"blockHeight": 30257971,
		"_from": "bcbFG9SVLBcoeUNQD2cgEzm2PnRVhFe7FVCJ",
		"_to": "bcbMDDm9omuGzK9246qTmw77FqNzQE7PEs8F",
		"contractAddr": "bcbLVgb3odTfKC9Y9GeFnNWL9wmR4pwWiqwe",
		"amount": "0",
		"amountDollar": "0",
		"gasLimit": 100000,
		"fee": "0.00125",
		"feeDollar": "0.005335",
		"newTokenContractAddr": null,
		"newOwnerAddr": null,
		"methodId": "44d8ca60",
		"timestamp": "Jan-14-2020 02:50:37 AM +UTC",
		"timeDesc": "23 hrs 18 mins ago",
		"status": 1,
		"confirmBlock": 57417,
		"nonce": 421,
		"note": "计算机123jajs\uD83D\uDE00",
		"gasPrice": "0.0000025",
		"inputData": "Function: Transfer(types.Address,bn.Number)\n\nMethodID: 44d8ca60\n[0]: bcbMDDm9omuGzK9246qTmw77FqNzQE7PEs8F\n[1]: 1000000\n",
		"isDoman": 0,
		"tokenAmount": "0.001",
		"coinCode": "BCB",
		"failLog": null,
		"resultData": null,
		"feeCoinType": "BCB",
		"ibcHash": null,
		"gasUsed": "500"
	}]
}
```