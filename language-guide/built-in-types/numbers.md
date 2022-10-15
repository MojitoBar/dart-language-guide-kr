# Numbers

다트에서 numbers는 두 가지 방식으로 제공됩니다.

[`int`](https://api.dart.dev/stable/dart-core/int-class.html)``\
``[플랫폼에 따라](https://dart.dev/guides/language/numbers) 64비트 이하의 정수 값을 가집니다. 기본 플랫폼에서 `int`값은 -2^64에서 2^63 - 1 사이일 수 있습니다. 웹에서 정수 값은 JavaScript 숫자(소수 부분이 없는 64비트 부동 소수점 값)으로 표시되며 -2^53에서 2^53 - 1일 수 있습니다.

[`double`](https://api.dart.dev/stable/dart-core/double-class.html)``\
``IEEE 754 표준에서 지정한 64비트(배정밀도) 부동 소수점 숫자입니다.

`int`와 `double`은 모두 [num](https://api.dart.dev/stable/2.18.2/dart-core/num-class.html)의 하위 타입입니다. num 타입에는 +, -, / 및 \*와 같은 기본 연산자가 포함되며 사용할 수 있는 다른 메소드로는 `abs()`, `ceil()` 및 `floor()` 등이 있습니다. (>>와 같은 비트 연산자는 int 클래스에 정의되어 있습니다.) num과 그 하위 타입에 원하는 메소드가 없으면 [dart:math](https://api.dart.dev/stable/dart-math) 라이브러리에 있을 수 있습니다.

정수는 소수점이 없는 숫자입니다. 다음은 정수 리터럴을 정의하는 몇 가지 예입니다.

```dart
var x = 1;
var hex = 0xDEADBEEF;
```

숫자에 소수가 포함되어 있으면 실수 입니다. 다음은 실수 리터럴을 정의하는 몇 가지 예입니다.

```dart
var y = 1.1;
var exponents = 1.42e5;
```

변수를 num 타입으로 선언할 수도 있습니다. 이렇게 하면 변수는 정수와 실수값을 모두 가질 수 있습니다.

```dart
num x = 1; // x는 int와 double 값을 모두 가질 수 있습니다.
x += 2.5;
```

정수 리터럴은 필요한 경우 자동으로 double로 변환됩니다.

```dart
double z = 1; // double z = 1.0와 똑같습니다.
```

문자열을 숫자로 숫자를 문자열로 바꾸는 방법은 다음과 같습니다.

```dart
// String -> int
var one = int.parse('1');
assert(one == 1);

// String -> double
var onePointOne = double.parse('1.1');
assert(onePointOne == 1.1);

// int -> String
String oneAsString = 1.toString();
assert(oneAsString == '1');

// double -> String
String piAsString = 3.14159.toStringAsFixed(2);
assert(piAsString == '3.14');
```

`int` 타입은 플래그 조작 및 마스킹에 유용한 기존 비트 시프트(`<<`, `>>`, `>>>`), 보수(`~`), AND(`&`), OR(`|`) 및 XOR(`^`) 연산자가 있습니다.

```dart
assert((3 << 1) == 6); // 0011 << 1 == 0110
assert((3 | 4) == 7); // 0011 | 0100 == 0111
assert((3 & 4) == 0); // 0011 & 0100 == 0000
```

더 많은 예를 보려면 [bitwise and shift operator](https://dart.dev/guides/language/language-tour#bitwise-and-shift-operators)을 참조하세요.

리터럴 숫자는 컴파일 타임 상수입니다. 피연산자가 컴파일 타임 상수인 경우 대부분의 산술 표현식도 컴파일 시간 상수입니다.

```dart
const msPerSecond = 1000;
const secondsUntilRetry = 5;
const msUntilRetry = secondsUntilRetry * msPerSecond;
```

자세한 내용은 Dart의 [Numbers](https://dart.dev/guides/language/numbers)를 참조하세요.
