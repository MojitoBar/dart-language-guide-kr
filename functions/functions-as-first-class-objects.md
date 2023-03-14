# Functions as first-class objects

함수를 다른 함수의 매개변수로 전달할 수 있습니다. 아래는 예시입니다.

```dart
void printElement(int element) {
  print(element);
}

var list = [1, 2, 3];

// Pass printElement as a parameter.
list.forEach(printElement);
```

함수를 변수에 할당할 수도 있습니다.

```dart
var loudify = (msg) => '!!! ${msg.toUpperCase()} !!!';
assert(loudify('hello') == '!!! HELLO !!!');
```

이 예제에서는 익명 함수(anonymous function)를 사용합니다. 이에 대해서는 다음 섹션에서 자세히 설명하겠습니다.
