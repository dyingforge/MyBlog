 地址表示为40个16进制的数  ，160位
address —> state(账户状态)
==问：为什么不用hash表？==
每次添加新内容，merkle tree都会改变，构建代价太高
==问：直接建立merkle tree==
没有快速查找更新方法，要排序，不然形状不唯一 ，但排序代价太大
#### trie(字典查找树)
![[Pasted image 20240423191318.png]]
注意：比特币和以太坊的地址是不通用的，但都是公钥经过转换得到的 
#### Patricia tree(压缩前缀树)
![[Pasted image 20240423193054.png]]
适用于稀疏的trie
#### MPT(Meikle Patricia tree)
**优点**：不可篡改，merkle proof
#### modified MPT
 ![[Pasted image 20240423195445.png]]
![[Pasted image 20240423195622.png]]
注意：1.以太坊是一颗MPT包裹很多小的MPT
		2.不同节点的MPT大体相同
		3.每个全节点不是维护一颗MPT，而是新建一个节点时，创建一个新的MPT
		4.不当场维护，而是新建一棵树是为了在分叉时回滚89![[Pasted image 20240423200711.png]]
   以太坊中的数据结构
   ![[Pasted image 20240423200711.png]]
parenthash：区块头的hash
root：状态树的root hash
TXhash：交易树的root hash
Receiphash：收据树的根hash
![[Pasted image 20240423200957.png]]
该图是区块发布时发布的信息
（key，value）：key是地址，value要经过RLP（Recursive Length Profix）序列化

   