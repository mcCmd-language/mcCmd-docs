## 고차 함수
### 함수를 담은 변수 만들기
```k
@ /test arg1@int #
!#;

@ func[type=func,value=test];
```
함수를 담은 변수는 함수의 기능을 가지긴 하나 일반적인 함수와 같이 `/`로 호출할 수 없습니다. 대신 `/call` 함수를 사용하여 호출할 수 있습니다.

```xml
/call @<변수명> <매개변수>...;
```
**ex)**
```k
/call @func 1;
```

### 함수 변수 자체 선언하기
```k
@ /func[type=func,value=#
    /say "ee";
!#];
```
자체 선언된 함수 변수는 매개변수를 받을 수 없습니다.

### 함수 변수의 사용

함수가 담긴 변수는 다른 함수의 매개변수로 넘길 수 있습니다.
**일반 함수는 불가능합니다!**

```k
@ /test ev@func #
    /call @ev;
!#;

@ func[type=func,value=#
    /say "cyper angel";
!#];

/test @func;
```