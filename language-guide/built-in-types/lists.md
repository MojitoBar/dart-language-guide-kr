# Lists

거의 모든 프로그래밍 언어에서 가장 일반적인 컬렉션은 array 일 것입니다. Dart에서 배열은 [List](https://api.dart.dev/stable/dart-core/List-class.html) 객체이므로 사람들은 그냥 lists이라고 부릅니다.

다트에서 List 리터럴은 대괄호(\[])로 묶인 쉼표로 구분된 표현식 또는 값으로 표시됩니다. 다음은 간단한 Dart List입니다.

```dart
var list = [1, 2, 3];
```

{% hint style="info" %}
**Note:** Dart는 `list`에 `List<int>` 가 있다고 추론합니다. 이 list에 정수가 아닌 개체를 추가하려고 하면 런타임에서 오류가 발생합니다. 자세한 내용은 [type inference](https://dart.dev/guides/language/type-system#type-inference)에 대해 읽어보세요.
{% endhint %}

Dart 컬렉션 리터럴의 마지막 항목 뒤에 쉼표를 추가할 수 있습니다. 이 후행 쉼표는 컬렉션에 영향을 미치지는 않지만 복사-붙여넣기 오류를 방지하는 데 도움이 될 수 있습니다.

```dart
var list = [
  'Car',
  'Boat',
  'Plane',
];
```

List는 0부터 시작하는 인덱싱을 사용합니다. 여기서 0은 첫 번째 값의 인덱스이고 `list.length - 1`은 마지막 값의 인덱스입니다. `.length` 속성을 사용하여 List의 길이를 얻고 아래 첨자 연산자(\[])를 사용하여 List의 값에 접근할 수 있습니다.

```dart
var list = [1, 2, 3];
assert(list.length == 3);
assert(list[1] == 2);

list[1] = 1;
assert(list[1] == 1);
```

컴파일 타임 상수인 List를 만들려면 List 리터럴 앞에 `const`를 추가하세요.

```dart
var constantList = const [1, 2, 3];
// constantList[1] = 1; // 이 줄에서 에러가 발생합니다.
```

Dart 2.3에서는 여러 값을 컬렉션에 삽입하는 간결한 방법을 제공하는 **스프레드 연산자**(`...`)와 **널 인식 스프레드 연산자**(`...?`)를 도입했습니다.

```dart
var list = [1, 2, 3];
var list2 = [0, ...list];
assert(list2.length == 4);
```

스프레드 연산자 오른쪽에 있는 식이 널일 수 있는 경우 널 인식 스프레드 연산자(`...?`)를 사용하여 예외를 피할 수 있습니다.

```dart
var list2 = [0, ...?list];
assert(list2.length == 1);
```

스프레드 연산자 사용에 대한 자세한 내용과 예는 [spread operator proposal](https://github.com/dart-lang/language/blob/master/accepted/2.3/spread-collections/feature-specification.md)을 참조하세요.

Dart는 또한 조건부(`if`)와 반복(`for`)을 사용하여 컬렉션을 구축하는 데 사용할 수 있는 **collection if** 및 **collection for** 제공합니다.

다음은 **collection if**를 사용하여 3\~4개의 항목이 포함된 List를 만드는 예입니다.

```dart
var nav = ['Home', 'Furniture', 'Plants', if (promoActive) 'Outlet'];
```

다음은 **collection for**을 사용하여 다른 List에 추가하기 전에 List의 항목을 조작하는 예입니다.

```dart
var listOfInts = [1, 2, 3];
var listOfStrings = ['#0', for (var i in listOfInts) '#$i'];
assert(listOfStrings[1] == '#1');
```

collection `if` 및 `for`에 대한 자세한 내용과 예제는 [control flow collections proposal](https://github.com/dart-lang/language/blob/master/accepted/2.3/control-flow-collections/feature-specification.md)을 참조하세요.

List 타입에는 List을 조작하기 위한 많은 편리한 방법이 있습니다. List에 대한 자세한 내용은 [Generics](https://dart.dev/guides/language/language-tour#generics) 및 [Collections](https://dart.dev/guides/libraries/library-tour#collections)을 참조하세요.\
