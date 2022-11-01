
> REST : 웹(HTTP)의 장점을 활용한 아키텍쳐

## 1. REST(REpresentational State Transfer) 기본
- REST의 요소
	- Method
|Method|의미|Idempotent|
|--------|----|-----------|
|POST|Create|No|
|GET|Select|Yes|
|PUT|Update|Yes|
|DELETE|Delete|Yes|
>Idempotent : 한 번 수행했을 때랑, 여러 번 수행했을 때 결과가 같은지?
 
- Resource
	- `http://myweb/users`와 같은 URI
	- 모든 것을 Resource로 표현하고, 세부 Resource에는 id를 붙임
- Message
	- 메세지 포맷이 존재
		: JSON, XML과 같은 형태가 있음

```
HTTP POST, http://myweb/users/
{
	"users" : {
		"name" : "terry"
	}
}
```

- REST 특징
	- Uniform Interface
		- HTTP 표준만 맞는다면, 어떤 기술도 가능한 Interface 스타일
			ex) REST API 정의를 HTTP + JSON으로 했다면, C/Java/Python/IOS 플랫폼 등 특정 언어나 기술에 종속받지 않고 모든 플랫폼에 사용 가능한 Loosely Coupling 구조
		- 포함
			- Self-Decriptive Messages
				API 메세지만 보고 API를 이해할 수 있는 구조 -> (Resource, Method를 이용해 무슨 행위를 하는지 직관적으로 이해할 수 있음)
			- HATEOAS(Hypermedia As The Engine Of Application State)
				- Application의 상태(State)는 Hyperlink를 통해 전이돼야 함.
				- 서버는 현재 이용 가능한 다른 작업에 대한 하이퍼링크를 포함하여 응답해야 함.
			- 