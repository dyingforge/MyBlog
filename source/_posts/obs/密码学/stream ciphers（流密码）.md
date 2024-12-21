例：
- 手机信号加密
- ![[Pasted image 20240427161800.png]]
问：为什么加密和解密是一种方法
![[Pasted image 20240427162415.png]]
mod2和xor（异或）是一样的操作
![[Pasted image 20240427163444.png]]
实例：ASCII“A”![[Pasted image 20240427164203.png]]
Q：如何得到si（流密码秘钥）：
- 随机数
#### 随机数生成器（Random Number Generators）-RNG
- True Random Number Generators（TRNG）:随机的物理过程.etc
	- 掷硬币
	- 彩票
	- 热噪音
	- 鼠标点击节奏
- pseudo(伪) Random Number Generators（PRNG）:确定的
	- C语言的rand函数
- cryptogiaphycally secure PRANG（CPRNG）:密码安全的PRNG
	- ==不可预测的==
		- 无法被现代计算机所计算出来
#### one time pad（OTP）：一次性密码
- 流密码秘钥来自TRNG
- 每一个秘钥只使用一次
- 绝对安全
- 但是使用起来极其复杂，秘钥保存，生成，使用完的销毁
#### linear congruential geneator（LCG）：
- 使用一个由PRNG生成的流密码秘钥
- ![[Pasted image 20240427171851.png]]