==Block chain is secured by mining==(区块链被挖矿保护)
#### 比特币挖矿机制的缺点
- 挖矿门槛的提高
- 挖矿间隔十分钟
#### LiteCoin
- scrypt:对内存要求很高的挖矿协议
	- ASIC—resistance and GPU—resistance
	- ![[Pasted image 20240426163113.png]]
	经过计算得到seed
	表后面的数都是对前面的数取hash，得到一个数组
	然后用伪随机的顺序读取数组，进行运算
	- 问题：验证困难
- 出块间隔为两分半
### ETH
ASIC resistance
- ethash
![[Pasted image 20240426164727.png]]
- 经过根据block header和nonce计算得到seed
	  表后面的数都是对前面的数取hash，得到一个数组cache
	  然后用伪随机的顺序读取数组，进行256次读取，每次 读取的值都填入dataset
	  mining时在dataset中读取64次（128个数），最后和难度阈值比较，不行更换nonce在进行
	- 有两个数据集
	- cache（轻节点保存）
	-  dataset （miner保存）
	- 数据集都逐渐增长，初始cache为16M，dataset为1G
#### 伪代码
![[Pasted image 20240426164838.png]]
![[Pasted image 20240426165024.png]]![[Pasted image 20240426165042.png]]![[Pasted image 20240426170612.png]]![[Pasted image 20240426170703.png]]