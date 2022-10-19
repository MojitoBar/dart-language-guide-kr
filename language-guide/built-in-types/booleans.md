# Booleans

Boolean 값을 나타내기 위해 Dart에는 `bool`이라는 타입이 있습니다. bool 타입은 `true` 및 `false` 값을 가지며, 둘 다 컴파일 타임 상수입니다.

Dart는 type-safe하기 때문에 `if(nonbooleanValue)` 또는 `assert(nonbooleanValue)`와 같은 코드를 사용할 수 없습니다. 대신 예제와 같이 명시적으로 값을 확인해야합니다.

```dart
// Check for an empty string.
var fullName = '';
assert(fullName.isEmpty);

// Check for zero.
var hitPoints = 0;
assert(hitPoints <= 0);

// Check for null.
var unicorn;
assert(unicorn == null);

// Check for NaN.
var iMeantToDoThis = 0 / 0;
assert(iMeantToDoThis.isNaN);
```
