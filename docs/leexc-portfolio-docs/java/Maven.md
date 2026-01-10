## Maven

管理和创建 Java 项目的工具，apache 旗下的开源项目。

`tips: apache 全球最大开源软件基金会`

### Maven 作用

- 项目构建：标准化跨平台（Linux/Mac/Windows）自动化项目构建方式。

  - 纯手工编译发布的流程
    1. 用 javac 编译 .java 源码生成 .class 文件；
    2. 再用 jar（或 jlink 等）把字节码打包成可分发的 .jar；
    3. 最后如果要发布或部署，可以再执行 scp/rsync 之类的脚本，或者调用 mvn deploy 这类 Maven 命令上传。
  - 使用 Maven 的自动化流程

    1. mvn package 执行编译、测试、打包
    2. mvn install 安装
    3. mvn deploy 发布（deploy 总是在 install 之后执行，且通常用于发布到远端仓库）
    4. 会自动在内部调用 javac、jar 等步骤
    5. 总结：Maven 是一个工具链，一条命令替你完成编译、测试、打包、发布；

  - IDEA 编辑器
    1. IntelliJ IDEA（或其他现代 Java IDE）默认会在你保存/构建时自动执行编译、测试、打包这些步骤，但它本质上是在后台调用 Maven/Gradle（或内置构建器）来完成。
    2. IDE 是在帮你封装这些命令（自动或快捷方式），但底层还是依赖像 Maven/Gradle 这样的构建工具来完成编译、测试、打包和发布流程。

- 依赖管理：方便快捷的管理项目依赖的资源（jar 包）
- 统一项目结构：提供标准、统一的项目结构

### 构建流程

编译（compile）-> 测试（test）-> 打包（package） -> 发布（deploy）

### 总结：

maven 是一款管理和构建 Java 项目的重要工具

---

### maven 的结构

- 项目对象模型（Project Object Model，POM）
- 依赖管理模型（Dependency Management Model，依赖管理模型（Dependency）
- 构建生命周期/阶段（Build Lifecycle/Phase）
  1. 基于插件，进行文件的编译、打包、测试等操作
  2. 生成临时文件，存在 target 目录下

### pom.xml 文件

Maven 项目的核心配置文件

1. POM（项目对象模型） 就是 pom.xml 文件本身，它描述了项目的元数据（比如 groupId、artifactId）和构建配置；

2. 依赖管理模型 通过 pom.xml 中的 <dependencies> 统一定义项目依赖，Maven 会在构建前自动从本地/远端仓库下载；

3. 构建生命周期/阶段（如 compile、test、package、deploy）和所需的插件也都在 pom.xml 中声明，Maven 会按配置调用相关插件（如 maven-compiler-plugin、maven-jar-plugin）去编译、打包、测试等，输出内容默认放在 target/ 目录。

pom.xml 是上述结构的入口和串联点：你写在 pom.xml 里的依赖、插件、生命周期配置决定了整个构建流程是怎么跑的。
