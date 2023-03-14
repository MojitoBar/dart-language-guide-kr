# Anonymous functions

대부분의 함수는 `main()`이나 `printElement()`와 같이 이름이 지정된 함수입니다. 그러나 익명 함수(anonymous function) 또는 람다(lambda) 또는 클로저(closure)라고 불리는 이름 없는 함수도 만들 수 있습니다. 예를들어, 익명 함수를 변수에 할당하여 컬렉션에서 추가하거나 제거할 수 있습니다.

익명 함수는 이름이 지정된 함수와 비슷합니다. 괄호 안에 쉼표로 구분된 매개변수 목록(선택적으로 타입 어노테이션이 포함될 수 있음)이 나오고, 이어서 아래와 같은 함수의 본문이 나옵니다.

`([[`_`Type`_`]`` `_`param1`_`[, …]]) {`\
&#x20; ```  `_`codeBlock`_`;`\
`};`

아래 예제는 타입이 지정되지 않은 매개변수 `item`을 가지는 익명 함수를 정의하고, 이를 `map` 함수에 전달합니다. 리스트의 각 항목에 대해 호출된 함수는 각 문자열을 대문자로 변환합니다. 그런 다음 `forEach`에 전달된 익명 함수에서 각 변환된 문자열과 해당 길이를 출력합니다.

```dart
const list = ['apples', 'bananas', 'oranges'];
list.map((item) {
  return item.toUpperCase();
}).forEach((item) {
  print('$item: ${item.length}');
});
```

만약 함수가 단일 표현식 또는 반환문만을 포함한다면, 화살표 표기법(arrow notation)을 사용하여 축약할 수 있습니다. 아래 코드를 [DartPad](https://dartpad.dev/)에 붙여넣고 실행하여 기능적으로 동등한지 확인할 수 있습니다.

```dart
list
    .map((item) => item.toUpperCase())
    .forEach((item) => print('$item: ${item.length}'));
```
