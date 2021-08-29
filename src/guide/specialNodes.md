# 특수 노드

커맨드의 파라미터로 사용할 수 있는 특수 노드들입니다.

## FunctionNode

`FunctionNode`를 사용해 함수 타입의 값을 파라미터로 사용할 수 있습니다.
`Toaster`의 `ExecuteFunction` 메서드로 함수를 실행할 수 있습니다.

```cs
ToastCommand.CreateAction<ToastContext, int, FunctionNode>("repeat", (ctx, x, y) => {
    for (int i = 0; i < x; i++) {
        ctx.Toaster.ExecuteFunction(y, new object[] { i }, ctx);
    }
})
```
```js
> repeat 5 (x){ print x }
0
1
2
3
4
```

## CommandNode

`CommandNode`를 커맨드의 파라미터로 사용하면 파싱된 노드를 실행 전에 가져와 사용할 수 있습니다.
커맨드 노드를 사용하면 삼항 연산자를 만들거나 복잡한 커맨드의 가독성을 높일 수 있습니다.

```cs
ToastCommand.CreateFunc<ToastContext, bool, object, object>("if", (ctx, x, y) => x ? y : null)
ToastCommand.CreateFunc<CommandNode, ToastContext, object, object>("else", (x, ctx, y) => {
    if (x.Command.Name != "if") {
        throw new Exception();
    }

    if ((bool)ctx.Toaster.ExecuteNode(x.Parameters[0])) {
        return ctx.Toaster.ExecuteNode(x.Parameters[1]);
    }
    else {
        return y;
    }
})
```
```js
> if true 1
1
> if false 1

> if true 1 else 2
1
> if false 1 else 2
2
```

## VariableNode

파라미터가 한 개도 없는 커맨드는 변수 노드로 취급됩니다.
변수 노드는 키워드, 속성이나 enum 등으로 사용할 수 있습니다.

```cs
ToastCommand.CreateFunc<VariableNode, ToastContext, object, string>("of", (x, ctx, y) => {
    if (x.Name == "type") {
        return y.GetType().Name;
    }
    else {
        throw new Exception();
    }
})
```
```js
> type of "string"
String
```