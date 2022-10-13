---
description: Dart 언어에 대해 배울 때 아래 사실과 개념을 염두에 두세요.
---

# Important concepts

* 변수에 넣을 수 있는 모든 값은 객체(object)이고, 모든 객체는 클래스의 인스턴스입니다. 심지어 number, funtions, null도 객체(object)입니다. null을 제외하고 ([Sound null safety](https://dart.dev/null-safety)를 활성화한 경우) 모든 객체는 [Object](https://api.dart.dev/stable/2.18.2/dart-core/Object-class.html) class를 상속합니다.

{% hint style="info" %}
**Version Note:** [Null safety](https://dart.dev/null-safety)는 Dart 2.12에서 도입되었습니다. null safety 사용하려면 2.12 이상의 언어 버전이 필요합니다.
{% endhint %}

* Dart는 강타입 언어이지만, 타입 유추가 가능하므로 타입 표기는 선택사항입니다.
* Null safety가 활성화 된 버전이라면, 변수는 기본적으로 `null`값을 포함할 수 없습니다. 타입 끝에 물음표(?)를 넣어 변수를 nullable로 만들 수 있습니다. 예를 들어 `int?` 는 정수이거나 `null`일 수 있습니다. 표현식이 null이 아님을 알고 있는 경우, 느낌표(!)를 추가하여 표현식이 null이 아니라고 주장할 수 있습니다. (만약 null이라면 예외가 발생합니다.) 예를 들어 `int x = nullableButNotNullInt!` 와 같이 표현할 수 있습니다.
* 모든 타입이 허용된다고 명시적으로 선언하고 싶을 때 유형 Object?(null safety를 활성화한 경우), Object를 사용하거나 런타임까지 타입 검사를 연기해야 ​​하는 경우 특수 타입 dynamic를 사용하세요.
* Dart는 `List<int>` 또는 `List<Object>` 와 같은 제네릭 타입을 지원합니다.
* Dart는 최상위 함수(예: `main()`)와, 클래스 또는 객체에 연결된 함수(각각 정적 및 인스턴스 메서드)를 지원합니다. 함수 내에서 함수를 생성할 수도 있습니다(중첩 또는 로컬 함수).
* 마찬가지로 Dart는 최상위 변수와, 클래스 또는 객체에 연결된 변수(정적 및 인스턴스 변수)를 지원합니다. 인스턴스 변수를 필드 또는 속성(properties)이라고도 합니다.
* Java와 달리 Dart에는 `public`, `protected` 및 `private` 키워드가 없습니다. 식별자가 밑줄(\_)로 시작하는 경우 해당 라이브러리에 대해 비공개입니다. 자세한 내용은 [Libraries and visibility](https://dart.dev/guides/language/language-tour#libraries-and-visibility) 참조하세요.
* 식별자는 문자나 밑줄(\_)로 시작하고 그 뒤에 해당 문자와 ​​숫자의 조합이 올 수 있습니다.
* Dart는 expressions(런타임 값이 있는)과 statements(없는)을 모두 가지고 있습니다. 예를 들어 조건연산자 `조건 ? expr1 : expr2`는 expr1 또는 expr2의 값을 가집니다. 값이 없는 `if-else` 문과 비교됩니다. statements에는 종종 하나 이상의 expressions가 포함되지만 expressions은 statements를 직접 포함할 수 없습니다.
* Dart 도구는 warnings와 errors라는 두 가지 종류의 문제를 리포트할 수 있습니다. warnings는 코드가 작동하지 않을 수 있다는 표시일 뿐, 프로그램 실행을 방해하지는 않습니다. errors에는 컴파일 에러와 런타임 에러가 있습니다. 컴파일 타임 오류의 경우 코드가 전혀 실행되지 않습니다. 런타임 오류의 경우는 코드가 실행되는 와중에 예외([exception](https://dart.dev/guides/language/language-tour#exceptions))가 발생합니다.
