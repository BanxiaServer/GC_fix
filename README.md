- 这是我们半夏公益服使用的部分核心文件

- 这个仓库存在的目的只有一个——优化玩家在获得大量物品时服务器的cpu占用率

- 原版gc在玩家使用 /give all 指令时会将cpu占满 且还会持续几秒到十几秒的高占用率

- 现在使用此仓库的核心 玩家在使用 /give all 指令时只会占用不到百分之五的cpu

- [创建这个仓库的原因](https://github.com/Grasscutters/Grasscutter/issues/2458)

- 本仓库使用的所有代码均来自官方核心 我只是对部分代码进行了取舍以修复hyper分支的注册问题+玩家重进游戏不储存背包物品和dev分支的高cpu占用问题

- 可以点击[这里](https://github.com/BanxiaServer/Grasscutter/actions/workflows/build.yml)下载自动编译的核心
- 如果开一段时间后就崩服 且控制台输入什么都没有反应 则代表着默认分配的内存已被消耗完 可以将启动代码改为`java -Xms初始分配的内存g -Xmx分配最大内存g -jar 核心名字.jar` 来增加分配给gc使用的内存 内存泄露是原版gc就存在的问题 我无法修复



---

### 快速开始（全自动）

- 获取Java 17：https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
- 获取[MongoDB社区版](https://www.mongodb.com/try/download/community)
- 获取游戏4.0正式版 (如果你没有4.0的客户端，可以在这里找到）：https://github.com/MAnggiarMustofa/GI-Download-Library/blob/main/GenshinImpact/Client/4.0.0.md)

- 下载[最新的Cultivation版本](https://github.com/Grasscutters/Cultivation/releases/latest)（使用以“.msi”为后缀的安装包）。
- 以管理员身份打开Cultivation，按右上角的下载按钮。
- 点击“下载 Grasscutter 一体化”
- 点击右上角的齿轮
- 将游戏安装路径设置为你游戏所在的位置。
- 将自定义Java路径设置为`C:\Program Files\Java\jdk-17\bin\java.exe`
- 保持所有其它设置为默认值

- 点击“启动”按钮旁边的小按钮。
- 点击“启动”按钮。
- 随便想一个用户名登录，不需要密码。

### 构建

Grasscutter使用Gradle来处理依赖和构建。

**前置：**

- [Java SE Development Kits - 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)或更高版本
- [Git](https://git-scm.com/downloads)

##### Windows

```shell
git clone --recurse-submodules https://github.com/Grasscutters/Grasscutter.git
cd Grasscutter
.\gradlew.bat # 设置开发环境
.\gradlew jar # 编译
```

##### Linux（GNU）

```bash
git clone --recurse-submodules https://github.com/Grasscutters/Grasscutter.git
cd Grasscutter
chmod +x gradlew
./gradlew jar # 编译
```

你可以在项目的根目录找到输出的jar。

