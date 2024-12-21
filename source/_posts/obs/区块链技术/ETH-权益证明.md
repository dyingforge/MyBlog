 #### ==proof of stake==：virtual mining(虚拟挖矿)
- 原因：
	- 原来的工作量证明太浪费电
- 系统中预留一部分货币给开发者，并出售部分，根据权益证明的共识机制进行分配，投票是根据拥有该币的多少决定
	- 解决电量
	- 能够解决新链刚建立时的薄弱期
- 问题：nothing at stake：可以在两条链上同时下注
![[Pasted image 20240427143145.png]]
#### Caspe协议
- valiator（保证金）
- epoch![[Pasted image 20240427144125.png]]
	- 对前面区块是prepare 后面是commit
	- 投票成功的epoch会变成finality
	- 验证者履行职责可以得到相应奖励
	- 但如果不投票，会退掉一定的valiator，两边下注要没收（销毁）全部