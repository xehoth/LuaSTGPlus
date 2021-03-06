# luaSTG+

luaSTGPlus项目致力于发展luastg的后续可维护版本。

本项目以**LuaSTG.2012.8源代码(by 隔壁的桌子)**为基准，在保证**大多数功能兼容**的前提下重写luaSTG底层框架，以优化完善过去老的代码、适应新的游戏开发要求为目标。

## API文档

请查阅`APIManual`以获得更多帮助。

## luaSTG代码迁移

请查阅`luastg迁移向导`以获得更多帮助。

## 更新记录

### 0.2.2.0

- 增加对RenderTarget的操作
- 修正判定模型为严格判定模型
	- 若`rect=false`，则视为半径`(a+b)/2`的圆形
	- 若`rect=true`，则视为半边长为`a`和`b`的矩形
- 在dev版本中可以用`F8`开启碰撞盒显示功能

### 0.1.9.1

- Execute中允许隐藏窗口

### 0.1.9

- lfs增加接口用以删除文件

### 0.1.8.6

- RenderTTF增加缺失接口

### 0.1.8.5

- 修正RemoveResource的bug（感谢白丝丽丽反馈）

### 0.1.8.4

- 修正资源包解密不可用的问题（感谢电台同学反馈）

### 0.1.8.3

- splash窗口强制置顶

### 0.1.8.2

- 增加错误时的调用堆栈打印

### 0.1.8.1

- 增加Execute函数用于执行外部程序

### 0.1.8

- 修正ChangeVideoMode没有返回值的bug（感谢电台同学发现bug）
- 去掉了多余的坐标修正

### 0.1.7.2

- 将载入窗口的背景设为透明
- 去除窗口失焦后的自动静音

### 0.1.7

- 修正fancy2d在重置effect时引发的bug
- 更正粒子系统&资源系统的兼容性
- 移除曲线激光、粒子发射器的对象数量限制
- 添加手柄支持

### 0.1.6

- 加快加载速度
- 增加性能监视功能
- 修正混合模式的BUG和文档的BUG
- 增加鼠标功能

### 0.1.5

- 增加了缺失的音效控制接口

### 0.1.4

- 修正fancy2d视口设置的bug
- 增加了shader/PostEffect支持

### 0.1.3

- 增加了可选的加载窗口
- 增加游戏中使用Ctrl+Enter切换全屏/窗口状态

### 0.1.2

- 修正了fancy2d在设备丢失后重置ZBuffer的BUG
- 去除了lua.dll对VC++2013运行库的依赖
- 增加了切换显示选项的API

### 0.1.1

- 修正了隐藏鼠标指针不起作用的BUG
- 增加了对音乐循环节的参数检测，防止死循环BUG

### 0.1.0

- 第一版本

## 其他

### TO DO LIST

- 反弹板
- 重启功能

## 鸣谢

隔壁的桌子、⑨要、白丝丽丽等等众人。

程序图标 by 拉布拉多

luastg交流群`230927410`

若有任何BUG或意见请反馈至1871361697@qq.com，非常感谢！

## 编译配置

1. 确保项目根目录外克隆了fancy2d，同时确保克隆了3rdParty/luajit
	
		目录结构：
			fancy2d\
				...
			luastgplus\
				3rdparty\
				...

2. 编译fancy2d

3. 在luajit目录中建立_build文件夹，并使用CMake&VS编译luajit

		mkdir _build
		cd _build
		cmake -G "Visual Studio 12" -DLUAJIT_ENABLE_LUA52COMPAT=false ..

4. 在VS中编译luastg+

		NOTE:
			Debug版本用于调试（log细节多）
			Release版本用于发布
			Release_dev版本用于发布测试版本（log细节同Debug版本）

## 许可

BSD Lisence
