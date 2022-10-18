# String

Dart 문자열(String 객체)은 일련의 UTF-16 코드 단위를 보유합니다. 작은따옴표나 큰따옴표를 사용하여 문자열을 만들 수 있습니다.

```dart
var s1 = 'Single quotes work well for string literals.';
var s2 = "Double quotes work just as well.";
var s3 = 'It\'s easy to escape the string delimiter.';
var s4 = "It's even easier to use the other delimiter.";
```

`${expression}`을 사용하여 문자열 안에 표현식을 넣을 수 있습니다. 표현식이 식별자인 경우 {}를 생략할 수 있습니다. 객체에 해당하는 문자열을 가져오기 위해 Dart는 객체의 `toString()` 메서드를 호출합니다.

```dart
var s = 'string interpolation';

assert('Dart has $s, which is very handy.' == 
    'Dart has string interpolation, which is very handy.');
assert('That deserves all caps. ${s.toUpperCase()} is very handy!' ==
    'That deserves all caps. STRING INTERPOLATION is very handy!');
```

{% hint style="info" %}
**Note:** `==` 연산자는 두 개체가 동일한지 여부를 테스트합니다.
{% endhint %}

인접한 문자열 리터럴 또는 `+` 연산자를 사용하여 문자열을 연결할 수 있습니다.

```dart
// 인접한 문자열 리터럴로 연결
var s1 = 'String '
    'concatenation'
    " works even over line breaks.";
assert(s1 ==
    'String concatenation works even over '
    'line breaks.');

// + 연산자로 연결
var s2 = 'The + operator ' + 'works, as well.';
assert(s2 == 'The + operator works, as well.');
```

여러 줄 문자열을 만드는 또 다른 방법: 작은따옴표나 큰따옴표로 삼중따옴표를 사용합니다.

```dart
var s1 = '''
You can create
multi-line strings like this one.
''';

var s2 = """This is also a
multi-line string.""";
```

`r`을 접두사로 붙여 "원시(raw)" 문자열을 만들 수 있습니다.

```dart
var s = r'In a raw string, not even \n gets special treatment.';
```

문자열에서 유니코드 문자를 표현하는 방법에 대한 자세한 내용은 [Runes and grapheme clusters](https://dart.dev/guides/language/language-tour#characters)를 참조하세요.

표현식이 null, 숫자, 문자열, bool 값, 즉 컴파일 타임 상수인 경우 리터럴 문자열은 컴파일 타임 상수입니다.

```dart
// 이들은 const string에서 사용할 수 있습니다.
const aConstNum = 0;
const aConstBool = true;
const aConstString = 'a constant string';

// 이들은 const string에서 사용할 수 없습니다.
var aNum = 0;
var aBool = true;
var aString = 'a string';
const aConstList = [1, 2, 3];

const validConstString = '$aConstNum $aConstBool $aConstString';
// const invalidConstString = '$aNum $aBool $aString $aConstList';
```

문자열 사용에 대한 자세한 내용은 [문자열 및 정규식](https://dart.dev/guides/libraries/library-tour#strings-and-regular-expressions)을 참조하세요.\
