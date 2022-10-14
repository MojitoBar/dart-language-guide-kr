---
description: 아래 코드는 Dart의 가장 기본적인 기능을 많이 사용한 코드입니다.
---

# A basic Dart program

```dart
// 함수 정의.
void printInteger(int aNumber) {
    print('The number is $aNumber.');    // 콘솔 창에 출력.
}

// 여기에서 앱이 실행되기 시작합니다.
void main() {
    var number = 42;    // 변수를 선언하고 초기화합니다.
    printInteger(number);    // 함수 호출.
}
```

다음은 거의 모든 Dart 앱에 적용되는 내용입니다.

`// 이것은 주석입니다.`\
``한 줄 주석입니다. Dart는 여러 줄과 문서 주석도 지원합니다. 자세한 내용은 [여기](https://dart.dev/guides/language/language-tour#comments)를 참조하세요.

`void`\
사용된 적이 없는 값을 나타내는 특수한 자료형입니다. 명시적으로 값을 반환하지 않는 `printInteger()` 및`main()` 과 같은 함수는 반환 유형이 `void` 입니다.

`int`\
정수를 나타내는 자료형입니다. 기본 제공 자료형에는 `String`, `List`, `bool`이 있습니다.

`42`\
숫자 리터럴. 숫자 리터럴은 일종의 컴파일 타임 상수입니다.

`print()`\
출력을 표시하는 편리한 방법입니다.

`'...' & "..."`\
문자열 리터럴입니다.

`$variableName & ${expression}`\
문자열 보간: 문자열 리터럴 내부에 변수 또는 표현식에 해당하는 문자열을 포함합니다. 자세한 내용은 [여기](https://dart.dev/guides/language/language-tour#strings)를 참조하세요.

`main()`\
앱이 시작되기 위해 필요한 최상위 함수입니다. 자세한 내용은 [여기](https://dart.dev/guides/language/language-tour#the-main-function)를 참조하세요.

`var`\
자료형을 지정하지 않고 변수를 선언하는 방법입니다. 이 키워드 변수의 유형은 초기 값에 의해 결정됩니다.

{% hint style="info" %}
**Note:** 이 사이트의 코드는 [Dart style guide](https://dart.dev/guides/language/effective-dart/style)의 규칙을 따릅니다.
{% endhint %}
