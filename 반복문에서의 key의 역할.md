# 반복문에서의 key의 역할

리스트에서 순서대로 유지하게 한다. 리스트가 이동된 경우(정렬 등), 또는 삽입 삭제가 됐을 때 리액트는 key값을 이용해 DOM 트리를 올바르게 업데이트 한다.

그러므로 리스트에서 올바른 key값을 줘서 리액트가 목록을 효율적으로 업데이트하게 해야한다.

---
참고
- [https://react.dev/learn/rendering-lists#keeping-list-items-in-order-with-key](https://react.dev/learn/rendering-lists#keeping-list-items-in-order-with-key)
