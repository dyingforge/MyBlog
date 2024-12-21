![[Pasted image 20240409180352.png]]注释：output——输出![[Pasted image 20240409180602.png]]
locktime——交易的生效时间（一般为0）
time——交易产生时间
blocktime——区块产生时间![[Pasted image 20240409180830.png]
vout——交易中的第几个输出
![[Pasted image 20240409181615.png]]asm——交易的具体内容 
reqsigs——交易还需要多少个区块才能兑现![[Pasted image 20240409181901.png]]
先执行输入脚本再 执行输出脚本![[Pasted image 20240409182023.png]]
![[Pasted image 20240409182256.png]]![[Pasted image 20240409183515.png]]![[Pasted image 20240409183106.png]]  P2SH应用：
1.多重签名 
![[Pasted image 20240409185018.png]]
1.销毁比特币
AltCoin（Alternative coin）：需要摧毁比特币才能得到的货币
2.往区块链里提交一些内容——销毁很少的比特币（也可以把比特币作为交易费交给矿工）来获得往链中写入信息的权利
比特币脚本语言一般不支持循环，所以不存在停机问题