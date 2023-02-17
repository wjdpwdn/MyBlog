# 나의 리엑트 기초를 책임진다! 기초부터 다지기위한 첫번째 프로젝트
## react 왜쓸까?
> 1. HTML,CSS로 페이지 단위로 개발을 했다면 컴포넌트 단위로 개발이 가능하다.

컴포넌트 단위의 개발은 다음의 장점을 가진다.
1. 독립성 : 기능작동에 집중하여 개발
2. 재사용성 : 유지보수하기 좋고 유닛 테스트 하기 좋다.

> 2. react는 HTML,CSS,JS를 하나의 파일에 명시적으로 작성가능하도록 JSX를 활용한 선언형 프로그래밍을 지향한다.

> 3. 프레임 워크는 생태계에 종속하기 때문에, 기존 프로젝트에 유연하게 사용 가능하다.

> 4. 네이티브로 모바일 개발도 가능하다.

## JSX 정의와 규칙

* JSX는 React에서 UI를 구성할때 쓰는 문법 (JS를 확장한 문법)
* JSX ▶︎ Babel(컴파일) ▶︎ JS ▶︎ Browser
* DOM(HTML,CSS,JS) 🤜 🤛 ReactDOM(CSS,JSX)
  * DOM과는 다르게, JSX를 활용한 ReactDOM은 html에서 입력하는것처럼 엘리먼트 입력이 쉽다.
* JSX 규칙
  1. 최상위에서 opening tag와 closing tag로 감싸주어야 한다.
  2. 엘리먼트 클래스 사용시, className 으로 표기
  3. JS표현식 사용시, 중괄호 이용
  4. 컴포넌트 선언시 ParscalCase 로
  5. 조건부 렌더링에는 삼항연산자 사용
  6. 여러개의 HTML 엘리먼트를 표시할때 map()함수를 이용

## map을 이용한 반복
반복적으로 입력하는 엘리먼트를 고차함수 map의 특성을 이용하여 쉽게 입력 가능하다.
map함수를 사용할 경우 opening tag에 key 값을 설정해주어 element에 안정적인 고유성을 부여한다.
```javascript
function Blog() {
  const blogs = posts.map((post) => (
    <div key={post.id}> // key 값이 없으면 오류가 난다.
      <h3>{post.title}</h3>
      <p>{post.content}</p>
    </div>
  ));
  return <div className="post-wrapper">{blogs}</div>;
}
```
