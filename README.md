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

## etc

---