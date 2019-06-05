## 关于重庆电子工程职业学院寝室网络的 ~~改造~~ 折腾

学校经过网络一体化改造后虽然对宽带不收费，采用认证登陆的方式上网。但不知从什么时候开始，寝室网络突然被限速为250k,250k!!!!!!。突发奇想写一个思路来折腾折腾寝室的网络。

### 1.采取多wan口登陆的方式，再进行负载均衡。

首先，总得买点什么设备来搞搞吧，一个二手的傻瓜式交换机（30元），一个斐讯K2路由器（40元），再来几段网线。大概网络是这个样子

 ![TIM图片20190605164511](https://github.com/sundidyu/idea/tree/master/imagsTIM图片20190605164511.png)

K2支持多wan口扩展的固件比较方便的应该就是高恪了吧 [视频教程](http://v.youku.com/v_show/id_XMjk1MTYyMTE4MA==.html?spm=a2hzp.8244740.0.0
)，

![2](https://github.com/sundidyu/idea/tree/master/imags2.png)

![3](https://github.com/sundidyu/idea/tree/master/imags3.png)

![4](https://github.com/sundidyu/idea/tree/master/imags4.png)

交换机上插进网的线和四根短的网线，然后把四根网线插到路由器的四个wan口，简直不要太简单。在多线设置里边设置后负载均衡后就随便打开网页登陆上网账号就行。账号是学号，默认密码都是123456   真好。实测网络叠加了四次。也就1M emmmmmm ，勉勉强强。

---

### 2.用虚拟机安装软路由，多网口登陆上网。

如果不用WIFI的话，这样也挺好，不用买什么东西，电脑插上网线就能用，简单粗暴。

软路由的话爱快，红蜘蛛都是可以的，这里用爱快来演示。

虚拟机的话virtualbox只能设置四个网卡，再添加的话需要用命令行；VMware的话直接可以添加10个网卡，哎哟。有点厉害哦。

爱快的话下载32位的iso就行[链接](https://www.ikuai8.com/component/download)

虚拟机选择32位的linux,运行和存储至少1G.添加5个网卡吧，一个lan四个wan。五个网卡都采用桥接的方式。然后就可以进行安装了。安装完成后记得取消虚拟光驱。

![11](https://github.com/sundidyu/idea/tree/master/imags11.png)

![22](https://github.com/sundidyu/idea/tree/master/imags22.png)

![33](https://github.com/sundidyu/idea/tree/master/imags33.png)

![44](https://github.com/sundidyu/idea/tree/master/imags44.png)

![55](https://github.com/sundidyu/idea/tree/master/imags55.png)

![66](https://github.com/sundidyu/idea/tree/master/imags66.png)

![77](https://github.com/sundidyu/idea/tree/master/imags77.png)

![88](https://github.com/sundidyu/idea/tree/master/imags88.png)



在浏览器输入web管理地址就可以登陆到控制台了，账号密码都是admin。

自己电脑设置和web管理地址一个网段，然后进入控制台依次将几个网卡绑定到wan上

然后每次设置一个网卡为默认的网关，打开浏览器随便输个网站就能登陆。将全部网卡登陆后。设置好多线负载后ok了。

![111](https://github.com/sundidyu/idea/tree/master/imags111.png)

![222](https://github.com/sundidyu/idea/tree/master/imags222.png)

![333](https://github.com/sundidyu/idea/tree/master/imags333.png)

![444](https://github.com/sundidyu/idea/tree/master/imags444.png)

![555](https://github.com/sundidyu/idea/tree/master/imags555.png)

---

这样每次电脑开机后运行软路由就能多线叠加了。晚上挂着下下游戏还是能行的。

尽管折腾了这些，网速也不会变得多块。不过呢，重在折腾吧。还是希望网管在某一天给我们调调网速。

#### 仅仅提供一个思路，有很多瑕疵，请原谅。如果有更多想法的小伙伴，请私信我啊

邮箱1569340123@qq.com

