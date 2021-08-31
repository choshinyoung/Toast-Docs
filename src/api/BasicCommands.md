# BasicCommands

기본적인 커맨드를 미리 정의해둔 클래스입니다.

## All

```cs
static ToastCommand[] All
```

모든 기본 커맨드를 모아둔 배열입니다.

## Literals

```cs
static ToastCommand[] Literals
```

리터럴 커맨드를 모아둔 배열입니다.

### Null

```cs
Func("null", (ToastContext) => null)
```
```js
> null
```

`null`을 리턴합니다.

### True

```cs
Func("true", (ToastContext) => bool)
```
```js
> true
```

`true`를 리턴합니다.

### False

```cs
Func("false", (ToastContext) => bool)
```
```js
> false
```

`false`를 리턴합니다.

## Operators

```cs
static ToastCommand[] Operators
```

연산자 커맨드를 모아둔 배열입니다.

### Addition

```cs
Func("add", (float, ToastContext, float) => float)
```
```js
> x add y
```

덧셈 연산자입니다.

### Subtraction

```cs
Func("sub", (float, ToastContext, float) => float)
```
```js
> x sub y
```

뺄셈 연산자입니다.

### Multiplication

```cs
Func("mul", (float, ToastContext, float) => float)
```
```js
> x mul y
```

곱셈 연산자입니다.

### Division

```cs
Func("div", (float, ToastContext, float) => float)
```
```js
> x div y
```

나눗셈 연산자입니다.

### Modulus

```cs
Func("mod", (float, ToastContext, float) => float)
```
```js
> x mod y
```

나머지 연산자입니다.

### FloorDivision

```cs
Func("floorDiv", (int, ToastContext, int) => int)
```
```js
> x floorDiv y
```

정수 나눗셈 연산자입니다.

### Exponentiation

```cs
Func("exp", (float, ToastContext, float) => float)
```
```js
> x exp y
```

x의 y제곱을 리턴합니다.

### Equal

```cs
Func("is", (object, ToastContext, object) => bool)
```
```js
> x is y
```

두 객체가 같은지 확인합니다.

### Greater

```cs
Func("greater", (float, ToastContext, float) => bool)
```
```js
> x greater y
```

x가 y보다 큰지 확인힙니다.

### Less

```cs
Func("less", (float, ToastContext, float) => bool)
```
```js
> x less y
```

x가 y보다 작은지 확인합니다.

### GreaterOrEqual

```cs
Func("greaterEqual", (float, ToastContext, float) => bool)
```
```js
> x greaterEqual y
```

x가 y보다 크거나 같은지 확인힙니다.

### LessOrEqual

```cs
Func("lessEqual", (float, ToastContext, float) => bool)
```
```js
> x lessEqual y
```

x가 y보다 작거나 같은지 확인합니다.

### And

```cs
Func("and", (bool, ToastContext, bool) => bool)
```
```js
> x and y
```

x와 y가 모두 true라면 true를 리턴합니다.

### Or

```cs
Func("or", (bool, ToastContext, bool) => bool)
```
```js
> x or y
```

x와 y 중 하나 이상이 true라면 true를 리턴합니다.

### Not

```cs
Func("not", (ToastContext, bool) => bool)
```
```js
> not x
```

x가 true라면 false를, false라면 true를 리턴합니다.

### BitwiseAnd

```cs
Func("bitAnd", (int, ToastContext, int) => int)
```
```js
> x bitAnd y
```

비트 and 연산자입니다.

### BitwiseOr

```cs
Func("bitOr", (int, ToastContext, int) => int)
```
```js
> x bitOr y
```

비트 or 연산자입니다.

### BitwiseXor

```cs
Func("bitXor", (int, ToastContext, int) => int)
```
```js
> x bitXor y
```

비트 xor 연산자입니다.

### BitwiseNot

```cs
Func("bitNot", (ToastContext, int) => int)
```
```js
> bitNot x
```

비트 not 연산자입니다.

### LeftShift

```cs
Func("lShift", (int, ToastContext, int) => int)
```
```js
> lShift x
```

왼쪽 쉬프트 연산자입니다.

### RightShift

```cs
Func("rShift", (int, ToastContext, int) => int)
```
```js
> rShift x
```

오른쪽 쉬프트 연산자입니다.

## Statements

```cs
static ToastCommand[] Statements
```

선택문, 반복문 커맨드를 모아둔 배열입니다.

### If

```cs
Func("if", (ToastContext, bool, object) => object)
```
```js
> if x y
```

x가 true라면 y를, false라면 null을 리턴합니다.

### Else

```cs
Func("else", (object, ToastContext, object) => object)
```
```js
> if x y else z
```

if와 함께 사용하여, x가 true라면 y를, false라면 z를 리턴합니다.

### While

```cs
Action("while", (ToastContext, INode, FunctionNode))
```
```js
> while x (){

}
```

x가 true인동안 함수를 실행합니다.

### For

```cs
Func("for", (ToastContext, object[], FunctionNode) => object[])
```
```js
> for x (y) {
    
}
```

배열 x의 값을 각각 파라미터 y로 하는 함수 (`(y) { }`)의 실행결과를 모은 배열을 리턴합니다.

## Others

```cs
static ToastCommand[] Others
```

기타 커맨드를 모아둔 배열입니다.

### Print

```cs
Action("print", (ToastContext, object))
```
```js
> print x
```

콘솔에 x를 출력합니다.

### Input

```cs
Func("input", (ToastContext) => string)
```
```js
> input
```

콘솔에서 입력을 받아옵니다.

### Assign

```cs
Action("var", (ToastContext, CommandNode))
```
```js
> var x is y
> var x add y
> var x sub y
> var x mul y
> var x div y
> var x mod y
> var x exp y
> var x floorDiv y
> var x bitAnd y
> var x bitOr y
> var x bitXor y
> var x bitNot y
> var x lShift y
> var x rShift y
```

`var x is y`: y를 리턴하는 커맨드 x를 생성해 등록합니다. 즉 x를 변수처럼 사용할 수 있습니다.

`var x add y`: += 연산자와 같습니다. 그 외의 커맨드도 이 커맨드와 같습니다.

### Convert

```cs
Func("as", (object, ToastContext, VariableNode) => object)
```
```js
> x as y
```

x의 타입을 y로 변환한 값을 리턴합니다.
y에는 [Toaster.TypeAliases](Toaster.md#typealias)를 대입하여 사용할 수 있습니다.

### Execute

```cs
Func("execute", (ToastContext, FunctionNode, object[]) => object)
```
```js
> execute x y
```

함수 x를 실행합니다.

### Random

```cs
Func("random", (ToastContext, int, int) => long)
```
```js
> random x y
```

x 이상 y 미만의 수 중 하나를 랜덤으로 선택합니다.

### RandomChoice

```cs
Func("randomChoice", (ToastContext, object[]) => object)
```
```js
> randomChoice x y
```

배열 x에서 요소 한 개를 랜덤으로 선택합니다.

## Lists

```cs
static ToastCommand[] Lists
```

리스트 관련 커맨드를 모아둔 배열입니다.

### Member

```cs
Func("member", (ToastContext, int, object[]) => object)
```
```js
> member x y
```

배열 y에서 x번째 인덱스의 요소를 리턴합니다.

### Length

```cs
Func("len", (ToastContext, object[]) => int)
```
```js
> len x
```

배열 x의 길이입니다.

### IndexOf

```cs
Func("indexOf", (ToastContext, object[], object) => int)
```
```js
> indexOf x y
```

배열 x에서 요소 y를 찾아 인덱스를 리턴합니다.

### Filter

```cs
Func("filter", (ToastContext, object[], FunctionNode) => object[])
```
```js
> indexOf x (y) {

}
```

배열 x에서 함수 `(y) { }`의 리턴값이 true인 요소만 골라 리턴합니다.

### Map

```cs
Func("map", (ToastContext, object[], FunctionNode) => object[])
```
```js
> map x (y) {

}
```

배열 x의 각 요소를 파라미터로 하는 함수 `(y) { }`의 실행결과를 리턴합니다.

### Combine

```cs
Func("combine", (ToastContext, object[], object[]) => object[])
```
```js
> combine x y
```

두 배열을 합합니다.

### Append

```cs
Func("append", (ToastContext, object, object[]) => object[])
```
```js
> append x y
```

배열 y에 x를 추가합니다.
두 배열을 합합니다.

### Remove

```cs
Func("remove", (ToastContext, object, object[]) => object[])
```
```js
> remove x y
```

배열 y에서 x를 제거합니다.

### Sort

```cs
Func("sort", (ToastContext, object[]) => object[])
```
```js
> sort x
```

배열을 정렬합니다.

### Shuffle

```cs
Func("sort", (ToastContext, object[]) => object[])
```
```js
> shuffle x
```

배열을 랜덤으로 섞습니다.

### Range

```cs
Func("range", (ToastContext, int, int) => object[])
```
```js
> range x y
```

x부터 y개의 수를 배열로 만들어 리턴합니다.

## Strings

```cs
static ToastCommand[] Strings
```

문자열 관련 커맨드를 모아둔 배열입니다.

### Split

```cs
Func("split", (ToastContext, string, string) => object[])
```
```js
> split x y
```

문자열 x를 y를 기준으로 분리합니다.

### Reverse

```cs
Func("reverse", (ToastContext, string) => string)
```
```js
> reverse x
```

문자열 x를 뒤집습니다.

### StartsWith

```cs
Func("startsWith", (ToastContext, string, string) => bool)
```
```js
> startsWith x y
```

문자열 x가 y로 시작하는지 확인합니다.

### EndsWith

```cs
Func("endsWith", (ToastContext, string, string) => bool)
```
```js
> endsWith x y
```

문자열 x가 y로 끝나는지 확인합니다.

### Contains

```cs
Func("contains", (ToastContext, string, string) => bool)
```
```js
> contains x y
```

문자열 x에 y가 포함되는지 확인합니다.

### EndsWith

```cs
Func("endsWith", (ToastContext, string, string) => bool)
```
```js
> endsWith x y
```

문자열 x가 y로 끝나는지 확인합니다.

### Trim

```cs
Func("trim", (ToastContext, string) => string)
```
```js
> trim x
```

문자열 양쪽 끝의 공백을 제거합니다.

### Substring

```cs
Func("substring", (ToastContext, string, int, int) => string)
```
```js
> substring x y z
```

문자열 x의 y번째 문자부터 z개의 문자를 리턴합니다.

### Join

```cs
Func("join", (string, ToastContext, object) => string)
```
```js
> join x y
```

두 문자열을 결합합니다. 만약 y가 배열이라면 x를 분리자로 사용해 y의 요소를 결합합니다.

### Replace

```cs
Func("replace", (ToastContext, string, string, string) => string)
```
```js
> replace x y z
```

문자열 x의 부분 문자열 y를 모두 z로 대체합니다.

### ToUpper

```cs
Func("toUpper", (ToastContext, object) => string)
```
```js
> toUpper x
```

문자열을 모두 대문자로 만듭니다.

### ToLower

```cs
Func("toLower", (ToastContext, object) => string)
```
```js
> toLower x
```

문자열을 모두 소문자로 만듭니다.