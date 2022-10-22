# Set

Dart의 Set은 고유한 항목의 순서가 없는 컬렉션입니다. Set에 대한 Dart 지원은 Set 리터럴 및 [Set](https://api.dart.dev/stable/dart-core/Set-class.html) 타입에 의해 제공됩니다.

다음은 Set 리터럴을 사용하여 만든 간단한 Dart의 Set입니다.

```dart
var halogens = {'fluorine', 'chlorine', 'bromine', 'iodine', 'astatine'};
```

{% hint style="info" %}
**Note:** Dart는 `halogens` 타입이 `Set<String>`이라고 추론합니다. Set에 잘못된 유형의 값을 추가하려고 하면 컴파일 또는 런타임에서 오류가 발생합니다. 자세한 내용은 [type inference](https://dart.dev/guides/language/type-system#type-inference)에 대해 읽어보세요.
{% endhint %}

빈 Set을 생성하려면 타입 인수가 앞에 오는 `{}`를 사용하거나 `Set` 유형의 변수에 `{}`를 할당합니다.

```dart
var names = <String>{};
// Set<String> names = {}; // 빈 Set을 생성합니다.
// var names = {}; // Set이 아니라 Map이 생성됩니다.
```

{% hint style="info" %}
**Set or map?** map 리터럴의 구문은 Set 리터럴의 구문과 유사합니다. map 리터럴이 먼저 나왔기 때문에 `{}`는 기본적으로 map 타입이 됩니다. `{}`의 타입이나 변수 할당을 생략한 경우 Dart는 `Map<dynamic, dynamic>` 유형의 객체를 생성합니다.
{% endhint %}

`add()` 또는 `addAll()` 메서드를 사용하여 기존 Set에 항목을 추가합니다.

```dart
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
```

`.length`를 사용하여 Set의 항목 수를 가져옵니다.

```dart
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
assert(elements.length == 5);
```

컴파일 타임 상수인 Set을 만들려면 Set 리터럴 앞에 `const`를 추가하세요.

```dart
final constantSet = const {
  'fluorine',
  'chlorine',
  'bromine',
  'iodine',
  'astatine',
};
// constantSet.add('helium'); // 이 줄에서 에러가 발생합니다.
```

Set은 List과 마찬가지로 스프레드 연산자(`...` 및 `...?`) 및 collection `if` 및 `for`를 지원합니다. 자세한 내용은 [list spread operator](https://dart.dev/guides/language/language-tour#spread-operator) 및 [list collection operator](https://dart.dev/guides/language/language-tour#collection-operators) 참조하세요.

집합에 대한 자세한 내용은 [Generics](https://dart.dev/guides/language/language-tour#generics) 및 [Sets](https://dart.dev/guides/libraries/library-tour#sets)을 참조하세요.
