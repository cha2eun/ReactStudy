# ES
# 
#### 출처 [Vlpt] (https://react.vlpt.us/basic/)
## 2022-07-04
#### 비구조화 할당 (구조분해)
객체에서 값들을 추출하여 새로운 상수로 선언해서 이용
#
(*객체관련* 객체에 this.~를 사용한 함수를 포함할 때, function이 아닌 화살표 함수로 넣으면 동작하지 않는다.
 function에서 this는 자신이 속한 객체를 가리키지만, 화살표함수는 그렇지 못하기때문)

> const object={a: 1, b:2 };
> const {a, b} = object;     비구조화 할당
> console.log(a);
> console.log(b);   
#
#
*비구조화 할당시 값 변경하기*
#
위 코드에서
> const {a, b} = object;
> object.a = 3; 을 하면 바꿀 수 있음
> 그러나
> const c = object.a;    로 받아왔다면 위와 같이 바꿀 수 없으므로
>    const { a : c } = object;
 
## 2022-07-06
#### 조건부 렌더링
> 삼항연산자 이용
> 조건(true/false)에 따라 처리되도록 && 연산자 이용 / <TestComp isSetting/> <--true라고 간주

#### useState 
[참고링크 ](https://velog.io/@isabel_noh/React-useState-%EB%B9%84%EB%8F%99%EA%B8%B0-batch-update)
> 사용자 인터렉션에 따라 컴포넌트에서 보이는 내용이 바뀌어야 할 때 사용
> const [number, setNumber] = useState(0);  : 첫번째-현재 상태, 두번째-Setter 함수
> setNumber(prevNumber => prevNumber + 1);  : 이전값 업데이트 
>   > 힘수형으로 파라미터를 넘겨주면 배치로 상태값 변경 처리함
>   >   > *useState, 비동기, batch에 대하여*
>   >   > - setState를 사용하여 업데이트할 경우, 리렌더링된 후에야 state에 반영된다.
>   >   > - 효율적인 렌더링을 위하여 여러번의 상태값 변경 요청을 배치로 처리한다.
>   >   > - 변경사항을 모아서 일괄처리로 처리함으로써 렌더링 횟수를 최소화함
>   >   > ----> 바로바로 업데이트 하기위해서는 
>   >   >   > 1. useEffect
>   >   >   > 2. 함수형 업데이트 가 필요하다.

d