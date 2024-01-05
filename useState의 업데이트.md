# useState의 업데이트

```jsx
function App(){
  const [count, setCount] = useState(0);
  
  const handleClick = ()=>{
    setCount(count + 1);
    console.log(count); // 버튼 누르기 이전 값
  }
  
  return(
    <button onClick={handleClick}>+</button>
  )
  
}

```

버튼을 눌렀을 때, handleClick에서 로그를 찍으면 이전 값이 찍힌다.

setState 실행시, 렌더링 후에 업데이트 된 값을 사용한다.
1. 컴포넌트 리렌더링
2. 업데이트 된 값을 사용

## state는 비동기적으로 업데이트 된다.
리액트는 성능을 위해 여러 setState()호출을 단일 업데이트로 한번에 처리하기 때문에 이전 값이 찍힌다.

## state에 의존하는 state 다루기
```jsx
const [count, setCount] = useState(0);
const [number, setNumber] = useState(1);
//...
<div className='App'>
  <p>1부터 3까지 세봅시다. {number}</p>
  <button
    onClick={()=>{
      setCount(count+1);
      if(count<3) {
        setNumber(number+1);
      }
    }}>
    나를 눌러주세용
  </button>
</div>
```
위 코드는 1부터 3이 아닌 4까지 세게 된다. 버튼을 눌렀을 때 기대하는 상태 값은 `count = 1, number = 2`, `count = 2, number = 3`이다. 그런데 실제로 동작은 `count = 0, number = 2`, `count = 1, number = 3`, `count = 2, number = 4`이다. 이렇게 동작하는 이유는 useState는 비동기로 동작하기 때문이다.

`useEffect`훅을 사용하면 원하는 동작을 하게 할 수 있다. 
```jsx
useEffect(()=>{
  if(count !== 0 && count < 3) {
    setNumber(number+1);
  }
}, [ count ]);

// ...
<div className='App'>
 <p>1부터 3까지 세봅시다. {number}</p>
 <button 
    onClick={()=>{
      setCount(count+1);
  }}>
    나를 눌러주세용
  </button>
</div>
);
```


---
참고
- [https://codingapple.com/unit/react-setstate-async-problems/](https://codingapple.com/unit/react-setstate-async-problems/)

