#### UTXO(未被花掉的输出)-SUI链
- 账户模本模型
	- 账户余额由不同的Coin组成
		- exp：100sui可能有60个Coin做加法得到。。
		- 10也可能有100个Coin
#### Sui的数据存储模型
- 对象在Sui上维护了一个全局的Map结构
	- Map<ID,object>
#### Object定义
- 必须有key能力
- 第一个字段必须是id
	- 且类型为sui::object::UID
#### 资产
- Object
- 银行余额，房产等与现实中的资产被程序的方式定义
#### 资产所有权
- 所有权和实际使用权不一样
- 独有资产
	- 对象有字段标记所有权
	- 对象被某个地址拥有
- 共有资产
	- 对象被全局共享
	
```move
 //独享
transfer(object,ctx.sender())
public_transfer()
//共享 常量-不能再改变
freeze_object()
public_freeze_object()
//共享
share_object()
publich_share_object()
```
所有权
- T
	- 转移，删除，写入，可读
- &mut T
	- 读写
- &mut
	- 读
