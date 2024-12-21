#### 工作原理：
- ![[Pasted image 20240514131353.png]]
- 所有AES的操作都基于FF
- 分组长度：128bits
- 密钥长度：128.192.256bits
- 圈数：         10.12 .14
- ![[Pasted image 20240514133026.png]]
	- R1:![[Pasted image 20240514133101.png]]
	- R10：![[Pasted image 20240514133204.png]]
#### 圈函数
- 字节代替变换（唯一的非线性变换）——S盒
	- ==S（a）=f(a的-1次方)==
	- ![[Pasted image 20240514133622.png]]
	- 将字节矩阵中的每个字节利用同一个S盒变换成另一个字节，变换后的位置不变
	- 有两个可逆变换而成
		- ![[Pasted image 20240514134837.png]]
		- ![[Pasted image 20240514134211.png]]
	- 面向字节的运算
		- ![[Pasted image 20240514134247.png]]
		-  ![[Pasted image 20240514134424.png]]
			- ![[Pasted image 20240514134501.png]]
- 行移位变换
	- ![[Pasted image 20240514135738.png]]
- 列混合变换
	- ![[Pasted image 20240514135945.png]]
- 圈密钥加
	- ![[Pasted image 20240514140026.png]]
- 密钥生成算法
	- ![[Pasted image 20240514140306.png]]
	- ![[Pasted image 20240514140345.png]]
	- ![[Pasted image 20240514140711.png]]
	- ![[Pasted image 20240514140737.png]]
		- rotebyte 循环左移1个字节
		- Bytesub 字节代换
#### 脱密算法
![[Pasted image 20240514140835.png]]

#### FF-finite fields（有限域）
- 只存在p的m次方的有限域（p为质数，m为整数）
	- 例：
		- 11，256，128
			- 12就没有有限域
	- m为1时为素域
	- m>1时为扩展域
#### 素域
- 元素
	- {0，1，p-1}
- 运算
	- 加法，减法，乘法
	![[Pasted image 20240518155517.png]]
#### 扩展域（2的m次方）
- 元素
	- ![[Pasted image 20240518160616.png]]
- 运算
	- 加法，减法
		- ![[Pasted image 20240518161527.png]]
	- 乘法：乘完后和加加减做相同运算
		- ![[Pasted image 20240518161752.png]]
		- 除法
			- ![[Pasted image 20240518162751.png]]
#### AES的结构
- 