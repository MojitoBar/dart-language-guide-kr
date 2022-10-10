---
description: Dart 언어에 대해 배울 때 아래 사실과 개념을 염두에 두세요.
---

# Important concepts

* 변수에 넣을 수 있는 모든 값은 객체(object)이고, 모든 객체는 클래스의 인스턴스입니다. 심지어 number, funtions, null도 객체(object)입니다. null을 제외하고 ([Sound null safety](https://dart.dev/null-safety)를 활성화한 경우) 모든 객체는 [Object](https://api.dart.dev/stable/2.18.2/dart-core/Object-class.html) class를 상속합니다.

{% hint style="info" %}
**Version Note:** [Null safety](https://dart.dev/null-safety)는 Dart 2.12에서 도입되었습니다. null safety 사용하려면 2.12 이상의 언어 버전이 필요합니다.
{% endhint %}

* Dart는 강타입 언어이지만, 타입 유추가 가능하므로 타입 표기는 선택사항입니다.
*
