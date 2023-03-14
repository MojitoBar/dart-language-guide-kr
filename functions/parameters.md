# Parameters

함수는 required 파라미터를 원하는 수만큼 가질 수 있습니다. 다음에는 named 파라미터 또는 optional 파라미터가 올 수 있습니다(둘 다는 안됨).

{% hint style="info" %}
**Note:** 일부 API(특히 [Flutter](https://flutter.dev/) 위젯 생성자)는 required 파라미터에 대해서도 named 파라미터만 사용합니다. 자세한 내용은 다음 섹션을 참조하십시오.
{% endhint %}

함수에 인수를 전달하거나 함수 매개변수를 정의할 때 [trailing commas](https://dart.dev/guides/language/language-tour#trailing-comma)를 사용할 수 있습니다.

### **Named parameters**

Named parameters는 `required` 키워드가 표시되지 않는 한 선택 사항입니다.

함수를 정의할 때 `{param1, param2, …}`를 사용하여 Named parameters를 지정합니다.

```dart
/// Sets the [bold] and [hidden] flags ...
void enableFlags({bool? bold, bool? hidden}) {...}
```

함수를 호출할 때 `paramName: value`를 사용하여 Named parameters를 지정할 수 있습니다. 아래는 예시입니다.

```dart
enableFlags(bold: true, hidden: false);
```

명명된 매개변수에 null 이외의 기본값을 정의하려면, `=`을 사용하여 기본값을 지정하세요. 지정된 값은 컴파일 타임 상수이어야 합니다. 아래는 예시입니다.

```dart
/// Sets the [bold] and [hidden] flags ...
void enableFlags({bool bold = false, bool hidden = false}) {...}

// bold will be true; hidden will be false.
enableFlags(bold: true);
```

명명된 매개변수는 일종의 선택적 매개변수이지만 매개변수가 필수임을 나타내기 위해 `required` 키워드을 달 수 있습니다. 이렇게 되면, 사용자는 매개변수 값을 제공해야 합니다. 아래는 예시입니다.

```dart
const Scrollbar({super.key, required Widget child});
```

만약 `child`를 지정하지 않은 채로 `Scrollbar`를 생성하려하면 컴파일 타임에 에러가 발생합니다.

{% hint style="info" %}
**Note:** 필수로 표시된 매개변수도 `null`이 가능합니다.
{% endhint %}

위치 인수(positional arguments)를 먼저 배치하는 것이 일반적이지만 Dart가 그러한 규칙을 요구하지는 않습니다. Dart는 매개변수 목록에서 명명된 매개변수를 어디에 놓아도 허용합니다.

```dart
repeat(times: 2, () {
  ...
});
```

### **Optional positional parameters**

대괄호 `[]`로 함수 매개변수를 묶으면 선택적 위치 매개변수로 표시됩니다. 기본값을 제공하지 않으면, 해당 매개변수의 타입은 `null`이 될 것이므로 `nullable`이어야 합니다.

```dart
String say(String from, String msg, [String? device]) {
  var result = '$from says $msg';
  if (device != null) {
    result = '$result with a $device';
  }
  return result;
}
```

선택적 매개변수를 사용하지 않고 이 함수를 호출하는 예시입니다.

```dart
// Optional positional parameter인 device 생략 
assert(say('Bob', 'Howdy') == 'Bob says Howdy');
```

다음은 세 번째 매개변수를 사용하여 이 함수를 호출하는 예시입니다.

```dart
assert(say('Bob', 'Howdy', 'smoke signal') ==
    'Bob says Howdy with a smoke signal');
```

null 이외의 선택적 위치 매개변수에 기본값을 정의하려면, `=`을 사용하여 기본값을 지정하세요. 지정된 값은 컴파일 타임 상수이어야 합니다. 아래는 예시입니다.

```dart
String say(String from, String msg, [String device = 'carrier pigeon']) {
  var result = '$from says $msg with a $device';
  return result;
}

assert(say('Bob', 'Howdy') == 'Bob says Howdy with a carrier pigeon');
```

\
