# The main() function

### The main() function <a href="#the-main-function" id="the-main-function"></a>

모든 앱은 최상위 `main()` 함수를 가져야합니다. 이 함수는 앱의 진입점(entrypoint) 역할을 합니다. `main()` 함수는 `void`를 반환하며, 인자로 선택적으로 `List<String>`을 받을 수 있습니다.

다음은 `main()` 함수의 예제입니다.

```dart
void main() {
  print('Hello, World!');
}
```

아래는 인자를 받는 command-line 앱의 main() 함수의 예시입니다.

```dart
// Run the app like this: dart args.dart 1 test
void main(List<String> arguments) {
  print(arguments);

  assert(arguments.length == 2);
  assert(int.parse(arguments[0]) == 1);
  assert(arguments[1] == 'test');
}
```

command-line 인자를 정의하고 파싱하기 위해 [`args` 라이브러리](https://pub.dev/packages/args)를 사용할 수 있습니다.
