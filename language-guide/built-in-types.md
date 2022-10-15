# Built-in types

Dart는 다음과 같은 타입들을 지원합니다.

* [Numbers](https://dart.dev/guides/language/language-tour#numbers) (`int`, `double`)
* [Strings](https://dart.dev/guides/language/language-tour#strings) (`String`)
* [Booleans](https://dart.dev/guides/language/language-tour#booleans) (`bool`)
* [Lists](https://dart.dev/guides/language/language-tour#lists) (`List`, 배열이라고도 함.)
* [Sets](https://dart.dev/guides/language/language-tour#sets) (`Set`)
* [Maps](https://dart.dev/guides/language/language-tour#maps) (`Map`)
* [Runes](https://dart.dev/guides/language/language-tour#characters) (`Runes`; 보통 `characters` API로 대체됨.)
* [Symbols](https://dart.dev/guides/language/language-tour#symbols) (`Symbol`)
* `null` 값 (`Null`)

이 지원에는 리터럴을 사용하여 개체를 만드는 기능이 포함됩니다. 예를 들어 `'this is a string'`은 문자열 리터럴이고 `true`는 boolean 리터럴입니다.

Dart의 모든 변수는 객체(클래스의 인스턴스)를 참조하기 때문에 일반적으로 생성자를 사용하여 변수를 초기화할 수 있습니다. 일부 빌트인 타입에는 자체 생성자가 있습니다. 예를 들어 `Map()` 생성자를 사용하여 map을 만들 수 있습니다.

몇몇 타입들은 Dart 언어에서 특별한 역할을 합니다.

* `Object`: Null을 제외한 모든 Dart 클래스의 상위 클래스 입니다.
* `Enum`: 모든 열거형의 상위 클래스 입니다.
* `Future & Stream`: 비동기 지원에 사용됩니다.
* `Iterable`: [for-in](https://dart.dev/guides/libraries/library-tour#iteration) 반복문과 동기 [generator functions](https://dart.dev/guides/language/language-tour#generator)에서 사용됩니다.
* `Never`: 표현식의 결과가 성공적으로 완료될 수 없음을 나타냅니다. 항상 예외를 throw하는 함수에 가장 자주 사용됩니다.
* `dynamic`: 타입을 명시하고 싶지 않다는 것 나타냅니다. 일반적으로 `Object` 또는 `Object?` 대신에 사용합니다.

`Object`, `Object?`, `Null` 및 `Never` 클래스는 [Understanding null safety](https://dart.dev/null-safety/understanding-null-safety)의 [top-and-bottom](https://dart.dev/null-safety/understanding-null-safety#top-and-bottom) 섹션에 설명된 대로 클래스 계층에서 특별한 역할을 합니다.
