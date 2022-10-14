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

### Default value

nullable 타입인 초기화되지 않은 변수의 초기 값은 `null`입니다. ([null safety](https://dart.dev/null-safety) 타입이 아닌 경우 모든 변수에는 nullable 타입이 있습니다.) number 타입의 변수도 처음에는 null입니다. 왜냐하면 number 타입은 Dart의 다른 모든 것과 마찬가지로 객체(Object)이기 때문입니다.

```dart
int? lineCount;
assert(lineCount == null);
```

{% hint style="info" %}
**Note:** 프로덕션 코드는 `assert()` 호출을 무시합니다. 반면에 개발하는 동안 `assert(condition)`은 조건이 거짓이면 예외를 던집니다. 자세한 내용은 [Assert](https://dart.dev/guides/language/language-tour#assert) 참조하세요.
{% endhint %}

null safety 타입의 경우 변수 값을 사용하기 전에 초기화해야 합니다.

```dart
int lineCount = 0;
```

선언된 지역 변수를 초기화할 필요는 없지만 사용하기 전에 값을 할당해야 합니다. 예를 들어 다음 코드는 Dart가 `print()`에 전달할 때 `lineCount`가 null이 아님을 확인할 수 있기 때문에 유효합니다.

```dart
int lineCount;

if (weLikeToCount) {
  lineCount = countLines();
} else {
  lineCount = 0;
}

print(lineCount);
```

최상위 및 클래스 변수는 초기화 코드는 변수가 처음 사용될 때 실행되는 lazily initialized 입니다.

### Late variables

Dart 2.12에는 두 가지 사용 사례가 있는 `late` 키워드를 추가되었습니다.

* 선언 후에 초기화되는 nullable이 아닌 변수를 선언하기 위해 사용합니다.
* 변수를 느리게 초기화하기 위해 사용합니다.

```dart
late String description;

void main() {
  description = 'Feijoada!';
  print(description);
}
```

{% hint style="danger" %}
Late 변수 초기화에 실패하면 변수를 사용할 때 런타임 오류가 발생합니다.
{% endhint %}

변수를 late로 표시하지만 선언 시 초기화하면 실질적인 변수 초기화는 변수가 처음 사용될 때 실행됩니다. 이러한 지연 초기화는 다음과 같은 경우에 유용합니다.

* 변수가 필요하지 않을 수 있으며 초기화하는 데 비용이 많이 드는 경우.
* 인스턴스 변수를 초기화하고 있으며 이에 대한 액세스 권한이 필요한 경우.

다음 예시에서 `temperature` 변수가 사용되지 않으면 값비싼 `readThermometer()` 함수가 호출되지 않습니다.

```dart
// 이것은 readThermometer()에 대한 프로그램의 유일한 호출입니다.
late String temperature = readThermometer(); // 지연 초기화
```

### Final and const

변수를 수정하지 않으려면 `var` 대신 또는 타입에 `final` 또는 `const`를 추가하여 사용하세요. final 변수는 한 번만 초기화 할 수 있습니다. const 변수는 컴파일 타임 상수입니다. (Const 변수는 암묵적으로 최종입니다.)

다음은 final 변수를 만들고 초기화하는 예입니다.

```dart
final name = 'Bob'; // 타입 없이 초기화
final String nickname = 'Bobby';
```

final 변수의 값은 변경할 수 없습니다.

```dart
name = 'Alice'; // 에러: final 변수는 한 번만 설정할 수 있습니다.
```

**컴파일 타임 상수**가 될 변수에는 const를 사용하세요. const 변수가 클래스 레벨에 있으면 `static const`로 표시합니다. 변수를 선언할 때, 값을 number 또는 문자열 리터럴, const 변수 또는 상수 숫에 대한 산술 연산 결과와 같은 컴파일 타임 상수로 설정합니다.

```dart
const bar = 1000000; // 압력 단위 (dynes/cm2)
const double atm = 1.01325 * bar; // 표준 대기
```

const 키워드는 상수 변수를 선언하기 위한 것만이 아닙니다. 상수 값을 생성하는 생성자를 선언할 수도 있습니다. 모든 변수는 상수 값을 가질 수 있습니다.

```dart
var foo = const [];
final bar = const [];
const baz = []; // `const []`와 동일합니다.
```

위의 baz와 같이 `const` 선언의 초기화 표현식에서 `const`를 생략할 수 있습니다. 자세한 내용은 [DON’T use const redundantly](https://dart.dev/guides/language/effective-dart/usage#dont-use-const-redundantly) 참조하세요.

`const` 값으로 초기화 했어도 final 또는 const 가 아니라 변수의 값을 변경할 수 있습니다.

```dart
foo = [1, 2, 3]; // Was const []
```

`const` 변수의 값은 변경할 수 없습니다.

```dart
baz = [42]; // 에: 상수 변수에 값을 할당할 수 없습니다.
```

[type checks and casts](https://dart.dev/guides/language/language-tour#type-test-operators)(`is` 또 `as`), [collection if](https://dart.dev/guides/language/language-tour#collection-operators), [spread operators](https://dart.dev/guides/language/language-tour#spread-operator)(... 또는 ...?)를 사용하여 상수를 정의할 수 있습니다.

```dart
const Object i = 3; // 여기서 i는 int 값을 가진 const 객체입니다.
const list = [i as int]; // type casts를 사용.
const map = {if (i is int) i: 'int'}; // is와 collection if 사용.
const set = {if (list is List<int>) ...list}; // spread operator 사용.
```

{% hint style="info" %}
**Note:** `final` 객체는 수정할 수 없지만 객체의 필드는 변경할 수 있습니다. 그에 비해 `const` 객체는 그 필드도 변경할 수 없습니다.
{% endhint %}

`const`를 사용하여 상수 값을 만드는 방법에 대한 자세한 내용은 [Lists](https://dart.dev/guides/language/language-tour#lists), [Maps](https://dart.dev/guides/language/language-tour#maps) 및 [Classes](https://dart.dev/guides/language/language-tour#classes)를 참조하세요.
