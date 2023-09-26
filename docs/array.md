## 배열

### 배열 선언
```xml
@ <배열명>[type=array,element=<요소의자료형>,value=(<요소>...),size=<배열크기>,constraintSize=true];
```
`constraintSize` - 배열 크기가 선언떄 지정된 값으로 고정됩니다. (안적어도 됨)

`size` - 배열 크기를 지정합니다. (안적어도 됨)

**ex)**
```k
@ arr[type=array,element=int,size=3,value=(1, 2, 3),constraintSize=true];
```

### 배열 호출
```k
/say @arr[element=1];
```
