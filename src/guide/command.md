# 커맨드

커맨드를 만드는 방법을 설명합니다.

## 커맨드 생성

```cs
toaster.AddCommand(ToastCommand.CreateAction<ToastContext, string>("print", (ctx, x) => Console.WriteLine(x)));

toaster.AddCommand(ToastCommand.CreateFunc<ToastContext, string>("input", (ctx) => Console.ReadLine()));
```

토스트 커맨드에는 Action과 Func 두 종류가 있습니다.

`< >` 안에 적힌 타입 파라미터는 커맨드의 파라미터 또는 리턴 타입을 지정합니다.

`ToastContext`는 toaster 관련 데이터를 전달하는, 실제 시용시 전달되지 않는 파라미터입니다. `ToastContext`는 타입 파라미터에 단 한 개가 있어야됩니다.

## Action 커맨드

Action 커맨드는 리턴값이 없는 커맨드입니다.

```cs
ToastCommand cmd = ToastCommand.CreateAction<ToastContext, object>("print", (ctx, x) => Console.WriteLine(x));
```
오브젝트를 콘솔에 출력하는 코드입니다. 아래처럼 사용할 수 있습니다.
```js
> print "This is an Action command."
This is an Action command.
```

## Func 커맨드

Func 커맨드는 리턴값이 없는 커맨드입니다.
타입 파라미터의 마지막 타입이 리턴값의 타입입니다.

```cs
toaster.AddCommand(ToastCommand.CreateFunc<ToastContext, string>("input", (ctx) => Console.ReadLine()));
```
콘솔에서 입력을 받아 출력하는 코드입니다.