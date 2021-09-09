# **CSS**

> **Cascading Style Sheet**

CSS는 웹 개발에서 실제 화면에 표시되는 색상, 크기, 폰트, 레이아웃 등의 디자인을 꾸미는 역할을 한다.

HTML이 정보를 담는다는 그 역할에 집중하게 되면서 웹을 꾸미기 위해 새롭게 개발된 언어이다.

<br/>
<br/>

# **기본 문법**
CSS의 기본적인 문법은 아래와 같다.
```css
div {
  color: red;
}
```
CSS의 기본 문법은 선택자와 선언으로 이루어지며  
여기서 선언은 속성과 속성값, 그리고 둘을 구분하는 구분자로 이루어진다.  
세미콜론 `;` 으로 선언과 선언을 구분한다.

- **선택자**  
꾸며줄 HTML 요소를 선택한다.  
위의 예시에서 `div` 에 해당.

- **선언**  
선택한 HTML 요소에 적용할 스타일을 `속성:속성값;` 형태로 작성한다.  

  해당 선택자에 대한 모든 선언을 {}로 감싸서 작성한다.

  - **속성**  
  적용할 스타일의 종류를 말한다.  
  위의 예시에서 `color` 에 해당.

  - **:**  
  속성과 속성값을 구분하는 역할을 한다.

  - **속성값**  
    스타일의 종류에 대한 값을 말한다.  
    위의 예시에서 `red`에 해당.

  - **;**  
  선언과 선언을 구분하는 역할을 한다.

<br/>
<br/>

# **선언 방식**
HTML에 CSS를 적용하는 선언 방식은 4가지가 있다.

- **내장 방식**  
  ```html
  <head>
    <style>
      div {
        color: red;
      }
    </style>
  </head>
  ```
  HTML의 `<head> </head>` 태그의 하위 태그로 `<style> </style>` 태그를 삽입하고 그 안에 CSS를 작성하는 방식.  

  HTML과 CSS, JS는 별도의 문서로 관리하는 것이 유지보수에 용이하기 때문에 권장하지는 않는다.

- **링크 방식**  
  ```html
    <link rel="stylesheet" href="./main.css">
  ```
  프로젝트 폴더 내에서 별도로 작성한 css 문서를 `<link>`를 통해 현재 HTML로 불러와서 연결하는 방식.  
  일반적인 상황에서 권장되는 방식이다.

  복수의 css 문서가 연결되어 있어도 병렬 방식으로 연결되어 모든 css 문서가 동시에 로드된다.

- **인라인 방식**
  ```html
  <div style="color: red;">
    Hello, World!
  </div>
  ```  
  HTML 문서의 요소에 직접 작성하는 방식.  
  지나치게 높은 우선순위를 갖기 때문에 일반적인 상황에서는 권장하지 않는다.

- **@import 방식**  
  ```css
  @import url("./sub.css")
  ```
  링크 방식으로 불러온 CSS 문서 내에서 다른 CSS 문서를 불러와서 직렬 연결하는 방식.  
  ( HTML <- 링크 CSS <- @import CSS )  

  직렬 방식이어서 순차적으로 css 문서가 로드된다.

<br/>
<br/>

# **선택자의 종류**

## **기본 선택자**

- **전체 선택자**  
`* {}`  
모든 요소를 선택한다.

- **태그 선택자**  
`태그명 {}`  
해당 태그를 갖는 요소를 모두 선택한다.

- **클래스 선택자**  
`.클래스명 {}`  
해당 클래스를 갖는 요소를 모두 선택한다.

- **id 선택자**  
`#아이디명 {}`  
해당 아이디를 갖는 요소를 모두 선택한다.

<br/>

## **복합 선택자**

- **일치 선택자**  
`x.y {}`  
x와 y를 동시에 만족하는 요소를 모두 선택한다.  
.x#y 등과 같이 다른 선택자를 자유롭게 사용할 수 있다.  
띄어쓰기 없이 사용한다.  

- **자식 선택자**  
`x>y {}`  
x의 자식 요소 중 y를 모두 선택한다.  
직계 자식 요소만 대상으로 한다.  

- **하위 선택자**  
`x y {}`  
x의 하위 요소 중 y를 모두 선택한다.  
직계 자식 요소를 포함한 모든 하위 요소를 대상으로 한다.

- **인접 형제 선택자**  
`x + y {}`  
x의 다음 형제 요소 y를 **하나만** 선택한다.  

- **일반 형제 선택자**  
`x ~ y {}`  
x의 다음 형제 요소 y를 모두 선택한다.

<br/>

## **가상 클래스 선택자**  

- `x:hover {}`  
요소 x가 마우스 오버 되었을 때 선택한다.  

- `x:focus {}`  
요소 x가 포커스 되었을 때 선택한다.  

- `x:active {}`  
요소 x가 클릭되는 동안 선택한다.

- `x:first-child {}`  
요소 x가 형제 요소 중 첫번째일 경우 선택한다.

- `x:last-child {}`  
요소 x가 형제 요소 중 마지막일 경우 선택한다.

- `x:nth-child(n) {}`  
요소 x가 형제 요소 중 (n)번째일 경우 선택한다.  
인자 n에 별도의 기호 없는 자연수만 입력하여 n번째를 선택하는 방법으로 많이 사용하지만 다양한 사용법이 존재한다.  

  - `3n`  
  3의 배수

  - `2n`  
  짝수  

  - `2n+1`  
  홀수

  - `n+2`  
  두번째 요소부터 선택  

  - `-n+3`  
  세번째 요소까지만 선택

  - 등등

- `x:not(y) {}`  
y가 아닌 요소 x를 모두 선택한다.

<br/>

## **가상 요소 선택자**  

- `x::before {content: ""}`  
요소 x의 내부 가장 앞에 인라인 요소를 추가하고 해당 요소를 선택한다.  

  단순히 스타일을 꾸며줄 때만 사용할 요소를 추가할 때 사용한다.  

  속성 `content: "텍스트";` 를 통해 해당 요소에 텍스트를 삽입할 수 있는데, 이는 선택 사항이 아닌 필수 사항이며, 내용이 필요 없는 경우에는 `content: "";` 로 빈 텍스트를 넣으면 된다.

- `x::after {content: "";}`  
`x::before` 와 동일하지만 내부 가장 뒤에 요소를 추가한다.

<br/>

## **속성 선택자**  

- `[x] {}`  
단일 속성(disable, checked 등) x를 포함한 요소를 모두 선택한다.

- `[x="y"] {}`  
속성 x에 대해 y값을 갖는 모든 요소를 선택한다.

<br/>
<br/>

# **상속**

상위 요소에 적용된 스타일은 하위 요소에 상속되기도 한다. 

<br/>

## **상속되는 속성**  
대부분 글자와 관련된 속성이다.

- `font-style`

- `font-weight`

- `font-size`

- `line-height`

- `font-family`

- `color`

- `text-align`

- 그 외 등등

<br/>

## **강제 상속**
상속되지 않는 스타일을 강제로 상속시킬 수 있다.  

부모 요소와 자식 요소의 스타일을 통일시킨 경우,  
 나중에 수정이 필요한 상황에서 부모 요소만 수정하고 자식 요소의 수정은 누락되는 경우를 방지할 때 사용할 수 있다.

자식 요소에 아래 속성:값을 입력하여 해당 속성에 대한 값을 부모로부터 상속 받는다.  

`속성 : inherit;`

<br/>
<br/>

# **선택자 우선순위**

같은 요소에 동일한 스타일이 중복으로 선언되었을 때 어떤 스타일을 우선으로 적용할 것인지에 대한 순위이다.  

만약 우선순위가 같을 경우 마지막에 해석된 선언이 적용된다.  

대상의 범위가 좁을수록 순위가 더 높다.

1. **!important**

2. **inline 선언**

3. **id 선택자(#)**

4. **클래스 선택자(.)**

5. **태그 선택자**

6. **전체 선택자(*)**

7. **상속**

<br/>
<br/>

# **값의 단위**
값에 사용할 수 있는 대표적인 단위는 아래와 같다.

- **px**  
픽셀 단위.

- **%**  
상대적 백분율.  
기준은 부모 요소 등으로, 상황에 따라 다르게 적용된다.

- **em**  
현재 요소의 글꼴 크기의 배수.  
현재 요소의 글꼴이 12px일 때, 요소의 너비를 2em으로 지정할 경우 24px이 된다.

- **rem**  
현재 요소가 아닌 최상위 요소(HTML)의 글꼴 크기를 기준으로 한다.

- **vw**  
뷰포트 가로 너비의 백분율.  
뷰포트의 크기가 변하면 너비도 그에 맞춰 변한다.

- **vh** 
뷰포트 세로 너비의 백분율.  
뷰포트의 크기가 변하면 너비도 그에 맞춰 변한다.

<br/>
<br/>

# **단축 속성**

**단축 속성**은 관련된 **여러 속성을 하나로 합쳐 선언**할 수 있도록 만들어진 속성이다.  

합쳐진 각 속성은 **개별 속성** 이라고 부른다.

여러 속성을 합친 만큼 복수의 값을 전달하는 경우가 많은데, 이 때 **전달하는 값의 개수에 따라 각 값이 의미하는 바가 달라진다.**

대표적으로 값의 개수에 따라 방향이 달라지는 margin, padding 등이 있다.

<br/>

## **방향 지정이 가능한 단축 속성**  

기본적으로는 모든 방향에 대해 선언되지만,  
특정 방향을 지정하여 선언 가능한 속성들이 존재한다.  

이 때 속성의 이름 뒤에 `-방향` 을 붙여 방향을 지정할 수 있다.  

### **margin 방향 지정 예시**

- `margin-top`  
위쪽 외부 여백

- `margin-bottom`  
아래쪽 외부 여백

- `margin-left`  
왼쪽 외부 여백

- `margin-right`  
오른쪽 외부 여백

<br/>

이러한 방향 지정 가능한 속성은 대부분 **단축 속성**으로도 선언이 가능하다.  

이 때, **전달하는 값의 개수에 따라 각 값이 가리키는 방향이 달라진다.**

### **margin 단축 속성 예시**

- `margin: 10px;`  
모든 방향 10px

- `margin: 10px 20px;`  
상하 10px,  
좌우 20px  

- `margin: 10px 20px 30px;`  
상 10px,  
중(좌우) 20px,  
하 30px

- `margin: 10px 20px 30px 40px;`  
상 10px,  
우 20px,  
하 30px,  
좌 40px

<br/>
<br/>

# **속성의 종류** 

## **박스 모델**

### **`width`**  
요소의 가로 너비를 지정한다.

### **`max-width`**  
요소의 최대 가로 너비를 지정한다.

### **`min-width`**  
요소의 최소 가로 너비를 지정한다.

<br/>

### **`height`**
요소의 세로 높이를 지정한다.

### **`max-height`**  
요소의 최대 세로 높이를 지정한다.

### **`min-height`**  
요소의 최소 세로 높이를 지정한다.  

<br/>

### **`margin`**  
요소의 외부 여백을 지정한다.

개별 속성을 방향 지정이 가능하다.

블록 요소에 width 값이 지정된 상태에서 좌우 여백을 auto로 지정하면 가운데 정렬이 가능하다.

<br/>

### **`padding`**  
요소의 내부 여백을 지정한다.  

개별 속성으로 방향 지정이 가능하다.

내부 여백인 만큼 요소의 크기에 영향이 있다.

<br/>

### **`border`**
요소의 테두리를 지정하는 단축 속성이다.  
입력값은 순서대로 두께, 종류, 색상을 의미한다.

방향 지정이 가능하다.
```css
{border: 1px solid gray;}
```

### **`border-width`**  
테두리의 두께를 지정하는 `border`의 개별 속성이다.

### **`border-style`**  
테두리의 종류를 지정하는 `border`의 개별 속성이다.

### **`border-color`**  
테두리의 색상을 지정하는 border의 개별 속성이다.

### **`border-radius`**  
테두리의 둥근 정도를 지정한다.

<br/>

### **`outline`**  
`<input />` 등 요소를 포커스할 시 생기는 테두리를 지정한다.  

일반적인 상황에서 `outline: none;` 으로 선언하여 테두리를 없애고 `border`로 다시 테두리를 지정하는 것을 권장한다.

<br/>

### **`box-sizing`**  
요소의 크기 계산 기준을 지정한다.  

<br/>

- **`content-box;`**  
요소의 내부 여백과 테두리를 무시하고 순수한 요소의 크기만 계산한다.

- **`border-box;`**  
요소의 테두리 가장 바깥 부분으로 크기를 계산한다.

<br/>

### **`overflow`**  
요소의 크기 이상으로 내용이 넘쳤을 때를 제어하는 단축 속성이다.

- **`visible`**  
넘친 내용을 그대로 출력한다. (기본값)

- **`hidden`**  
넘친 내용은 잘라낸다.

- **`scroll`**  
스크롤을 생성한다.  
이 스크롤은 내용의 넘침 여부에 상관 없이 항상 생성된다.

- **`auto`**  
요소가 넘칠 시 스크롤을 생성한다.

### **`overflow-x`**  
`overflow`의 x축을 제어하는 개별 속성이다.

### **`overflow-y`**  
`overflow`의 y축을 제어하는 개별 속성이다.

<br/>

### **`scoll-behavior`**  
`overflow: scroll` 이 선언된 컨테이너 요소 내에서 다른 아이템 요소로 이동하는 `<a>` 태그를 사용할 때,  
스크롤이 움직이는 방식을 지정한다.  

컨테이너 역할을 하는 요소에 선언한다.
- `smooth`  
스크롤이 부드럽게 이동한다.

<br/>

### **`display`**  
요소의 화면 출력 특성을 지정한다.  

- `block`

- `inline`  

- `inline-block`

- `flex`

- `grid`

- `none`

<br/>

### **`opacity`**  
요소의 투명도를 지정한다.

0(투명)~1(불투명) 사이의 값을 부여한다.

<br/>

### **`box-shadow`**  
```css
{box-shadow: 4px 4px 10px rgba(0,0,0,.15);}
```
박스에 그림자 효과를 부여한다.  

속성값은 순서대로 x축 위치, y축 위치, 블러 정도, 색상을 의미한다.

<br/>
<br/>

## **스크롤 스냅**
브라우저를 스크롤할 때 요소의 스냅을 제어한다.  

스냅을 적용할 아이템 요소들과 그 아이템을 감싸는 컨테이너 요소가 필요하며, 컨테이너 요소에 `overflow: scroll;` 속성이 선언되어 있어야 한다.

### **`scroll-snap-type`**  
```css
{scroll-snap-type: y mandatory;}
```
스냅의 축과 엄격도를 지정한다.  
스냅을 적용할 컨테이너 요소에 선언한다.  

- 축 가용값

  - `x`

  - `y`

  - `block`

  - `inline`

  - `both`

- 엄격도 가용값

  - `none`

  - `proximity`

  - `mandatory`

### **`scroll-snap-align`**  
스냅이 적용될 때 아이템들의 정렬을 지정한다.  
스냅을 적용할 아이템들에 선언한다.

- `none`

- `start`

- `end`

- `center`

### **`scroll-snap-padding`**  
스냅에 대한 컨테이너의 내부 여백을 지정한다.  

이 내부 여백은 스냅이 적용되지 않는 범위를 의미한다.

### **`scroll-snap-margin`**  
스냅에 대한 각 아이템의 외부 여백을 지정한다.

이 내부 여백은 스냅이 적용되지 않는 범위를 의미한다.

<br/>
<br/>

## **글꼴**

### **`font-family`**  
`{font-family: "글꼴", "예비 글꼴"..., 글꼴 계열;}`
```css
{font-family: "Courier New", Courier, monospace;}
```
사용할 글꼴과 예비 글꼴, 그리고 글꼴 계열을 지정한다.  

지정한 글꼴을 모두 사용할 수 없는 경우 지정한 글꼴 계열 중 아무 글꼴이나 사용한다.  

예비 글꼴에 개수 제한은 없으며, 글꼴 이름에 띄어쓰기 등의 특수문자가 존재할 경우 따옴표로 감싸서 작성한다.  

마지막에 입력하는 글꼴 계열은 필수 입력 사항이다.

- 글꼴 계열 가용값  

  - `serif` : 바탕체

  - `sans-serif` : 고딕체

  - `monospace` : 고정 너비

  - `cursive` : 필기체  

  - `fancy` : 장식

<br/>

### **`font-size`**  
글자의 크기를 지정한다.  

기본값은 16px이다.

<br/>

### **`font-weight`**  
글자의 두께를 지정한다.  

- `nomal` 혹은 `400`

- `bold` 혹은 `700`

- `bolder` : 부모 요소보다 두껍게

- `lighter` : 부모 요소보다 얇게

- 그 외 `100` ~ `900` 사이 100 단위 숫자

<br/>

### **`font-style`**  
글자의 기울기를 지정한다.  

- `italic`

<br/>

### **`color`**  
글자의 색상을 지정한다.

- `rgb(0, 0, 0)`

- `색상명`

- `rgba(0, 0, 0, 0)`

<br/>

### **`line-height`**  
줄의 높이를 지정한다. (줄간격 x)  

글자는 해당 줄 높이의 정가운데로 정렬되며,  
이를 이용하여 요소의 `height` 와 `line-height` 를 통일시키면 글자를 수직 가운데정렬 할 수 있다.

<br/>

### **`text-indent`**  
문단의 들여쓰기와 내어쓰기를 지정한다.  

기본값은 0이며 px, em, rem 등의 단위를 사용한다.

<br/>
<br/>

## **배경**

### **`background-color`**  
배경의 색상을 지정한다.  

배경 이미지와 함께 사용이 가능하다.  

<br/>

### **`background-image: url("")`**  
요소의 배경 이미지를 지정한다.  

기본값으로 사용 시 요소의 크기에 따라 배경이 잘리거나 반복될 수 있다.

<br/>

### **`background-size`**  
요소 배경 이미지의 크기를 지정한다.

-  `auto`  
실제 크기. (기본값)

-  `cover`  
비율 유지, 더 넓은 너비에 맞춰진다.

-  `containe`  
비율 유지, 더 짧은 너비에 맞춰진다.

- 그 외 px 등 단위

<br/>

### **`background-repeat`**  
요소 배경 이미지의 반복을 지정한다.

- `repeat`  
바둑판 식으로 반복. (기본값)

- `no-repeat`  
반복 없음.  

- `repeat-x`  
x축 반복.  

- `repeat-y`  
y축 반복

<br/>

### **`background-position`**  
요소 배경 이미지의 위치를 지정한다.  

기본값은 `0% 0%` 이다. (x축 y축)

값으로 xy축의 `%`, `px` 등 단위 외에도 `top`, `bottom`, `center` 등의 방향을 선언할 수 있으며, 복수로 사용 가능하다.  
별도로 선언하지 않은 나머지는 center(50%)로 선언된다. 

<br/>  

### **`background-attachment`**  
요소 배경 이미지의 스크롤 특성을 지정한다.

- `scroll`  
배경 이미지도 스크롤되어 움직인다. (기본값)

- `fixed`  
배경 이미지가 뷰포트에 고정된다.

<br/>
<br/>

## **배치**  

### **`position`**  
요소의 위치 지정을 위한 기준을 정한다.  

아래에 나올 `top`, `bottom` 등을 통한 위치 옮김 시 기준을 정한다.

- `static`  
기준이 존재하지 않는다. 따라서 움직일 수 없다. (기본값)

- `relative`  
요소 자신에게 원래 할당된 위치를 기준으로 한다. 

  만약 요소를 움직이더라도 시각적으로 움직인 것 처럼 보이는 것 뿐이지 실제로 해당 요소는 원래의 위치에 존재한다.  따라서 다른 요소가 빈 자리를 채워주지 않는다.

  이러한 이유로 요소들의 위치가 직관적으로 이해되지 않는 상황이 발생할 수 있어 아래 나올 `absolute` 의 부모 요소로 사용할 때를 제외하고는 잘 쓰이지 않는다.

- `absolute`  
`position: static;`(기본값) 이 아닌 가장 가까운 상위 요소의 좌측 상단을 기준으로 잡는다.  

  조건에 해당하는 상위 요소가 존재하지 않을 시 뷰포트의 좌측 상단을 기준으로 잡는다.  

  이 속성을 부여하면 해당 요소는 공중에 붕 뜬 상태가 되어 더이상 자리를 차지하지 않게 되며, 다른 요소가 그 자리를 채울 수 있고 겹쳐질 수 있게 된다.

  또한 요소에 `display: block;` 속성을 자동으로 부여한다.

- `fixed`  
뷰포트의 좌측 상단을 기준으로 잡는다.

  이 속성을 부여하면 해당 요소는 공중에 붕 뜬 상태가 되어 더이상 자리를 차지하지 않게 되며, 다른 요소가 그 자리를 채울 수 있고 겹쳐질 수 있게 된다.

  뷰포트를 기준으로 고정되기 때문에 스크롤을 움직여도 해당 요소는 그 자리에 고정된다.  

  또한 요소에 `display: block;` 속성을 자동으로 부여한다.

- `sticky`  
`static` 과 `fixed` 의 가변형이다.  

  평상시에는 `static`으로 원래 위치에 존재하지만 뷰포트의 특정 위치에 도달할 경우 `fixed`로 변한다.  

  다시 특정 위치를 벗어날 경우 `static` 으로 돌아간다.

  사용하기 위한 조건이 까다로운 편에 속한다.

  - 사용 조건  

    - top, bottom, left, right 중 최소 하나의 속성이 반드시 필요하다.

    - 부모 혹은 상위 요소의 `overflow` 값이 하나라도 `hidden`, `scroll`, `auto`일 경우 동작하지 않는다.

    - 부모 요소의 `height` 가 명시되어야 한다. (% 제외)

<br/>

### **`top`, `bottom`, `left`, `right`**
요소의 위치를 지정한다. 

각 방향에서 전달한 값 만큼 이동하게 된다.

### **`z-index`**
요소의 쌓임 순서를 지정한다.

단위 없는 수로 값을 부여한다.

음수도 가능하긴 하다.

기본적인 순서는 `position: static;`이 아닌 요소가 위에 쌓이며, 이 조건이 동일할 경우 `z-index`의 값이 높을 수록 위에 쌓인다.

만약 위의 두 조건 모두 동일할 경우 하위 요소가 더 위에 쌓인다.

<br/>
<br/>

## **flex**

`display: flex;`가 선언된 요소와 그 하위 요소들에 대해 여러 속성을 부여하여 레이아웃을 만드는데 사용한다.

이 때 `display: flex;`가 선언된 요소를 **container**, 그 하위 요소를 **items**라고 부른다.

<br/>

## container 속성

### **`display: flex;`**
`display: flex;`가 선언되면 아이템들은 블록 요소더라도 **수평으로 쌓이고** **width 값이 최대한 줄어들게** 된다. 

flex를 이용한 레이아웃을 만들 때 가장 선행되어야 하는 속성이다.

<br/>

### **`display: inline-flex`**  
위와 동일하지만 container도 수평으로 쌓이고 `width` 값이 최대한 줄어들게 된다.

<br/>

### **`flex-direction`**  
아이템들을 정렬할 주 축을 지정한다.

이 때 주 축을 기준으로 정렬이 시작되는 쪽을 시작점(start), 그 반대편을 끝점(end) 라고 부른다.    

주 축과 교차되는 축은 교차축 이라고 부른다.

- `row`  
수평 축으로 좌에서 우로 정렬. (기본값)  

- `row-revers`  
수평 축으로 우에서 좌로 정렬. 

- `column`  
수직 축으로 상에서 하로 정렬.

- `column-reverse`  
수직 축으로 하에서 상으로 정렬.

<br/>

### **`flex-wrap`**  
아이템들의 크기가 컨테이너를 넘칠 때 줄바꿈 여부를 지정한다.

- `nowrap`  
줄바꿈하지 않고 아이템들의 크기를 줄인다. (기본값)

- `wrap`  
줄바꿈하고 아이템들의 크기를 유지한다.

<br/>

### **`justify-content`**  
주 축을 기준으로 한 아이템들의 정렬 방법을 지정한다.

- `flex-start`  
주 축 시작점을 기준으로 정렬.

- `flex-end`  
주 축 끝점을 기준으로 정렬

- `center`  
주 축을 기준으로 가운데 정렬

- `space-between`  
아이템 사이를 균등하게 정렬

- `space-around`  
아이템들의 가장 외부 여백을 균등하게 정렬


<br/>

### **`align-content`**  
교차축을 기준으로 한 아이템들의 정렬 방법을 지정한다.

- `stretch`  
시작점으로 정렬.  
컨테이너의 크기에 맞게 아이템들의 크기가 늘어나려는 특징을 갖는다. (기본값)

- `flex-start`  
교차축 시작점을 기준으로 정렬.

- `flex-end`  
교차축 끝점을 기준으로 정렬.

- `center`  
교차축을 기준으로 가운데 정렬

- `space-between`  
교차축을 기준으로 아이템 사이를 균등하게 정렬

- `space-around`  
교차축을 기준으로 아이템들의 가장 외부 여백을 균등하게 정렬

<br/>

## items 속성

### **`order`**  
아이템의 정렬 순서를 지정한다.  

이 정렬은 z축이 아닌 x(혹은 y)축의 순서를 말한다.

숫자가 작을수록 우선순위가 높다.  음수도 사용이 가능하지만 남용을 방지하기 위해 -1 정도만 사용하는 것을 권장한다.

<br/>

### **`flex-basis`**  
아이템들의 공간 배분 전에 기본 너비를 지정한다.

기본값은 `auto`이며 아이템의 내용에 맞춰 크기가 자동으로 정해진다.

<br/>

### **`flex-grow`**  
각 아이템들의 너비 증가 비율을 지정한다.

단위 없는 수로 값을 부여한다.

컨테이너에 `flex`가 선언되면 아이템들은 인라인 특성을 띄고 그 너비가 최대한으로 줄어들게 되는데, 이 속성을 부여하면 해당 아이템의 너비를 늘려서 컨테이너의 빈 칸을 꽉 채울 수 있다.

각 아이템들에 값을 따로 부여하여 너비 증가 비율을 조절할 수 있다.

`flex-basis`로 지정한 크기를 제외하고 남은 공간에서 비율에 따라 공간을 분배하기 때문에 정확한 비율을 부여하기 위해서는 아이템들에 `flex-basis: 0;`을 선언하고 사용해야한다.

<br/>

### **`flex-shrink`**  
아이템들의 너비 감소 비율을 지정한다.  

단위 없는 수로 값을 부여하며, 0을 부여 시 크기가 줄어들지 않는다.

브라우저의 크기를 줄이는 등의 이유로 컨테이너의 크기가 줄어들면 아이템들의 크기도 함께 줄어들게 되는데, 이 때 각 아이템의 너비가 감소하는 비율을 지정한다. 

`flex-basis` 혹은 `width` 등의 너비 값이 `auto`가 아니어야 하며, `flex-grow`와 함께 사용할 수 없다.

<br/>
<br/>

## **전환**

### **`transition`**  
`{transition: 속성명 지속시간 타이밍함수 대기시간;}`
```css
{transition: color 1.5s linear 0.5s}
```
요소의 전환 효과를 지정하는 단축 속성이다.

특정 속성에 대해 전환 효과를 보다 부드럽고 다양한 스타일로 적용할 수 있다. 

지속시간은 해당 효과의 전환이 몇 초에 걸쳐 이루어질지를 의미하며, 타이밍 함수는 탄성, 가속 등의 효과를 의미한다.

쉼표 구분을 통해 여러 속성에 대해 다른 값을 부여할 수 있다.

`transition-property`,  
`transition-duration`,  
`transition-timing-function`,  
`transition-delay`  
각 개별 속성을 사용하여 값을 따로 선언할 수 있다.

- 속성 가용값

  - `all`  
  전부

  - 그 외 다양한 css 스타일 속성.

- 지속시간 가용값  

  - s, ms 등 시간단위  

- 타이밍함수 가용값  
  
  - `ease`  
  느리게 -> 빠르게 -> 느리게 (기본값)

  - `linear`  
  일정하게

  - `ease-in`  
  느리게 -> 빠르게

  - `ease-out`  
  빠르게 -> 느리게

  - https://matthewlein.com/tools/ceaser 에서 다양한 타이밍함수를 확인해보고 사용할 수 있다.

- 대기시간  
  - s, ms 등 시간단위.
 
<br/>
<br/>

## **변환**

### **`transform`**  
```css
{transform: translate(40px, 40px);}
```
요소의 변환 효과를 지정한다.  

아래에 나올 다양한 **변환 함수를 값으로 전달**하여 사용한다.

<br/>

### **`perspective`**  
원근법을 이용하여 변환 효과에서 요소에 거리감을 부여한다. 보다 입체적인 효과를 줄 수 있다.

**입체 효과를 부여할 요소의 부모 요소에 선언한다.**

요소를 바라볼 위치인 기준점이 생성되며,
전달한 값(px 단위)은 해당 요소와 이 기준점 사이의 거리를 의미한다.

이 거리가 가까울수록 요소의 왜곡의 정도가 심해진다.

translate 함수로 해당 요소의 위치를 옮겨도 바라볼 기준점은 옮겨지지 않아서 해당 요소를 옆에서 바라보는 느낌을 줄 수 있다.

입체 효과를 부여할 때 가장 먼저 선언해야 하는 속성이다.

아래에 나올 `perspective` 함수와는 차이점이 있다.  
`perspective` 함수는 적용 대상이 효과를 입힐 요소 자신이다.

<br/>

### **`backface-visibility`**  
3D 변환 함수로 회전된 요소의 뒷면 출력 여부를 지정한다.

- `visible`  
뒷면이 보여진다. (기본값)

- `hidden`  
뒷면을 숨긴다.

<br/>
<br/>

## **2D 변환 함수**

`transform`의 값으로 사용한다.

<br/>

### **`translate(x, y)`**
### **`translateX(x)`**
### **`translateY(y)`**
요소를 x, y축으로 인자값만큼 이동시킨다.

<br/>

### **`scale(x, y)`**
### **`scaleX(x)`**
### **`scaleY(y)`**
요소의 크기를 변경한다.  

인자는 배수로 적용되며, 하나의 값만 입력 시 x축과 y축 모두에 적용된다.

<br/>

### **`rotate(degree)`**  
요소를 회전시킨다.

인자는 각도로 적용된다. (단위 : deg)

<br/>

### **`skew(x, y)`**
### **`skewX(x)`**
### **`skewY(y)`**
요소를 기울인다.  

인자는 각도로 적용된다. (단위 : deg)

`skew(x, y)` 보다는 개별 함수가 주로 사용된다.

<br/>
<br/>

## **3D 변환 함수**

`transform`의 값으로 사용한다.

<br/>

### **`translate3d(x, y, z)`**
### **`translateZ(z)`**
`translate`의 z축 추가 버전.  

잘 사용되지 않는다.

<br/>

### **`scale3d(x, y, z)`**
### **`scaleZ(z)`**
`scale`의 z축 추가 버전.

잘 사용되지 않는다.

<br/>

### **`rotateX(x)`**
### **`rotateY(y)`**
### **`rotateZ(z)`**
### **`rotate3d(x, y, z)`**
각 축을 기준으로 회전시킨다.

인자는 각도로 적용된다. (단위 : deg)

z축은 잘 사용되지 않는다.

<br/>

### **`perspective(n)`**
`perspective` 속성의 함수 버전.

원근법 효과가 해당 요소에 직접 적용된다.

3D 효과를 부여할 요소마다 직접 적용해야하는 번거로움이 존재하고, 요소마다 기준점이 다르게 생성되어 따로 노는 느낌을 줄 수 있기 때문에 상위 요소에 속성으로 선언하는 것을 권장한다.

<br/>
<br/>

# **그 외 자잘한 팁**

## **요소 수평 가운데 정렬**

수평 가운데 정렬이 필요한 **블록 요소**에 `width` 값을 지정하고 좌우 `margin`을 `auto`로 선언하면 수평 가운데 정렬이 가능하다.

<br/>

## **요소 수직 가운데 정렬**

수직 가운데 정렬이 필요한 요소에 `height` 값을 지정하고 상하 `margin`을 `auto`로 선언한다.  

이어서  

`position: abolute;`,  
`top: 0;`,  
`bottom: 0;`  

을 선언하고 정렬의 기준이 될 부모 요소에 `position: relative`를 선언하면 수직 가운데 정렬이 가능하다.

<br/>

## **.inner**

`.inner` 클래스를 생성하여 해당 HTML 문서의 전 영역에서 공통적으로 적용할 가운데 정렬, `width`, `padding`, `margin` 혹은 `position` 의 기준을 위한 `position: relative;` 등 상황에 따라 다양한 속성을 선언한다.

이후 각 영역을 생성할 때 콘텐츠들을 `.inner`로 한 번 감싸주면 보다 편하게 필요한 레이아웃을 적용할 수 있다.

또한 영역별로 다르게 적용할 부분은 하위 선택자를 통해 해당 영역의 `.inner`에만 별도로 부여하면  

A 영역이 내부에서 1, 2, 3, 4의 영역으로 다시 나누어지더라도 1, 2, 3, 4에 전부 같은 `.inner`를 부여함으로써 1, 2, 3, 4는 여백, 정렬, 너비 등이 동일한 레이아웃을 갖게 된다.

<br/>

## **요소 가운데 배치**

가운데 정렬과는 조금 다른 내용이다.

보통은 뷰포트의 크기가 줄어들면 요소가 오른쪽부터 잘리고 점점 오른쪽으로 치우치게 되는데,

요소에 `position: absolute;`와 `left: 50%;`를 선언하고,  
요소의 너비 절반 만큼 `margin-left`에 값을 **음수**로 부여하면

창의 크기가 줄어도 요소의 콘텐츠가 항상 가운데에 위차하도록 할 수 있다.

<br/>

## **img 태그 하단 여백**

`<img />` 태그는 인라인 요소이고, 인라인 요소의 주 목적은 텍스트를 담는 것이다.

g, y 등과 같은 알파벳은 다른 알파벳보다 위치가 더 아래로 내려가 있는데, 이를 위해서 모든 인라인 요소는 기본적으로 하단 여백이 존재한다.  

따라서 `<img />` 태그도 동일하게 하단에 여백이 존재한다.  
이는 `display: block;` 을 선언하여 간단하게 해결할 수 있다.

<br/>

## **`<a>` 태그 클릭 영역**

`<a>` 태그의 폰트 크기를 줄이면 클릭 가능한 영역도 자동으로 줄어들게 된다. 

이 때 `padding`을 함께 부여하면 클릭 가능한 영역을 다시 늘릴 수 있다.  

`<a>` 태그는 인라인 요소이기 때문에 `display: block;`의 선언이 선행되어야 한다.

<br/>

## **세로 구분선**

헤더 메뉴나 카테고리 등에서 각 메뉴 요소의 구분선이 필요한 경우가 자주 있는데, 구분이 필요한 요소에 아래 내용을 선언하여 세로 구분선을 추가할 수 있다.

```css
ul li {
  position: relative;
}
ul li::before {
  content: "";
  width: 1px;
  height: 12px;
  background-color: black;
  position: absolute;
  top: 0;
  bottom: 0;
  margin: auto;
}
```
`width`는 구분선의 두께를 가리키고 `height`는 구분선의 길이를 가리킨다.  

그 외 `position`, `top`, `bottom`, `margin`은 구분선의 가운데 정렬을 위한 속성이다.

<br/>

## **요소의 비율**
```css
.container {
  width: 500px;
}
.container .item {
  width: 100%;
  padding-top: 56.25%;
}
```
컨테이너 내부 아이템의 `width` 와 `padding-top`의 %를 통해 컨테이너의 `width`에 맞춰 원하는 비율로 출력할 수 있다. 위의 예시는 16:9의 비율을 갖는다.  

여기서 아이템은 아무 내용 없이 단순히 컨테이너가 비율에 맞게 출력될 수 있도록 하는 역할이다.

이러한 방법을 사용하는 이유는, 컨테이너 내부에 아무 내용이 없을 경우 %를 통한 `height` 정확한 제어가 불가능하기 때문에 아무 내용 없는 요소의 내부 여백을 %로 제어하여 높이를 늘리는 것이다.

<br/>

## **폰트**
google fonts에서 다양한 폰트를 사용할 수 있다.  

무료로 사용 가능하지만 혹시 모를 상황에 대비해 사용 전에 라이센스를 확인하는 것을 권장한다.

### 사용 방법

1. <a href="https://fonts.google.com/">google fonts</a> 에서 원하는 폰트와 굵기 선택

1. 해당 폰트의 `<link>` 태그 내용 복사.

1. HTML `<head>` 태그 내에 붙여넣기.

1. CSS의 `font-family`로 기존의 폰트와 동일하게 사용.

<br/>

## **아이콘**
google fonts에서는 다양한 아이콘도 찾아서 사용할 수 있다.

### 사용 방법

1. HTML의 '<head>' 태그 내에 아래 내용 붙여넣기.  
  `<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">`

1. 아이콘을 사용할 위치에 종류 상관 없이 태그를 하나 생성하고, 클래스명에 `"material-icons"` 추가

1. <a href="https://fonts.google.com/icons"> google fonts </a> 에서 원하는 아이콘 검색.

1. 위에서 생성한 태그에 찾은 아이콘 이름 입력.