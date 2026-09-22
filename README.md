# MiniServletApi

Shared Servlet / HTTP contracts for the MiniSpring learning stack.

Chinese version: [README(CN).md](README(CN).md)

**Repository:** [https://github.com/HooYeecea/MiniServletAPI](https://github.com/HooYeecea/MiniServletAPI)

## Why this module exists

`MiniTomcat` (BIO) and `MiniTomcatNIO` are two different connectors / containers.
`MiniMVC` should not care which one is used at runtime.

This module holds only the **application-facing API**:

- `Servlet`, `Filter`, `FilterChain`
- `HttpRequest`, `HttpResponse`
- `ServletConfig`, `RequestDispatcher`, `HttpSession`, `DispatcherType`

Package: `com.minispring.web`  
Maven artifact: `com.minitomcat:mini-servlet-api`

Implementations stay in each server project. MVC and app code depend on this API only.

## Consumers

| Project | Role | Repository |
|---------|------|------------|
| [MiniTomcat](https://github.com/HooYeecea/MiniTomcat) | BIO mini HTTP server; implements the API | `HooYeecea/MiniTomcat` |
| [MiniTomcatNIO](https://github.com/HooYeecea/MiniTomcatNIO) | NIO mini Tomcat; implements the API | `HooYeecea/MiniTomcatNIO` |
| MiniMVC | Future SpringMVC-style layer; depends on the API, not a specific Tomcat | (local / upcoming) |

## Build

```bash
mvn clean install
```

Other modules in the parent `mini-spring` reactor can then depend on:

```xml
<dependency>
    <groupId>com.minitomcat</groupId>
    <artifactId>mini-servlet-api</artifactId>
    <version>1.0-SNAPSHOT</version>
</dependency>
```

## Layout

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

Personal practice project for learning Spring / Tomcat-style layering.
