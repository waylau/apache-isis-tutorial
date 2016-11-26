# 介绍

Apache Isis™ 是用于在 Java 中快速开发领域驱动（domain-driven）应用程序的框架。只需在实体、领域服务或视图模型中编写业务逻辑，该框架会将该领域模型的表示动态生成为 webapp 或丰富的超媒体 REST API。

官方主页为：http://isis.apache.org/


## Apache Isis 简介

Apache Isis 快速开发领域驱动（domain-driven）应用程序的框架，具有以下特点：

* Apache Isis 可以从底层领域对象（domain object）直接动态构建通用 UI 和丰富的超媒体 REST API。这使得该框架非常适用于具备快速原型、短反馈周期的敏捷开发。UI也可以根据特定用例进行扩展，并可以使用 [Bootstrap](http://getbootstrap.com/) 主题。
* Apache Isis 应用程序的核心是领域对象（domain object），即持久实体（persisted entities）或视图模型（view models）。 业务规则可以直接与领域对象相关联，或者可以被分解为单独的服务。Apache Isis 在所有地方都执行了依赖注入（dependency injection）以确保应用程序是解耦的。
* 同时，Apache Isis 还拥有大量的在 Github 托管的附加模块，用于安全、审计、命令分析，邮件合并和其他横切所关注的业务。它还有一些其他的 UI 扩展，包括地图、日历等。所有都是这些都是开源的，可以开箱即用，或按照需要进行 fork 代码。详情可以见 http://www.isisaddons.org/ 。