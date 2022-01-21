## Dart -형 변환- 

```dart
void main() {
 List<String> fish = ['싱어', '복어', '붕어', '장어'];
  print(fish.asMap());
  }

```

List를  Map 형태로 바꾸어주면,

```dart
{0: 싱어, 1: 복어, 2: 붕어, 3: 장어}
```

key 값에는  index 가, value 값에는, String 값들이 리스트 순서대로 생성된다.



```dart
void main() {
 List<String> fish = ['싱어', '복어', '붕어', '장어'];
  print(fish.asSet());
  }

```

Set는 사실 List 와 크게 다르지 않은 형태에 타입이다. 

List 는 중복값을 포함 할 수 있고, Set는 중복 값을 한가지 정보로 통일해준다.





