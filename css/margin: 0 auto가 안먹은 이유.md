# margin: 0 auto가 안먹은 이유

## 문제
![image](https://github.com/dev-hamster/TIL/assets/123740296/26968dd3-b87c-4845-8973-ddbf76a6955f)

```html
<style>
  .box {
    display: block;
    margin: 0 auto;
    border: 1px solid;
  }
</style>

<div class="box">hello</div>
```
기대한 중앙정렬이 되지 않는다

## 원인
[margin은 `coontaining block`의 width에 따라 계산된다](https://www.w3.org/TR/CSS22/box.html#propdef-margin-top)
> Percentages:	refer to width of containing block

그러므로 요소에 width를 적절히 주자
![image](https://github.com/dev-hamster/TIL/assets/123740296/7c3cb4ee-af1b-475d-9785-b91f447b3af5)

```html
<style>
  .box {
    display: block;
    margin: 0 auto;
    width: 100px;
    border: 1px solid;
  }
</style>

<div class="box">hello</div>
```
