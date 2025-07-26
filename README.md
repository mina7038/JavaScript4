# JavaScript4

## **✅ JavaScript 객체 문법**

- 객체는 **중괄호 `{}`** 로 시작하고 끝남
- **프로퍼티(속성)** 와 **메소드(함수)** 로 구성됨
- 프로퍼티는 **키(key)** 와 **값(value)** 의 쌍으로 이루어짐
- 각 프로퍼티는 **쉼표(,)** 로 구분함

```jsx
const obj = {
  name: '삐삐',
  age: 9,
  say: function() {
    console.log('이름은 ' + this.name + ' 나이는 ' + this.age);
  }
};

// 프로퍼티 접근
obj.name;    // 삐삐
obj['age'];  // 9

// 메소드 호출
obj.say();   // 이름은 삐삐 나이는 9
```

## **✅** 객체를 만드는 방법

### 1. **객체 리터럴(값)**

```jsx
var person = {
  name: 'Lee',
  gender: 'male',
  sayHello: function () {
    console.log('Hi! My name is ' + this.name);
  }
};

console.log(typeof person); // object
console.log(person);        // { name: "Lee", gender: "male", sayHello: ƒ }
person.sayHello();          // Hi! My name is Lee
```

### 2. **Object 생성자 함수**

```jsx
// 빈 객체 생성
var person = new Object();

// 프로퍼티 추가
person.name = 'Lee';
person.gender = 'male';
person.sayHello = function () {
  console.log('Hi! My name is ' + this.name);
};

console.log(typeof person); // object
console.log(person);        // { name: "Lee", gender: "male", sayHello: ƒ }
person.sayHello();          // Hi! My name is Lee
```

### 3. 함수형 객체 **(프로토타입)**

```jsx
function Person(name, gender) {
  this.name = name;
  this.gender = gender;
  this.sayHello = function () {
    console.log('Hi! My name is ' + this.name);
  };
}

// 인스턴스 생성
var person1 = new Person('Lee', 'male');
var person2 = new Person('Kim', 'female');

person1.sayHello(); // Hi! My name is Lee
person2.sayHello(); // Hi! My name is Kim
```

### 4. 객체 값 출력 (for in 문)

```jsx
var grades = { 'cemy': 10, 'stormy': 6, 'windy': 80 };

for (var key in grades) {
  document.write('key: ' + key + ' value: ' + grades[key] + '<br>');
}
```

### 5. 객체 사용

```jsx
var grades = {
  list: { 'cemy': 10, 'stormy': 6, 'windy': 80 },
  show: function () {
    for (var name in this.list) {
      document.write(name + ' : ' + this.list[name] + '<br>');
    }
  }
};

grades.show();
```
