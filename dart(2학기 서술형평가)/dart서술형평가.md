# Dart 서술형 시험 출제 내용 (주석 포함)

## 출제 내용 개요

1.  Base

1) print
2) 변수
3) null Safety
   ㄱ) ? 연산자
   ㄴ) ! 연산자

2.  Operator

1) 연산자
   ㄱ) 사칙연산
   ㄴ) 증감연산
2) 조건문
3) 반복문

3.  List, Map, Set

1) List 선언, 응용
2) Set 선언, 응용
   ㄱ) intersection 교집합
   ㄴ) difference 차집합

5.  객체 지향

1) 클래스 생성
2) 상속

## 상세 내용

### 01 Base

#### 1. print

```dart
void main(){
    print("Hello 1");  // 쌍따옴표로 문자열 출력
    print('Hello 2');  // 홑따옴표로 문자열 출력
}
```

#### 2. 변수

```dart
void main() {
  int myAge = 26;  // 정수형 변수 선언 및 초기화
  double myHeight = 181.8;  // 실수형 변수 선언 및 초기화
  String myName = 'Dave Lee';  // 문자열 변수 선언 및 초기화
  bool military = true;  // 불리언 변수 선언 및 초기화

  print(myAge);  // 정수형 변수 출력
  print(myHeight);  // 실수형 변수 출력
  print(myName);  // 문자열 변수 출력
  print(military);  // 불리언 변수 출력

  // 문자열 보간법(String Interpolation)을 사용한 변수 출력
  print('My Name is ${myName}');
  print('My age is ${myAge}, My Height is ${myHeight}');
}
```

#### 3. null Safety

##### ㄱ) ? 연산자

```dart
void main(){
    int? data1;  // null 값을 가질 수 있는 정수형 변수 선언
    print(data1);  // null 출력
}
```

##### ㄴ) ! 연산자

```dart
void main(){
    List<int?> myArray = [1, 3, null];  // null 값을 포함할 수 있는 정수 리스트
    int myItem = myArray[0]!;  // null이 아님을 확신할 때 ! 연산자 사용
    print(myItem);  // 1 출력
}
```

### 02 Operator

#### 1. 연산자

##### ㄱ) 사칙연산

```dart
void main(){
  print(5 + 3);  // 덧셈: 8
  print(5 - 3);  // 뺄셈: 2
  print(5 * 3);  // 곱셈: 15
  print(5 / 3);  // 나눗셈: 1.6666666666666667
  print(5 % 3);  // 나머지: 2
  print(5 ~/ 3);  // 몫: 1 (정수 나눗셈)
}
```

##### ㄴ) 증감연산

```dart
void main(){
  int a = 1;
  a = a + 1;  // 변수 a에 1을 더함
  print(a);  // 2 출력
  print(++a);  // 전위 증가 연산자: 먼저 증가 후 출력 (3 출력)
  print(a++);  // 후위 증가 연산자: 출력 후 증가 (3 출력)
  print(a);  // 4 출력 (이전 단계에서 증가된 값)
}
```

#### 2. 조건문

```dart
void main(){
  num data = 1;
  if(data == 1){
    print('data는 1이다.');  // data가 1일 때 실행
  }
  else if(data == 2){
    print('data는 2이다.');  // data가 2일 때 실행
  }
  else{
    print('data는 1과 2가 아니다.');  // data가 1도 2도 아닐 때 실행
  }
}
```

#### 3. 반복문

```dart
void main() {
  // for 루프
  for (int i = 0; i < 3; i++) {
    print('For 루프: $i');  // 0부터 2까지 출력
  }

  // while 루프
  int count = 0;
  while (count < 3) {
    print('While 루프: $count');  // 0부터 2까지 출력
    count++;
  }

  // do-while 루프
  int num = 0;
  do {
    print('Do-while 루프: $num');  // 최소한 한 번은 실행됨
    num++;
  } while (num < 3);  // 0부터 2까지 출력

  // for-in 루프 (컬렉션 순회)
  List<String> fruits = ['사과', '바나나', '오렌지'];
  for (String fruit in fruits) {
    print('For-in 루프: $fruit');  // 리스트의 각 요소 출력
  }
}
```

### 03 List, Map, Set

#### 1. List 선언, 응용

```dart
void main() {
  List<String> myList = ['Dave', 'Jimmy'];  // 문자열 리스트 선언 및 초기화
  print(myList);  // ['Dave', 'Jimmy'] 출력
  myList.add('David');  // 리스트에 'David' 추가
  print(myList);  // ['Dave', 'Jimmy', 'David'] 출력

  print(myList[0]);  // 첫 번째 요소 'Dave' 출력

  myList[0] = 'Jane';  // 첫 번째 요소를 'Jane'으로 변경

  myList.remove('Jane');  // 'Jane' 요소 제거
  print(myList);  // ['Jimmy', 'David'] 출력
  myList.removeAt(1);  // 인덱스 1의 요소 제거
  print(myList);  // ['Jimmy'] 출력

  print(myList.length);  // 리스트의 길이 1 출력
}
```

#### 2. Set 선언, 응용

##### ㄱ) intersection 교집합

```dart
void main() {
  var num1 = {1, 3, 5, 7};  // 첫 번째 집합
  var num2 = {2, 3, 6, 7};  // 두 번째 집합

  var num3 = num1.intersection(num2);  // 두 집합의 교집합
  print(num3);  // {3, 7} 출력
}
```

##### ㄴ) difference 차집합

```dart
void main() {
  var num1 = {1, 3, 5, 7};  // 첫 번째 집합
  var num2 = {2, 3, 6, 7};  // 두 번째 집합

  var num4 = num1.difference(num2);  // num1에서 num2를 뺀 차집합
  print(num4);  // {1, 5} 출력
}
```

### 05 객체 지향

#### 1. 클래스 생성

```dart
class Car {
  String brand = 'NOT';  // 기본 브랜드 값

  Car(String brand) {  // 생성자
    this.brand = brand;  // 인스턴스 변수에 매개변수 값 할당
  }

  String getBrand() {  // 브랜드를 반환하는 메서드
    return this.brand;
  }
}

void main() {
  Car myCar = Car('Tesla');  // Car 객체 생성
  print(myCar.getBrand());  // 'Tesla' 출력
}
```

#### 2. 상속

```dart
class Car {
  String brand = 'car';  // 기본 브랜드
  String color = 'red';  // 기본 색상

  Car(this.brand);  // 생성자

  String getBrand() {  // 브랜드 반환 메서드
    return this.brand;
  }

  String getDesc() {  // 설명 반환 메서드
    return 'This is a car';
  }
}

class ElecCar extends Car {  // Car 클래스를 상속받는 ElecCar 클래스
  String color = 'blue';  // ElecCar의 기본 색상

  ElecCar(String brand) : super(brand);  // 부모 클래스의 생성자 호출

  @override
  String getDesc() {  // 메서드 오버라이드
    return 'This is an electric car';
  }

  String getColor() {  // 새로운 메서드
    return '${this.color}, ${super.color}';  // 자식과 부모의 색상 반환
  }
}

void main() {
  ElecCar tesla = ElecCar('Tesla');  // ElecCar 객체 생성
  print(tesla.getBrand());  // 'Tesla' 출력
  print(tesla.getDesc());  // 'This is an electric car' 출력
  print(tesla.getColor());  // 'blue, red' 출력
}
```
