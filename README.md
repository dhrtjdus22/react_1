# react_1

> ## 리액트 파일 생성
>```npx create-react-app 프로젝트 이름```
    
> ## 미리보기
>```npm start```

> ## 코드 작성
>```App.js,App.css```

> ## 주석
> {/* 내용 */}

> ## 콘솔 warning 무시
> /* eslint-disable */

> ## 바인딩
>``` 
> let posts = 'list_1'; {/*변수 선언*/}
> 
><div className="list">
>   <h3> { posts } </h3> {/*바인딩 (변수,함수,state 등)*/}
>   <p>2월 17일 발행</p>
>  <hr/>
></div>
>```

> ## state
> ```
>임포트 = import React, {useState} from 'react'; 
>
> let [a , b] = useState(a에 담길 내용) {/*리스트 가능*/}    
> 
> a = 변수    
> b = a의 수정을 담을 변수
> 
> useState()는 2개(a = 내용, b = a의 수정본)를 반환한다
>:: state는 a를 직접 수정할 수 없기때문에 b를 수정한다 ::    
> 
> ex ▶ let [a , b] = useState(['안녕하세요','안녕히가세요','감사합니다']);
> a[0] = '안녕하세요'
> a[1] = '안녕히가세요'
> a[2] = '감사합니다'
> ```

>```
>import React, {useState} from 'react'; {/*state임포트*/}
>
>let [a , b] = useState(['안녕하세요','안녕히가세요','감사합니다'])
>
> <div className="list">
>   <h3> { a[0] } </h3> {/*바인딩 (변수,함수,state 등)*/}
>   <p>2월 17일 발행</p>
>  <hr/>
></div>
>```

> ## 이벤트 (onClick)
> ```
> 1. onClick = { 클릭될 때 실행할 "함수"}
> 2. onClick = { ()=>{실행할 내용} }
> 3. onClick = { state }
>```

>### 이벤트 1. onClick = { 클릭될 때 실행할 "함수"}
>```
>function my_fx(){
>   return console.log(0)
>}
>{/*콘솔에 0을 입력하는 함수 my_fx()*/}
>    
><span onClick={my_fx()}>♥</span> 0 {/*하트옆에 표시될 숫자*/}
>{/*하트를 누를때마다 my_fx() 함수 실행*/}
> ```

>### 이벤트 2. onClick = { ()=>{실행할 내용} }
>```
><span onClick={()=> {console.log(1)}}>♥</span> 0{/*하트옆에 표시될 숫자*/}
>{/*하트를 누를때마다 콘솔에 1을 출력*/}
> ```

>### 이벤트 3. onClick = { state }
>```
>let [a,b] = useState(0) {/*a = 0*/}
>
><span onClick={() => { b(a+1) } }>♥</span> {a} {/*하트옆에 표시될 숫자, 중괄호 안에 state를 넣어야함*/}
>{/*하트를 누를때마다 a가 1씩 증가*/}
>```
