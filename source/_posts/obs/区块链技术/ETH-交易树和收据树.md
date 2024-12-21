交易树和收据树都只包含当前交易的区块，但状态树是包含所有区块
每个交易完后会形成一个收据
每个交易的交易树和收据树都是独立的
作用：提供merkle proof
bloom filter（）：把每个元素取哈希在向量上映为1，把所有元素处理完形成的向量，就是该集合的digest（摘要）![[Pasted image 20240425152643.png]]
	注意：1.任选一个元素，如果映射到向量的值为0，该集合肯定不含该元素，但值为1不能说明含该元素（collision resistance）。
		2.bloom filter这个数据结构不支持删除操作
		3.一般取出来的向量要远小于原集合
		4.在查找时会出现fasle positive（错报），但不会false negetive（漏报）
		5.每个交易产生的收据中都有一个bloom filter，在每个区块的block header里也有一个总的bloom filter，是每个交易中的bloom filter的并集
	作用：1.查找，在查找时现在block header里的bloom filter中查找，如果有在去每个交易里查找
#### 以太坊的运行状态：transacion——driven state machine（交易驱动的状态机）
- 状态：每个账户的状态
- 交易：区块正在进行的交易
- 这些交易会会驱动状态的改变
- 状态转移必须是确定性的
#### 具体代码![[Pasted image 20240425155749.png]]
创建交易树，调用函树的得到root hash，创建交易列表
![[Pasted image 20240425155926.png]]
创建交易树，同样得到root hash，创建bloom filter
![[Pasted image 20240425160025.png]]
计算叔父区块的hash值，构建叔父数组![[Pasted image 20240425160105.png]]
deriveSha函数，得到前两个根hash的函数，用的是MPT
![[Pasted image 20240425160614.png]]
查询函数：查找topic，用bloom9函数把topic变成一个victor（向量），然后用and操作比较是否相等
