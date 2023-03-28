# Hey-Poe-Software-Development
陆流团队互联网+项目：《嘿坡：让社区更聪明的APP》
（一）确立软件项目名称为： 
嘿坡武院（嘿坡）
（二）软件需求分析方法的选择为： 
面向对象分析方法
（三）对软件功能需求描述为：
“嘿坡”的核心功能为社区碎片化服务互助和社区元宇宙世界。社区碎片化互助一方面， 社区居民在生活中需要服务，可以在“嘿坡”中发出请求，接单者接单后会帮助解决其需求； 另一方面，接单者通过接单也可以获得一定的金额回报，使接单者在闲暇的时间里用自己的一技之长也能赚取一些报酬。同时“嘿坡”的社区元宇宙就是对现实生活中的社区虚拟化的过程，人们通过在“嘿坡”上注册填写的地址自动分配到相对应的虚拟社区。“嘿坡”的虚拟社区会根据现实生活中的社区进行分割，保证现实所在社区中的居民在虚拟世界中也处在所在的虚拟社区。当一个居民填写社区时，这个社区的虚拟社区就会自动生成，如果后面其他人填写的资料也是这个小区的就会自动加入这个社区，保证了社区与社区之间的隐私性，在这里没有群主、没有特权，这就是社区居民共同的家园。同时，居民通过发布、接单、购买数字盲盒来获得不同稀有度数字藏品，获得的数字藏品可以用来装饰自己的虚拟形象和所在的虚拟社区，同时这些数字藏品可以在“嘿坡”的自由数字商店自由交易。同时“嘿坡 校园版”在小范围发散，提供的服务更加多、全，在疫情常态化的当下成为广大高校学子生活助手。

（四）对软件需求分析建模
1、用例模型
 
 
2、对象模型
类	服务
BaseUser:系统角色的基类	loginCheck:用于用户登录验证
Form:订单类	formAdd():新增用户订单
formDel():取消用户订单
formAccomplish():已完成用户订单
formComing():待完成用户订单
User类：用户信息类	
userAdd():新增用户信息
userDel():删除用户信息
userModify():修改用户信息
Album：相册类	albumAdd():新增图片
albumDel():删除图片
albumlike():喜欢图片
albumnoulike():不喜欢图片
albumModify():修改用户信息
Historyform：历史订单类	historyAdd():新增历史订单
Administrator:管理员类	formDel():删除用户订单
albumDel():删除用户图片
userDel():注销用户
arrange():管理订单
 
 
3、动态模型
 

（五）系统性能需求描述
在线用户数量：支持1w用户在线
平稳运行时间：30*24h
平均相应时间：打开页面响应时间低于2s

（六）系统接口需求描述
1、界面需求
整体需求
界面简洁，便于用户识别和使用
主要页面以下方导航栏切换
导航栏高度在50p左右
界面主要颜色为白色#ffffff和橙色#fab941
主要字体大小为24px
组件使用圆角20px

主页面
地图填满全部页面
地图上订单以红旗图标标识
订单标识大小适中，易于发现和点击


个人信息页面
个人信息集中放置于页面上方
历史订单选项置于页面中部
下方放置说明文本或相关连接

订单列表页面及历史订单页面
页面上方标识订单所属类别
下方为订单列表
订单列表中订单数量在7个以内，每条订单间有一定间隔

明信片页面
明信片照片显示在页面上部，占据页面大部分区域
下方放置明信片操作选项（个人信息、切换、点赞）
操作选项按钮大小适中，70px左右，不同的操作以图标进行区分
操作选项上部显示当前明信片的点赞数

明信片个人信息页面
最上方显示明信片的照片，下方显示明信片相关信息
底部放置历史订单和个人信息跳转按钮
跳转按钮需要有明显的颜色区分，以区别个人信息和历史订单
历史订单的“我点赞的”和“点赞我的”两种按钮以图标形式加以区分

2、外部接口需求（
腾讯地图sdk
微信小程序内置api
（七）其他需求描述
1、安全性需求
1、字符串加密：将App的源代码中敏感字符串做随机加密处理。在运行时进行对字符串动态解密，这样就可以避免攻击者，通过利用工具进行静态逆向分析发现关键字符串信息，从而快速定位到应用中的业务代码。
2、指令替换：对代码中的运算表达式进行等效转换，使其在常用反编译工具中，提高破解者逆向分析门槛，有效的保护核心算法的原始逻辑。
3、部局变量名称混淆：对源代码中的变量名称进行做混淆操作，混淆后变量名称变成无任何意义的名称。这给分析者加大了分析强度。
4、符号混淆：对App应用中的类名称、函数名称进行混淆操作，增大直接用工具分析难度，让反编译逆向工具，无法直接通过类名称、函数名称进行快速定位App的核心代码。


2、可靠性需求
1、防动态调试：对App应用进行防调试保护、检测到配置防动态调试功能的类、方法、函数被IDA逆向工具进行动态调试时候，App应用进行自动退出运行操作，有利于保护App应用直接被动态调试，从而提高攻防对抗的门槛。
2、防动态注入：对App应用进行防动态注入保护，当利用zygote或ptrace技术进行App应用的注入操作时，App应用进行自动退出运行操作，以此进行防御攻击方对App应用的非法操作，避免动态分析执行代码，从而达到动态保护App应用安全。
3、HOOK检测：对App进行防HOOK保护，检测到配置防hook保护功能的类名、方法名、函数名在被frida、xposed等工具动态hook时候，App进行自动退出操作，以此进行提高防御App安全性，保护App不被注入攻击，抵御恶意侵入。
4、代码段检验：对App应用中的代码段进行完整性校验，发现代码段被篡改，App应用进行自动退出运行，防止App应用中的代码逻辑被篡改，以此进行动态保护App的源代码安全性。
5、代码段检验：对App应用中的代码段进行完整性校验，发现代码段被篡改，App应用进行自动退出运行，防止App应用中的代码逻辑被篡改，以此进行动态保护App的源代码安全性。
6、完整性校验：对App中指定的函数级进行完整性校验，当应用被重新签名和代码的完整性遭到破坏时候，检测点进行触发App程序闪退，以此抵御主流的调试器调试分析，从而达到动态保护程序安全。
1、系统设计
为了便于管理，将每个重要的需求方向确定为一个子系统，根据不同的功能需求方向，可以将软件划分为以下几个子系统。包括登录注册、后台管理、发布订单、订单管理、发布明信片、明信片管理。
用例模型的包图：
 
子系统包图：
 
2、界面设计
“HELP(嘿坡)”UI设计风格为扁平化设计风格，采用橙色作为主题色，代表着太阳的颜色，希望2020年冬天来的疫情赶快离去，真正的春天尽快来临！社区互助页面以灰橙简约两色，功能设计简单、直接化，方便老人、小孩的操作，总体保证整个界面的清晰自然。在界面的交互中注重交互的流畅处理。在社区元宇宙的页面设计中，加大对社区居民的虚拟形象的配色方案的设计，在对人物的设计中，强调虚拟形象的动态化和线条的流畅化。
 
    
     
3、数据设计
用户：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
admin	VARCHAR(16)	NOT NULL	账号
faceImg	VARCHAR(500)	NOT NULL	头像
nickName	VARCHAR(30)	NOT NULL	昵称
num	INT	NOT NULL	用户id
password	VARCHAR(30)	NOT NULL	密码

订单：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
amount	INT	NOT NULL	定金
detail	VARCHAR(200)	NULL	详细描述
gmgoods	VARCHAR(50)	NOT NULL	代购的物品
latitude	FLOAT	NOT NULL	经度
longitude	FLOAT	NOT NULL	纬度
name	VARCHAR(20)	NOT NULL	姓名
phone	INT	NOT NULL	电话
place	VARCHAR(100)	NOT NULL	购买地点
service	VARCHAR(8)	NOT NULL	服务类型
time	DATETIME	NOT NULL	截止时间
type	VARCHAR(8)	NOT NULL	订单类型
取消订单：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
record	VARCHAR(32)	NOT NULL	订单id
userId	INT	NOT NULL	取消订单的用户id
完成订单：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
record	VARCHAR(32)	NOT NULL	订单id
userId	INT	NOT NULL	完成订单的用户id

历史订单：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
record	VARCHAR(32)	NOT NULL	订单id
userId	INT	NOT NULL	发布/接取订单的用户id

明信片：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
birthday	DATE	NOT NULL	生日
interest	VARCHAR(30)	NULL	兴趣
introduction	VARCHAR(100)	NULL	自我介绍
ownerId	INT	NOT NULL	明信片拥有者的用户id
preference	VARCHAR(20)	NOT NULL	推送偏好
profilePhoto	VARCHAR(500)	NOT NULL	头像
school	VARCHAR(30)	NOT NULL	学院
sex	VARCHAR(2)	NOT NULL	性别
wxnum	VARCHAR(30)	NOT NULL	微信号
点赞记录：
字段名	数据类型	是否为空	说明
id	VARCHAR(32)	NOT NULL	记录唯一标识
likeOwnerId	INT	NOT NULL	点赞者的用户id
photoOwnerId	INT	NOT NULL	被点赞明信片ownerId


4、对象设计
详细的类图
类	服务
BaseUser:系统角色的基类	loginCheck:用于用户登录验证
Form:订单类	formAdd():新增用户订单
formDel():取消用户订单
formAccomplish():已完成用户订单
formComing():待完成用户订单
User类：用户信息类	
userAdd():新增用户信息
userDel():删除用户信息
userModify():修改用户信息
Album：相册类	albumAdd():新增图片
albumDel():删除图片
albumlike():喜欢图片
albumnoulike():不喜欢图片
albumModify():修改用户信息
Historyform：历史订单类	historyAdd():新增历史订单
Administrator:管理员类	formDel():删除用户订单
albumDel():删除用户图片
userDel():注销用户
arrange():管理订单
 
 
顺序图
 

5、其他
1、开发环境设计
(1)硬件和操作系统
处理器：AMD Ryzen 7 4800H with Radeon Graphics
内存：16.0 GB
磁盘：PC SN530 NVMe SSD 512G
操作系统：Windows 11 家庭中文版
(2)开发工具
微信开发者工具
(3)	数据库
微信小程序云数据库

  2.软件工具：
      微信小程序开发工具（1.06.2210310 Windows 64） 
•	在 iOS、iPadOS 和 Mac OS 上，小程序逻辑层的 JavaScript 代码运行在 JavaScriptCore 中，视图层是由 WKWebView 来渲染的，环境有 iOS 14、iPad OS 14、Mac OS 11.4 等；
•	在 Android 上，小程序逻辑层的 JavaScript 代码运行在 V8 中，视图层是由基于 Mobile Chromium 内核的微信自研 XWeb 引擎来渲染的；
•	在 Windows 上，小程序逻辑层 JavaScript 和视图层都是用 Chromium 内核；
•	在 开发工具上，小程序逻辑层的 JavaScript 代码是运行在 NW.js 中，视图层是由 Chromium Webview 来渲染的。

结构	微信小程序
结构	WXML
样式	WXSS
逻辑	Javascript
配置	JSON

 



 
 

3.数据库
 微信小程序云数据库
打开控制台，选择 "数据库" 标签页，通过 "添加集合" 入口创建一个集合。假设我们要创建一个待办事项小程序，我们创建一个名为 todos 的集合。创建成功后，可以看到 todos 集合管理界面，界面中我们可以添加记录、查找记录、管理索引和管理权限。
 

6、架构设计
（1）小程序主要模块构成
小程序自身分为两个主要部分独立运行：view 模块和 service 模块。在开发者工具中，它们独立运行于不同的 webivew tag 中。
view 模块负责前端界面显示，它由 wxml 和 wxss 转换后代码以及微信提供相关辅助模块组成。 一个 view 模块对应一个 页面, 小程序支持同时多个 view 存在。
service 模块负责后台逻辑，它由 js 代码以及微信提供的相关辅助模块组成。 一个应用只有一个 service 进程，它同样也是一个页面。它在程序生命周期内后台运行，service 模块通过与 view 模块实现不同但接口格式一样的微信JSBridge 对象跟后台通信。
（2）动态模型
    
3，包图
 
4，场景示意图
 


