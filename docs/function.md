## 함수
mcCmd의 함수는 마인크래프트의 명령어 문법을 모티브로 구성되었습니다.

### 함수 선언
```xml
@ /<함수명> <매개변수>... <코드블럭>;
```
함수명 뒤에 매개변수는 갯수에 상관 없이 넣을 수 있으며 각 매개변수는 띄어쓰기로 구분됩니다. 인수를 전부 받은 후 마지막에 함수의 구현을 정의하는 코드블럭이 필요합니다.

**매개변수는 `변수명@형식`으로 받아옵니다**
```k
arg1@int
```

**코드블럭 예시**
```k
#
    /say "yes";
!#
```
**C 언어와 비교**
|mcCmd|C|
|---|---|
|`#`|`{`|
|`!#`|`}`|

**함수 선언 예시**
```k
@ /tell player@string message@string #
    /say "@player* said \"@message*\"";
!#;
```
**주의! 함수 선언에도 `세미콜론(;)`은 반드시 필요합니다!**

### 함수 호출
```xml
/<함수명> <매개변수>...;
```
**예시**
```k
@ p[type=string,value="steve"];

/tell @p "yeah! nice!";
```

### 매개변수 커스텀하기
[Selector Parameter](https://learn.microsoft.com/en-us/minecraft/creator/documents/targetselectors#selector-parameters) 형식을 사용하여 매개변수에도 조건이나 정보를 담을 수 있습니다.
#### nullable
정해진 값 대신 `null`을 받을 수 있습니다.
```c
@ /test arg1@int[nullable=true] #!#;
```
#### 기본값 넣기
값이 `null`일떄 `default`의 값으로 바꿉니다.
```c
@ /test arg1@int[default=5] #!#;
```