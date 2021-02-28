# ajaxStudy
Ajax Study 

## 개념

Ajax(Asynchronous Javascript And XML)

Ajax란 JavaScript 라이브러리 중 하나이며 비동기식 자바스크립트와 xml의 약자이다. 브라우저가 가지고 있는 XmlHttpRequest 객체를 이용해서 전체 페이지를
새로고침 하지 않고도 페이지의 일부만을 위한 데이터를 로드하는 기법이며 자바스크립트를 사용한 비동기 통신, 클라이언트와 서버 간에 XML 데이터를 주고받는 기술이다.

요약 : 자바스크립트를 통해서 서버에 데이터를 요청하는 것

비동기 방식의 장점 : 페이지 리로드를 할 경우 전체 리소스를 다시 불러와야하는데 이때 이미지, 스크립트, 코드 등을 모두 재요청하면 불필요한 리소스 낭비가 발생하게 된다.
하지만 비동기 방식을 이용하면 **필요한 부분만 불러와 사용할 수 있으므로** 매우 큰 장점이 있다.

---

## fetch

then 안에 들어있는 function은 익명 함수

``` javascript
    fetch('css').then(function(response)
    {
        response.text().then(function(text)
        {
            alert(text);
        })
    })

```
css란 파일 안에 있는 데이터를 서버를 통해 가져오는데 가져온 데이터는 text 변수에 저장되며 alter(text); 가 있는 부분에 있는 코드를 실행시킬 수 있다.

Client - Server는 통신을 함. `fetch('url')`을 입력하면 url이란 파일을 서버에게 요청함.

`.then()`은 fetch 뒤에 사용시 fetch 요청이 끝나면 then 안에 있는 함수를 실행시키도록 약속되어 있음.

then 안에 함수는 웹브라우저 응답이 끝나면 그제서야 실행됨. 요청이 끝나고서야 코드가 실행됨. 즉 절차적으로 밑에 있는 코드보다 나중에 실행된다.

병렬적으로 실행 = Asynchronous 비동기적

절차적으로 실행 = Synchronous 동기적

익명 함수
``` javascript
    function callbackme()
    {
        console.log('response end');
    }

    callbackme = function()
    {
        console.log('response end');
    }
```
위 두 코드는 서로 문법적으로 같음.

fetch의 구체적 탐구
1. then과 함께 익명 함수로 호출
2. 함수에 입력 값으로 response 객체를 주면서 실행시킴.
3. response 객체는 다양한 값들을 받음. body, bodyUsed, headers, status 등등

---

## Init page setting

html 태그에 있는 특정 아이디 값을 `URL#아이디명`으로 입력하면 스크롤이 특정 태그가 있는 곳으로 향한다. 이를 fragment identifier(부분 식별자)라고 부름.

`location.hash` : 자바스크립트에서 현재 URL의 해쉬값을 반환해줌.
ex) aaa.html#hihi -> console.log(location.hash) 하면 콘솔값으로 #hihi 출력됨.

`substr()` : 문자열 일부만 가져와주는 함수.

`split()` : 원하는 문자열 기준으로 나눠주는 함수.

`trim()` : 공백을 없애주는 함수.

## etc

response 객체에서 status 값에 200은 정상적인 실행, 404는 파일을 찾을 수 없다는 것. 400은 잘못된 요청. 500은 서버 오류. [HTTP 상태 코드](https://developer.mozilla.org/ko/docs/Web/HTTP/Status)


최근엔 hash bang 기술 대신 pjax라는 기술을 쓴다.

---