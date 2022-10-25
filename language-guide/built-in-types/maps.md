# Maps

일반적으로 맵은 key와 value를 연결하는 개체입니다. 키와 값 모두 모든 타입이 가능합니다. 각 key는 고유하지만 value는 동일한 값을 여러 번 사용할 수 있습니다. 맵에 대한 Dart 지원은 맵 리터럴 및 [맵](https://api.dart.dev/stable/dart-core/Map-class.html) 타입으로 제공됩니다.

다음은 맵 리터럴을 사용하여 만든 몇 가지 간단한 Dart 맵입니다.

```dart
var gifts = {
  // Key:    Value
  'first': 'partridge',
  'second': 'turtledoves',
  'fifth': 'golden rings'
};

var nobleGases = {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
```

{% hint style="info" %}
**Note:** Dart는 `gifts` 타입이 `Map<String, String>`이고 `nobleGases` 타입 `Map<int, String>`이라고 추론합니다. 맵에 잘못된 타입의 값을 추가하려고 하면 컴파일 또는 런타임에서 오류가 발생합니다. 자세한 내용은 [type inference](https://dart.dev/guides/language/type-system#type-inference)에 대해 읽어보세요.
{% endhint %}

Map 생성자를 사용하여 동일한 객체를 생성할 수 있습니다.

```dart
var gifts = Map<String, String>();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';

var nobleGases = Map<int, String>();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```

{% hint style="info" %}
**Note:** C# 또는 Java와 같은 언어의 경험이 있다면 `Map()` 대신 `new Map()`을 예상할 수 있습니다. Dart에서 `new` 키워드는 선택 사항입니다. 자세한 내용은 [Using constructors](https://dart.dev/guides/language/language-tour#using-constructors)을 참조하세요.
{% endhint %}

아래 첨자 할당 연산자(`[]=`)를 사용하여 기존 맵에 새 key-value 쌍을 추가합니다.

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds'; // key-value 쌍을 추가
```

아래 첨자 연산자(`[]`)를 사용하여 맵에서 값을 검색합니다.

```dart
var gifts = {'first': 'partridge'};
assert(gifts['first'] == 'partridge');
```

맵에 없는 키를 찾으면 null이 반환됩니다.

```dart
var gifts = {'first': 'partridge'};
assert(gifts['fifth'] == null);
```

`.length`를 사용하여 맵에서 key-value 쌍의 수를 가져옵니다.

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds';
assert(gifts.length == 2);
```

Maps는 lists와 마찬가지로 스프레드 연산자(`...` 및 `...?`)와 `if` 및 `for` 컬렉션을 지원합니다. 자세한 내용과 예제는 [spread operator proposal](https://github.com/dart-lang/language/blob/master/accepted/2.3/spread-collections/feature-specification.md) 및 [control flow collections proposal](https://github.com/dart-lang/language/blob/master/accepted/2.3/control-flow-collections/feature-specification.md) 을 참조하세요.

맵에 대한 자세한 내용은 [generics](https://dart.dev/guides/language/language-tour#generics) 섹션과 [Maps API](https://dart.dev/guides/libraries/library-tour#maps)에 대한 라이브러리 투어를 참조하세요.
