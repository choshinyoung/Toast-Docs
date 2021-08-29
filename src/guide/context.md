# 컨텍스트

컨텍스트를 활용해 커맨드를 커스터마이징할 수 있습니다.

## 컨텍스트 위치 변경

아래 커맨드는 일반적인 커맨드입니다.
```cs
ToastCommand.CreateFunc<ToastContext, float, float, float>("add", (ctx, x, y) => x + y)
```
```js
> add 1 2
3
```

하지만 ToastContext의 위치를 바꾸면 커맨드의 가독성을 높일 수 있습니다.
```cs
ToastCommand.CreateFunc<float, ToastContext, float, float>("add", (x, ctx, y) => x + y)
```
```js
> 1 add 2
3
```

현재 코드는 앞에 있는 커맨드가 먼저 실행됩니다.
```js
> 1 add 2 mul 3
9
```

하지만 CreateFunc 메서드에서 우선순위를 지정해 먼저 실행할 커맨드를 정할 수 있습니다.
```cs
/*
ToastCommand.CreateFunc<float, ToastContext, float, float>("mul", (x, ctx, y) => x * y)
*/
ToastCommand.CreateFunc<float, ToastContext, float, float>("mul", (x, ctx, y) => x * y, 1)
```
```js
> 1 add 2 mul 3
7
```

우선순위를 지정하지 않은 커맨드의 기본 우선순위 값은 0입니다. 우선순위가 높은 커맨드가 먼저 실행됩니다.


컨텍스트 위치 예제는 [여기서](https://github.com/choshinyoung/Toast/blob/master/Examples/Calculator.cs) 볼 수 있습니다.


## 커스텀 컨텍스트

커스텀 컨텍스트를 사용하면 커맨드에 사용자 지정 데이터를 간단히 전달할 수 있습니다.

먼저 ToastContext를 상속하는 클래스를 만듭니다.
```cs
class CustomContext : ToastContext
{
    // 커맨드로 전달할 값입니다.
    public readonly int Value;

    // 클래스 생성 때 값을 설정합니다.
    public CustomContext(int value)
    {
        Value = value;
    }
}
```

ToastContext 대신 CustomContext를 파라미터로 사용하는 커맨드를 만듭니다.
```cs
toaster.AddCommand(ToastCommand.CreateFunc<CustomContext, int>("getValue", (ctx) => ctx.Value));
```

이제 커맨드를 실행할 때 컨텍스트를 지정합니다.
```cs
toaster.Execute("getValue add 2", new CustomContext("10")); // 12
```

커스텀 컨텍스트 예제는 [여기서](https://github.com/choshinyoung/Toast/blob/master/Examples/CustomContextExample.cs) 볼 수 있습니다.