# HTTP 헤더를 알아보자

<img width="243" alt="스크린샷 2023-12-28 오후 2 19 17" src="https://github.com/dev-hamster/TIL/assets/123740296/b2a7f614-4ff7-452a-9797-47b7c43685ee">

### GET
특정한 리소스를 가져오는 요청 메소드이다.

### HOST
서버의 도메인명과 서버가 리스닝하는 부가적인 TCP 포트를 특정한다.

### Connection
현재의 전송이 완료된 후, 네트워크의 접속을 유지할지 말지를 제어한다. 

keep-alive값은 연결은 지속되고 끊기지 않으며, 동일한 서버에 대한 후속 요청을 수행할 수 있다. 즉 하나의 TCP 연결로 여러개의 HTTP request/response를 주고받을 수 있다. HTTP/1.0+ 부터 지원한다.

### Pragma

Cache-Control 헤더가 생기기 전에 사용한 헤더이다. 

no-cache는 캐시가 캐시 복사본을 릴리즈 하기전에 원격 서버로 요청을 날려 유효성 검사를 강제한다.

### Cache-Control

요청과 응답 내의 캐싱 메커니즘을 위한 디렉티브를 정하기 위해 사용한다. 

Client가 이전에 받은 데이터와 새로 요청한 데이터가 같은 경우 Cache-Control을 사용해 Server는 부하를 줄일 수 있고, Client는 네트워크를 거치는 시간을 아낄 수 있다. 

`no-cache`는 캐시된 복사본을 사용자에게 보여주기 이전에, 재검증을 위한 요청을 원 서버로 보내도록 강제한다.


### Upgrade-Insecure-Request

HTTPS:1과 동일한 표현, HTTP 메시지 전송시 보안을 적용한다.


### User-Agent

사용자의 웹 브라우저 종류나 기타 클라이언트의 소프트웨어 정보를 보여준다.

### Accept

웹 브라우저가 처리할 수 있는 MIME 타입으로 표현되는 데이터 타입을 의미한다. text/html은 text, html 형태의 문서를 처리할 수 있다는 뜻이다. 서버는 Content-Type 응답 헤더로 클라이언트에게 선택된 타입을 알려준다. 

### Accept-Encoding

여러 압축 알고리즘을 통해 리소스를 주고 받는다. 클라이언트는 서버에게 사용할 압축 알고리즘을 명시한다.
압축 알고리즘은 gzip, deflate, br이 있다.

<details>
  <summary>
  MIME 타입이란?
  </summary>
  
  - 미디어 타입 (Multipurpose Internet Mail Extensions 또는 MIME type로도 알려져 있음)는 문서, 파일 또는 바이트 집합의 성격과 형식을 나타낸다. 
  
  - MIME 타입은 IETF의 RFC 6838에 정의 및 표준화되어 있다.
  
  - 브라우저는 '파일 확장자가 아닌' MIME 타입을 사용하여 URL 처리 방법을 결정하므로 웹 서버가 응답의 Content-Type 헤더에 올바른 MIME 타입을 보내야 한다.
</details>

### Accept-Language
전송할 수 있는 언어(자연 언어)의 종류이다.


---
참조
- [https://www.blog-dreamus.com/post/cache-control-%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0](https://www.blog-dreamus.com/post/cache-control-%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0)
- MDN
