# 什么是 Apache Isis

在本章节，我们要向您展示现代 Apache Isis 应用程序的外观。以应用截图的方式，让您可以更好、更快的熟悉 Apache Isis。

下面的截图取自 Isis Addons 的 [todoapp](http://github.com/isisaddons/isis-app-todoapp) 示例（非 ASF 项目），您可以随意 fork 和使用。您也可以在https://github.com/isisaddons/isis-app-todoapp/tree/master/dom/src/main/java/todoapp/dom/todoitem 找到构建此 UI 的相应领域类（domain classes）。

todoapp 还与许多其他 [Isis Addons](http://www.isisaddons.org/) 模块进行了集成。考虑到大多数应用最终都会使用一个或多个这些插件，所以在本章节内容中，也会包括那些插件的截图。

## 基本操作

下面展示下该 todoapp 应用的基本操作。

### 登录

Apache Isis 与 Apache Shiro 进行了集成。Apache Shiro 框架支持基于文件的realms，同时 Isis Addons 安全模块（非 ASF 项目）针对从 Apache Isis 元模型（metamodel）派生的用户、角色和权限的子领域（subdomain）提供了很好的功能。todoapp 示例展示了与安全模块的集成。

![登录](images/Isis In Pictures/010-login.png)

### 安装 Fixture

Apache Isis 有很多功能可以帮助您快速建立原型，然后会完全测试您的应用程序。 其中一个例子是使用 fixture 脚本，它允许在运行的应用程序中安装预先封装的数据。这是这个非常好的作为识别新故事的起点的工具; 稍后在实现该功能时，相同的 fixture 脚本可以在该功能的集成测试中重新使用（有关测试的内容稍后会讲到）。

![安装 Fixture](images/Isis In Pictures/020-install-fixtures.png)


### 仪表板和视图模型
### 域实体
### 编辑属性
### 操作
### 混合
## 可扩展视图
## 安全，审计等...
## REST API
## 集成测试支持
## 内部事件总线