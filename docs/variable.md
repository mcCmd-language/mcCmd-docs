## 변수
mcCmd의 변수 문법은 마인크래프트 명령어의 [target selector](https://learn.microsoft.com/en-us/minecraft/creator/documents/targetselectors) 를 모티브로 구성되었습니다.
<br> **ex) `@a` `@p` `@e` `@s`**

### 변수 선언
```xml
@ <변수명>[type=<자료형>,value=<값>];
```
변수 선언에는 [Selector Parameter](https://learn.microsoft.com/en-us/minecraft/creator/documents/targetselectors#selector-parameters)형식이 필수적입니다.

<b>예시</b>
```k
@ num[type=int,value=1];
```

### 변수 호출
```xml
/say @<변수명>;
```
**예시**
```k
/say @num;
```

### 마크처럼 사용하기
```k
@ p[type=string,value="steve"];

/say @p; //steve
```

### 문자열 안에 변수를 넣을때
문자열에 변수가 들어갈떄에는 변수명 뒤에 `*`를 넣어서 구분해줘야합니다.
```k
/say "I'm @p*"; //I'm steve
```

### 문자열 안에 @를 사용하려고 할떄
```k
"this is \@"
```