## 클래스 객체

### 클래스 객체 선언
```xml
@ $$<클래스명> #
    <선언문>...
!#;
```
mcCmd에서의 클래스는 별도의 `코드 영역`입니다. 전역에서 사용하는 모든 선언문을 클래스 내부에서 사용할 수 있습니다.

**호출문 또한 사용은 가능하나 일부 클래스 전용 호출문 이외에는 추천하지 않습니다**

**ex)**
```k
@ $$human #
    @ name[type=string,value=""];
    @ age[type=int,value=0];

    @ /printName #
        /say @name;
    !#;
!#;
```

### 접근 제어자
클래스의 코드 영역 내부에서는 함수 형태로 접근 제어자를 지정할 수 있습니다.

```xml
/public <변수>/<함수>;
/private <변수>/<함수>;
```

접근 제어자 함수에서는 함수를 함수 변수로 변환하지 않고 함수 자체를 받아올 수 있습니다.

```k
@ $$human #
    @ name[type=string,value=""];
    /private name;
    @ age[type=int,value=0];
    /public age;

    @ /printName #
        /say @name;
    !#;
    /public printName;
!#;
```

**`static` `protected` 굳이 필요함?**

### 생성자
`/constructor`의 이름으로 함수를 생성하면 생성자로 인식됩니다.
```k
@ $$human #
    @ name[type=string,value=""];
    /private name;
    @ age[type=int,value=0];
    /public age;

    @ /constructor name_@string age_@int #
        name = _name;
        age = _age;
    !#;

    @ /printName #
        /say @name;
    !#;
    /public printName;
!#;
```

### 클래스 사용
선언된 클래스는 변수 타입으로 사용될 수 있습니다.
```k
@ cls[type=human,value=()];
```

생성자의 매개변수는 value에 `()`로 묶어서 담을 수 있습니다.
```k
@ cls[type=human,value=("steve", 17)];
```

클래스 내부의 함수와 변수는 다음과 같이 호출할 수 있습니다.
```xml
$$<클래스명>@<내부값>
```

**ex)**

변수
```k
/say $$human@age;
```
함수
```k
/$$human@printName;
```