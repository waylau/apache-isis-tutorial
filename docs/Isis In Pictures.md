# 什么是 Apache Isis

在本章节，我们要向您展示现代 Apache Isis 应用程序的外观。以应用截图的方式，让您可以更好、更快的熟悉 Apache Isis。

下面的截图取自 Isis Addons 的 [todoapp](http://github.com/isisaddons/isis-app-todoapp) 示例（非 ASF 项目），您可以随意 fork 和使用。您也可以在https://github.com/isisaddons/isis-app-todoapp/tree/master/dom/src/main/java/todoapp/dom/todoitem 找到构建此 UI 的相应领域类（domain classes）。

todoapp 还与许多其他 [Isis Addons](http://www.isisaddons.org/) 模块进行了集成。考虑到大多数应用最终都会使用一个或多个这些插件，所以在本章节内容中，也会包括那些插件的截图。

## 基本操作

下面展示下该 todoapp 应用的基本操作。

### 登录

Apache Isis 与 Apache Shiro 进行了集成。Apache Shiro 框架支持基于文件的realms，同时 Isis Addons 安全模块（非 ASF 项目）针对从 Apache Isis 元模型（metamodel）派生的用户、角色和权限的子领域（subdomain）提供了很好的功能。todoapp 示例展示了与安全模块的集成。

![登录](/images/Isis In Pictures/010-login.png)

### 安装 Fixture

Apache Isis 有很多功能可以帮助您快速建立原型，然后会完全测试您的应用程序。 其中一个例子是使用 fixture 脚本，它允许在运行的应用程序中安装预先封装的数据。这是这个非常好的作为识别新故事的起点的工具; 稍后在实现该功能时，相同的 fixture 脚本可以在该功能的集成测试中重新使用（有关测试的内容稍后会讲到）。

![安装 Fixture](/images/Isis In Pictures/020-install-fixtures.png)


### 仪表盘和视图模型

大多数时候，最终用户会与持久性领域域实体（persistent domain entity）的表示进行交互，但 Apache Isis 还支持可以聚合来自多个数据源的视图模型（view model）。todoapp 示例使用“仪表盘”视图模型列出尚未完成的待完成项与已完成项。

![仪表盘和视图模型](/images/Isis In Pictures/030-dashboard-view-model.png)


### 领域实体

下面的截图是 todoapp 的 `ToDoItem` 领域实体（domain entity）。 像所有网页一样，这个 UI 是在运行时生成的，直接来自领域对象（domain object）本身。没有用到控制器或这编写 HTML。

![仪表盘和视图模型](/images/Isis In Pictures/040-domain-entity.png)

除了领域实体之外，Apache Isis 还允许提供布局元数据（metadata）提示，例如指定属性分组，将这些组定位到列中，将动作（按钮）与属性或集合关联，将图标置于按钮上，等等。这些元数据可以指定为注解或 JSON 形式; 后者的好处是它可以随时更新（和重绘 UI），而无需重新启动应用程序。

任何具有产品级别的应用程序都将需要这些元数据，但是（像上面讨论的视图模型一样）这些元数据可以逐渐添加到核心领域模型之上。

### 编辑属性

默认情况下，领域实体（domain entity）上的属性是可编辑的，意味着它们可以直接更改。 在 todoapp 示例中，`ToDoItem`的描述就是一个这样的可编辑属性：

![编辑属性](/images/Isis In Pictures/050-edit-property.png)

注意，即使在编辑模式下，某些属性是只读的; 个别属性可以是不可编辑的。您也可以禁用所有属性，强制其仅能通过动作（action）来更改（如下所示）。

### 动作

修改实体的另一种方法是调用动作（action）。 在下面的屏幕截图中，`ToDoItem`的类别和子类别可以使用动作一起更新：

![动作](/images/Isis In Pictures/060-invoke-action.png)

对于动作来说，它可以做什么是没有限制的。它可能只是更新单个对象，它可以更新多个对象。或者，它可能不会更新任何对象，但可以改为执行一些其他活动，如发送电子邮件或打印文档。

一般来说，所有动作都与某个对象相关联，并且（至少最初）也由该对象实现，这符合良好的老式封装。 我们有时对这样的领域对象（domain object）使用术语“behaviourally complete（行为完全）”。


### Mixin

作为在领域对象（domain object）上放置动作（业务逻辑）的替代方法，它可以放在 mixin 对象中。 当一个对象由 Apache Isis 渲染时，mixin 将其行为“贡献”到领域对象上（类似于面向切面的特点）。

在下面的截图中，突出显示的“export as xml”动作，“relative priority”属性（以及“previous”和“next”动作），“similar to”集合和两个“as DTO”动作，都是由 mixin 贡献的。

![Mixin](/images/Isis In Pictures/065-contributions.png)

## 可扩展视图

Apache Isis 查看器是使用 [Apache Wicket](http://wicket.apache.org/) 实现的，并且被设计为是可扩展的。例如，当呈现对象集合时，这只是几个视图中的一个，如选择器下拉列表中所示：

![可扩展视图](/images/Isis In Pictures/070-pluggable-views.png)


[Isis Addons](http://isisaddons.org/) 库（非 ASF 项目）提供了很多类似的扩展。比如 [gmap3](https://github.com/isisaddons/isis-wicket-gmap3) 组件将呈现实现 `Locatable` 接口的任何领域实体（例如`ToDoItem`）：

![gmap3](/images/Isis In Pictures/080-gmap3-view.png)

类似地，Isis Addons 的 [fullcalendar2](http://isis.apache.org/images//isis-in-pictures/090-fullcalendar2-view.png) 组件（非 ASF 项目）将呈现实现了 `Calendarable` 接口的任何领域实体（例如`ToDoItem`）：

![fullcalendar2](/images/Isis In Pictures/090-fullcalendar2-view.png)

另一个“查看器”是由 Isis Addons excel 组件（非 ASF 项目）提供的。该组件提供了作为电子表格的下载按钮：

![excel-view](/images/Isis In Pictures/100-excel-view-and-docx.png)


上面的屏幕截图还显示了“export to Word”操作。 这不是一个查看器，而是一个动作，使用 Isis Addons [docx](https://github.com/isisaddons/isis-module-docx) 模块（非 ASF 项目）来执行“邮件合并”：

![)](/images/Isis In Pictures/110-docx.png)

注意： Isis Addons 不属于 ASF 项目，但都采用了 Apache License 2.0 协议。

## 安全、审计等

## REST API
## 集成测试支持
## 内部事件总线