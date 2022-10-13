# Variables

다음은 변수를 생성하고 초기화 하는 예시 입니다.

```dart
var name = 'Bob';
```

변수는 참조를 저장합니다. `name`이라는 변수는 값이 "Bob"인 `String` 객체에 대한 참조를 포함합니다.

name의 타입은 문자열로 유추되지만 개체가 단일 타입으로 제한되지 않는 경우 Object 타입(필요에 따라 Dynamic)으로 지정하여 해당 타입을 변경할 수 있습니다.

```dart
Object name = 'Bob';
```

또 다른 옵션은 유추될 타입을 명시적으로 선언하는 것입니다.

```dart
String name = 'Bob';
```

{% hint style="info" %}
**Note:** 이 페이지는 지역 변수에 직접 자료형을 지정(type annotaion) 해주는 대신 var를 사용하는 [스타일 가이드 권장 사항](https://dart.dev/guides/language/effective-dart/design#types)을 따릅니다.
{% endhint %}
