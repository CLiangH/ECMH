项目目标
=

Implement the ECMH scheme

代码解析
=

__曲线选取__
____________________

在此我们选取secp256k1曲线，相关参数如下

`p = 0xfffffffffffffffffffffffffffffffffffffffffffffffffffffffefffffc2f`

`a = 0`

`b = 7`

`n = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141`

`Gx = 0x79be667ef9dcbbac55a06295ce870b07029bfcdb2dce28d959f2815b16f81798`

`Gy = 0x483ada7726a3c4655da4fbfc0e1108a8fd17b448a68554199c47d08ffb10d4b8`

`G = [Gx, Gy]`

__求解二次剩余__
____________________

我们使用勒让德符号来判断、求取二次剩余，此处代码参考博客：https://blog.csdn.net/weixin_44617902/article/details/112785051

__ECMH函数__
____________________

我们不停地将消息更新为它的哈希值，倘若此哈希值在椭圆曲线上有解，则通过二次剩余将其求出，
并输出此节点。如此我们即找到了一个正确的解

__ECMH_Group函数__
____________________

此步我们只需要将所有元素单独求解得到一堆点，之后将其相加即可。

运行指导
=

直接运行即可。

__注意：由于系统自带哈希函数本身的缺陷，可能会出现哈希值不变情况导致系统停滞，此时可以重启或修改明文__

运行截图
=

![image](https://github.com/CLiangH/Picture/blob/main/ECMH2.png)
![image](https://github.com/CLiangH/Picture/blob/main/ECMH1.png)











