#### 比特币中的共识机制
- 只有在最长合法链上的出块奖励是被承认合法的
- BTC中30算力的mining pool一般获得超过30的出块奖励
	- 因为更有可能成为最长合法链，而个体节点的链可能无效，这个可能带来centrelization bias（中心化带来的不成比例的优势）
### ETH中的共识机制—GHOST协议
   ==注意现在的出块奖励为2==
- ==初版==：把没有成为最长合法链的上的区块（uncle block），包含进最长合法链的区块中，uncle block能得到7/8的出块奖励，而合法区块多得到1/32的出块奖励![[Pasted image 20240425162801.png]]
	- 问题：出现第三个uncle block怎么办
	- 问题：最长合法链不包含uncle block怎么办
	- 问题：在挖第二个区块时刚被告知uncle block怎么办
- ==二版==：最长合法链上的每个区块都可以找任意的七代以内的两个uncle block包含![[Pasted image 20240425163616.png]]
	- 每代uncle block的出块奖励（uncle reward）会递减![[Pasted image 20240425164326.png]]
		-  不限制，对全节点的压力太大
		- 有利于尽早进行合并
		- 该共识机制只能解决对当前状态问题的分叉不能解决意见分歧的分叉
	- uncle block中的交易信息不会被包含在合法区块中
		- 因为会出现冲突交易，有些合法交易会变成非法交易
	- 只有分叉的第一个区块会被视作uncle block![[Pasted image 20240425171312.png]]
		- 否则forking attack反而会收到奖励
- uncle block得不到gas fee
- [以太坊当前状态](https://etherscan.io/)
 
 
 