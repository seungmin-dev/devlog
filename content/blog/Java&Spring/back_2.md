---
title: 🔌Web Server와 WAS의 차이
date: 2020-09-03 17:15:80
category: Java&Spring
draft: false
---

## Web Server와 WAS의 차이

- `Web Server` -
  - HTTP 프로토콜을 기반으로 하여 클라이언트(웹 브라우저 또는 웹 크롤러)의 요청을 서비스
  - ex) Apache Server, Nginx, IIS 등
- `WAS(Web Application Server)` - - DB 조회나 다양한 로직 처리를 요구하는 동적인 컨텐츠를 제공하기 위해 만들어진 Application Server
  - HTTP를 통해 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어(소프트웨어 엔진) - **웹 컨테이너** 혹은 **서블릿 컨테이너**라고도 불림 >Container : JSP, Servelt을 실행시킬 수 있는 소프트웨어
    > = WAS는 JSP, Servlet 구동환경을 제공
  - WAS = Web Server + Web Container - Tomcat, JBoss, Jeus, Web Sphere 등
