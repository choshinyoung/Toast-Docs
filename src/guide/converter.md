# 컨버터

컨버터를 사용하면 필요한 타입에 맞춰 자동으로 타입을 변환시킬 수 있습니다.

컨버터를 만들 때는 타입 파라미터에 대상의 타입과 변환할 타입을 지정해야합니다.
람다 식의 파라미터는 `ToastContext` 오브젝트와 변환할 대상 오브젝트입니다.

```cs
// int를 bool로 변환하는 컨버터를 추가합니다.
toaster.AddConverter(ToastConverter.Create<int, bool>((ctx, x) => x != 0));
```

이제 `bool` 타입을 파라미터로 사용하는 커맨드에서 `int`를 사용할 수 있습니다.
```cs
toaster.AddCommand(ToastCommand.Create<ToastContext, bool, bool, bool>("and", (ctx, x, y) => x && y);
```
```js
> and 1 true
true
```