# MiniServletApi

MiniSpring 学习栈共用的 Servlet / HTTP 契约层。

英文版：[README.md](README.md)

**仓库：** [https://github.com/HooYeecea/MiniServletAPI](https://github.com/HooYeecea/MiniServletAPI)

## 为什么要单独抽模块

`MiniTomcat`（BIO）和 `MiniTomcatNIO` 是两套不同的连接器 / 容器实现。
`MiniMVC` 不该关心运行时具体用哪一个。

本模块只放**面向应用的 API**：

- `Servlet`、`Filter`、`FilterChain`
- `HttpRequest`、`HttpResponse`
- `ServletConfig`、`RequestDispatcher`、`HttpSession`、`DispatcherType`

包名：`com.minispring.web`  
Maven 坐标：`com.minitomcat:mini-servlet-api`

具体实现留在各自服务器工程里。MVC 和应用代码只依赖本 API。

## 谁在用

| 项目 | 角色 | 仓库 |
|------|------|------|
| [MiniTomcat](https://github.com/HooYeecea/MiniTomcat) | BIO 迷你 HTTP 服务器，实现本 API | `HooYeecea/MiniTomcat` |
| [MiniTomcatNIO](https://github.com/HooYeecea/MiniTomcatNIO) | NIO 迷你 Tomcat，实现本 API | `HooYeecea/MiniTomcatNIO` |
| MiniMVC | 后续 SpringMVC 风格层；只依赖本 API，不绑死某个 Tomcat | （本地 / 待建仓） |

## 构建

```bash
mvn clean install
```

父工程 `mini-spring` 下的其它模块可依赖：

```xml
<dependency>
    <groupId>com.minitomcat</groupId>
    <artifactId>mini-servlet-api</artifactId>
    <version>1.0-SNAPSHOT</version>
</dependency>
```

## 目录结构

```text
com.minispring.web
├── Servlet
├── Filter
├── FilterChain
├── HttpRequest
├── HttpResponse
├── ServletConfig
├── RequestDispatcher
├── HttpSession
└── DispatcherType
```

## License

个人练习项目，用于学习 Spring / Tomcat 风格分层。
