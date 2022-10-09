# A basic Dart program

이 페이지에서는 다른 언어로 프로그래밍하는 방법을 이미 알고 있다는 가정 하에 변수 및 연산자에서 클래스와 라이브러리에 이르기까지 각 주요 Dart 기능을 사용하는 방법을 보여줍니다. 언어에 대한 간략한 소개는 [language samples page](https://dart.dev/samples)를 참조하세요.

다트의 핵심 라이브러리에 대해 자세히 알아보려면 [library tour](https://dart.dev/guides/libraries/library-tour)를 참조하세요. 다트 언어 기능에 대해 자세한 정보를 원한다면 Dart [language specification](https://dart.dev/guides/language/spec)을 참조하세요.

{% hint style="info" %}
**Note:** [DartPad](https://dartpad.dev/)를 사용하면 대부분의 Dart언어 기능을 실행해볼 수 있습니다 ([자세히 알아보기](https://dart.dev/tools/dartpad)).
{% endhint %}

### A basic Dart program

아래 코드는 Dart의 가장 기본적인 기능을 많이 사용한 코드입니다.

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

