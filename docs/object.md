## 일반 객체

### 일반 객체 선언
```xml
@ $<객체명>[
    <key>@<자료형>=<value>...
];
```
객체에는 값과 해당 값을 특정하기 위한 key값과 자료형이 필요합니다.

**ex)**
```k
@ $obj[
    value1@int = 1,
    value2@int = 2,
    value3@string = "hahaha",
]
```

### 일반 객체 호출
```xml
$<객체명>@<key>
```

**ex)**
```k
@ objVar[type=int,value=$obj@value1];

/say $obj@value3;
```