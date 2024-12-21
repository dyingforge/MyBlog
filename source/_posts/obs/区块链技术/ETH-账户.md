###### 账户模式
BTC：tranduction—based ledger（基于交易的账本）![[Pasted image 20240423090126.png]]
ETH：accoun—based ledger（基于账户的账本）![[Pasted image 20240423090444.png]]
注意：1.不用说明币的来源，不用一次性将币转出。
	2.天然防范double spending attack（双花攻击）
	3.以太坊用nonce（开始nonce为0，每发布一个新交易nonce加1）防范replay attack（重放攻击）——nonce的值也受签名保护![[Pasted image 20240423091158.png]]
###### 账户类型
	1.externally owned account(外部账户，普通账户)
		存在balance（余额）和nonce
	2.smart contract account（合约账户）——不能主动发起一个交易
			code
			storage
			balance
			nonce
				注意：合约账户只能被调用参与一个交易
					智能合约要求要有一个稳定的账户