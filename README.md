# react_1
> ## 비주얼스튜디오 편집 단축키
![image](https://user-images.githubusercontent.com/75229868/110595718-b88f4380-81c1-11eb-81b9-de2be4c1345f.png)

> ## 리액트 파일 생성
>```npx create-react-app 프로젝트 이름```
    
> ## 미리보기
>```npm start```

> ## 코드 작성
>```App.js,App.css```

> ## 주석
> {/* 내용 */}

> ## 콘솔 warning 
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
> b = a의 값을 바꿔주는 함수
>```a[0] = 1 ```와 같이 state의 값을 직접변경하지는 못하기때문에
>b(변경사항) 같은 형태로 바꿔주어야 한다
>b()로 바꾼 값은 a에 남지 않는다.
> 
> useState()는 2개(a = 내용, b = a의 수정본)를 반환한다
>:: state는 a를 직접 수정할 수 없기때문에 b를 수정한다 ::    
> 
> ex ▶ let [a , b] = useState(['안녕하세요','안녕히가세요','감사합니다']);
> a[0] = '안녕하세요'
> a[1] = '안녕히가세요'
> a[2] = '감사합니다'
> ```
> 
>```
>import React, {useState} from 'react'; {/*state임포트*/}
>
>let [a , b] = useState(['안녕하세요','안녕히가세요','감사합니다']);
>
>   <h3> { a[0] } </h3> {/*바인딩 (변수,함수,state 등)*/}
>```

>### state 값 변경
>
>b(['qwer','asdf','zxcv']);
>'안녕하세요' -> 'qwer'
>'안녕히가세요' -> 'asdf'
>'감사합니다' -> 'zxcv'
>
>로 변경되었지만
>a = ['안녕하세요','안녕히가세요','감사합니다']
>```
>
>### state값 복사 후 변경
>```
>var newArray = [...a] {/* 기존의 리스트와는 다른 리스트, a 복제 (newArray = ['안녕하세요','안녕히가세요','감사합니다']) */}
>newArray[0] = 'qwer' {/* ['qwer','안녕히가세요','감사합니다']*/}
>b(newArray);
>
>{/*a의 값은 변경되지 않는다 a = ['안녕하세요','안녕히가세요','감사합니다']*/}
>{/*newArray = ['qwer','안녕히가세요','감사합니다']*/}
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
>
>### 이벤트 3. onClick = { state } :: 2
>
>```
>let [list_title,list_title_r] = useState(['남자 코트 추천','강남 우동 맛집','3번']);
>
>function title_r(){
>    var newarray = [...list_title]; {/*newarray = ['남자 코트 추천','강남 우동 맛집','3번']*/}
>    newarray[0] = '여자 코트 추천'; {/*newarray = ['여자 코트 추천','강남 우동 맛집','3번']*/}
>    list_title_r(newarray);
>} {/*state 값을 바꾸는 함수 title_r*/}
>
><button onClick={title_r}>바꾸기</button> 
>{/* 버튼을 클릭하면 '남자 코트 추천'이 '여자 코트 추천' 으로 바뀜*/}
>{/* 즉시 실행이 아닌 클릭이 되었을때 실행 되어야 하기때문에 함수명(title_r) 뒤에 괄호()는 붙이지 않음*/}
>```
