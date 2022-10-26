# Functions

Dart는 객체 지향 언어이므로 함수도 객체이며 [Function](https://api.dart.dev/stable/dart-core/Function-class.html)이라는 타입을 갖습니다. 즉, 함수를 변수에 할당하거나 다른 함수에 인자로 전달할 수 있습니다. 또한 Dart 클래스의 인스턴스를 마치 함수처럼 호출할 수도 있습니다. 자세한 내용은 [Callable classes](https://dart.dev/guides/language/language-tour#callable-classes)를 참조하세요.

다음은 함수를 구현하는 예입니다.

```dart
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
```

Effective Dart는 [공개 API에 대한 명시적 타입 선언](https://dart.dev/guides/language/effective-dart/design#do-type-annotate-fields-and-top-level-variables-if-the-type-isnt-obvious)을 권장하지만 타입을 생략해도 함수가 계속 작동합니다.

```dart
isNoble(atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
```

표현식이 하나만 포함된 함수의 경우 약식 구문을 사용할 수 있습니다.

```dart
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
```

`=> expr` 구문은 `{ return expr; }` 를 생략한 것입니다. `=>` 표기법은 화살표 구문이라고도 합니다.

{% hint style="info" %}
**Note:** statement가 아닌 expression만 화살표(=>)와 세미콜론(;)으로 표현할 수 있습니다. 예를 들어, [if statement](https://dart.dev/guides/language/language-tour#if-and-else)은 사용할 수는 없지만 [conditional expression](https://dart.dev/guides/language/language-tour#conditional-expressions)을 사용할 수는 있습니다.
{% endhint %}
