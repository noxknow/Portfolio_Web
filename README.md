# :notebook_with_decorative_cover: Portfolio_Web

https://github.com/noxknow/Portfolio_Web/assets/122594223/45ad3710-e42d-4eba-9f39-87f45f1ee231

# 목차

- [1. 문제 해결 과정](#bookmark_tabs-문제-해결-과정) <br/>
    - [1.1 Main](#main) <br/>
        - [1.1.1 position](#position) <br/>
        - [1.1.2 애니메이션](#애니메이션) <br/>
    - [1.2 About me](#about-me) <br/>
    - [1.3 Portfolio](#Portfolio) <br/>
    - [1.4 Contact With Me](#contact-with-me) <br/>

# :bookmark_tabs: 문제 해결 과정

## Main

### position

main.css 에서 transform: translateX(-50%);를 안해주면 좌측 상단만 중앙으로 가기때문에 해줘야 한다.

```css
main button.mouse {
    background-color: transparent;
    position: absolute;
    bottom: 1rem;
    left: 50%;
    transform: translateX(-50%);
    color: white;
}
```

### 애니메이션

**`애니메이션 만들기`**

구체적으로는 upDown이라는 이름의 애니메이션을 1초 동안 ease-in-out 타이밍 함수로 반복적으로 실행하는 것을 의미한다.

upDown 애니메이션은 요소를 수직 방향으로 이동시키는 효과를 가지며, ease-in-out 타이밍 함수는 애니메이션이 처음에는 천천히 시작하고, 중간에는 빠르게 진행되다가 마지막에 다시 천천히 끝나는 효과를 가지는 타이밍 함수이다.

infinite 속성을 사용하면 애니메이션이 무한 반복된다. 따라서 이 코드는 요소를 1초 간격으로 수직 방향으로 이동시키는 애니메이션을 계속해서 실행하게 된다.

**`@keyframes`**
규칙은 CSS 애니메이션에서 사용되며, 원하는 스타일 변화를 선언하여 애니메이션을 만듭니다.

```css
main button.mouse {
    background-color: transparent;
    position: absolute;
    bottom: 1rem;
    left: 50%;
    transform: translateX(-50%);
    color: white;
    animation: upDown 1s ease-in-out infinite;
}
main h2 span::after {
    content: "";
    height: 40px;
    width: 3px;
    background-color: #fff;
    display: inline-block;
    animation: blink .7s ease-in-out infinite;
}

@keyframes blink {
    0% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}

@keyframes upDown {
    0% {
        bottom: 1rem;
    }
    50% {
        bottom: 1.5rem;
    }
    100% {
        bottom: 1rem;
    }
}
```

## About me

### media Query

media query로 창이 줄어들면 영역의 크기도 변하도록 만들 때 flex를 설정해둔 부분이 있다면 정렬할때는

```css
section .about-self {
        flex-direction: column;
        align-items: center;
    }
```

혹은 아래와 같이 한다면 정렬시킬 수 있다.

```css
section .contact-me {
        flex-wrap: wrap;
    }
```
![image](https://github.com/noxknow/Portfolio_Web/assets/122594223/ee4cf45b-e419-4e31-b9b7-b8a21a3aa301)
![image](https://github.com/noxknow/Portfolio_Web/assets/122594223/94d21b46-583a-4080-94de-91dc748cdf47)

## Portfolio

`display: flex` 대신에 `float: left` 를 쓰는 경우 그 부분의 높이값이 나오지 않는 경우가 있는데 이를 해결하기 위해서 아래와 같이 선언을 해줘야 한다.  
`display: flex` 가 가능한 경우 flex를 이용하기.

```css
section .portfolio-me::after {
	content: "";
	display: block;
	clear: both;
}
```

## Contact With Me

label의 for부분과 input태그의 id부분이 같은 이름으로 들어가게 된다면, label의 부분을 클릭할 때 input태그에 깜박이는 커서가 들어가게 된다.

![image](https://github.com/noxknow/Portfolio_Web/assets/122594223/7f67b5eb-7c63-4366-8cb8-a83478b9731f)

