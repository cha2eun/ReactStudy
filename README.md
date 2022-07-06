# React/ES6공부

## 2022-07-04
#### 비구조화 할당 (구조분해)
객체에서 값들을 추출하여 새로운 상수로 선언해서 이용
(*객체관련* 객체에 this.~를 사용한 함수를 포함할 때, function이 아닌 화살표 함수로 넣으면 동작하지 않는다.
 funcion에서 this는 자신이 속한 객체를 가리키지만, 화살표함수는 그렇지 못하기때문)

 const object={a: 1, b:2 };
 const {a, b} = object;     비구조화 할당
 console.log(a);
 console.log(b);   

*비구조화 할당시 값 변경하기*
위 코드에서
 const {a, b} = object;
 object.a = 3; 을 하면 바꿀 수 있음
 그러나
 const c = object.a;    로 받아왔다면 위와 같이 바꿀 수 없으므로
 const { a : c } = object;
 
