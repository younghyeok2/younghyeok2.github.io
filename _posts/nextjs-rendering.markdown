- [Rendering](#rendering)
- [NextJs Rendering Method](#nextjs-rendering-method)
- [Pre-Rendering vs Client-Side Rendering](#pre-rendering-vs-client-side-rendering)
- [SSG in NextJs](#ssg-in-nextjs)
- [SSR in NextJs](#ssr-in-nextjs)
- [CSR in NextJs](#csr-in-nextjs)

## Rendering

React / NextJs 에서 렌더링은 React로 작성한 코드를 HTML 표현으로 바꾸는 작업을 의미한다.

```javascript
import React from "react";
import ReactDOM from "react-dom/client";

function Hello(props) {
  return <h1>Hello World</h1>;
}

ReactDOM.render(<Hello />, document.getElementById("root"));
```

위 javascript code는 아래 html 으로 변환된다.

```html
<html>
  <head></head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```

해당 HTML은 브라우저 렌더링 과정(HTML과 CSS 파일을 렌더링하는 작업)을 통해 아래와 같은 화면으로 그려진다.

![Hello World](data:image/png;base64,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)

## NextJs Rendering Method

NextJs에서는 SSG, SSR, CSR 의 세가지 렌더링 방법을 이용할 수 있다.

- SSG(Static Site Generation)
- SSR(Server-Side Rendering)
- CSR(Client-Side Rendering)

NextJs의 장점은 페이지별로 적합한 렌더링 기법을 선택할 수 있다는 것이다.

## Pre-Rendering vs Client-Side Rendering

Pre-rendering은 말그대로 HTML 이 미리 서버에서 생성되서 client에 전달됨을 의미한다.
SSG와 SSR 은 HTML이 미리 서버에서 생성되서 client에게 전달되기 때문에 Pre-rendering으로 분류된다.

![pre-rendering](https://nextjs.org/static/images/learn/foundations/pre-rendering.png)

Client Side Rendering은 브라우저가 빈 html 을 전송받고, 자바스크립트 명령이 실행되면서 HTML을 렌더링하는 작업이 client(user device)에서 일어난다. 렌더링이 일어나는 동안 사용자는 빈 화면을 보게 된다.

NextJs 문서에서는 이런 방식으로 동작하는 앱을 fully client side rendered app 으로 표현하고 있다. NextJs에서 지원하는 client side rendering 은 fully client side rendered app을 의미하지 않는다. client side rendering 부분에서 다시 설명하도록 하겠다.

![csr](https://nextjs.org/static/images/learn/foundations/client-side-rendering.png)

## SSG in NextJs

Static Site Generation의 경우, 빌드 시점에 정적 파일이 생성된다. request 마다 HTML 파일 생성되는 Server Side Rendering 과는 다른 부분이다.

해당 정적 파일들은 CDN에 배포될 수 있고, 배포 이후에는 서버없이 동작할 수 있다.

https://nextjs.org/docs/basic-features/data-fetching/get-static-props

## SSR in NextJs

Server Side Rendering의 경우, HTML 파일이 client 의 request 별로 생성된다. non-interactive 한 HTML이 화면에 보여지는 동안, JSON 파일과 javascript 명령을 통해 페이지가 interactive 하게 하는 과정을 진행한다.

위의 Pre-rendering 과정을 설명하는 이미지에서 Like 버튼이 hyration 과정 진행 후, 활성화 됨을 볼 수 있다.

https://nextjs.org/docs/basic-features/data-fetching/get-server-side-props


## CSR in NextJs

NextJs에서 Client Side Rendering을 client Side data fetching으로 표현하고 있다. 

page level에서만 이루어지는 Pre-rendering 과는 다르게 component level에서도 이루어 질 수있다.

결국 NextJs에서 말하는 CSR은 client에서 javascript를 통해 HTML을 렌더링하는 것을 의미한다. 아까 언급했던 fully client side rendered 보다 더 포괄적인 개념으로 봐라보아야 한다.

client Side data fetching 은 화면이 그려진 후, 데이터가 변경되었을 때 화면이 javascript 통해 업데이트 됨을 의미한다.

https://nextjs.org/docs/basic-features/data-fetching/client-side

---

출처: https://nextjs.org/learn/foundations/how-nextjs-works/rendering
