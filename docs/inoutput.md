## 입출력문
### 입력
입력을 받을때는 `/replaceitem` 함수를 사용합니다.
```xml
/replaceitem <입력받을변수>;
```
**ex)**
```k
@ input[type=int,value=0];

/replaceitem @input;
```
입력 받으면 해당 변수의 원래 값은 초기화됩니다.

### 출력
출력을 할떄는 `/say` 함수를 사용합니다.
```xml
/say <문자열>/@<변수명>
```
**ex)**
```k
/say "Hello! Honkai Impact!";
```