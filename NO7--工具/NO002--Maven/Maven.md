Maven是用于Java软件项目的强大构建工具。实际上，您也可以使用其他语言来构建软件项目，但是Maven是用Java开发的，因此，从历史上看，Maven被更多地用于Java项目。

Maven围绕着POM文件（项目对象模型）的概念。POM文件是项目资源（如源代码，测试代码，依赖项（使用的外部JAR）等）的XML表示。POM包含对所有这些资源的引用。POM文件应位于其所属项目的根目录中。

[参考](http://tutorials.jenkov.com/maven/maven-tutorial.html)

# Maven生命周期

|  Phase |  Handles | Description  |
|---|---|---|
| prepare-resources  |准备资源   | 在此阶段可以自定义资源复制。   |
| validate  |验证   | 验证项目是否正确以及所有必要的信息是否可用。   |
| compile  |编译   | 源代码编译在此阶段完成。   |
| Test  |测试   | 测试适合于测试框架的已编译源代码。   |
| package  |包   | 此阶段将创建POM.xml中的包中提到的JAR / WAR包。   |
| install  |安装   | 此阶段将软件包安装在本地/远程Maven存储库中。   |
| Deploy  |部署   | 将最终软件包复制到远程存储库。   |

