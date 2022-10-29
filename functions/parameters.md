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

위치 인수(positional arguments)를 먼저 배치하는 것이 일반적이지만 API에 적합할 경우 명명된 인수(named arguments)를 인수 목록의 아무 곳에나 배치할 수 있습니다.

```dart
repeat(times: 2, () {
  ...
});
```

{% hint style="info" %}
**Tip:** 매개변수가 선택사항이지만 null이 될 수 없는 경우 기본값을 제공하세요.
{% endhint %}

명명된 매개변수는 일종의 선택적 매개변수이지만 매개변수가 필수임을 나타내기 위해 `required` 키워드을 달 수 있습니다. 이렇게 되면, 사용자는 매개변수 값을 제공해야 합니다. 아래는 예시입니다.

```dart
const Scrollbar({super.key, required Widget child});
```

