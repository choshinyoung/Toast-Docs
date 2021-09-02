# ToastCommand

## Name

```cs
string Name { get; private init; }
```

커맨드의 이름입니다. 커맨드가 이 이름을 통해 실행됩니다.

## Method

```cs
MethodInfo Method { get; private init; }
```

커맨드를 실행할 때 실행되는 메서드입니다.

## Parameters

```cs
Type[] Parameters { get; private init; }
```

파라미터들의 타입입니다.

## Return

```cs
Type Return { get; private init; }
```

리턴값의 타입입니다.

## NamePosition

```cs
int NamePosition { get; private init; }
```

타입 파라미터에서 컨텍스트의 위치입니다. 이 값에 따라 커맨드의 이름과 파라미터의 순서가 달라집니다.

## Priority

```cs
int Priority { get; private init; }
```

커맨드의 우선순위입니다. 이 값이 높은 커맨드가 다른 커맨드보다 먼저 실행됩니다.

## CreateAction()

```cs
static ToastCommand CreateAction<T1>(string name, Action<T1> method, int priority = 0)
static ToastCommand CreateAction<T1, T2>(string name, Action<T1, T2> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3>(string name, Action<T1, T2, T3> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4>(string name, Action<T1, T2, T4, T4> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5>(string name, Action<T1, T2, T3, T4, T5> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6>(string name, Action<T1, T2, T3, T4, T5, T6> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7>(string name, Action<T1, T2, T3, T4, T5, T6, T7> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15> method, int priority = 0)
static ToastCommand CreateAction<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, T16>(string name, Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, T16> method, int priority = 0)
```

리턴값이 없는 커맨드를 만듭니다.

## CreateFunc()

```cs
static ToastCommand CreateFunc<T1, TResult>(string name, Func<T1, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, TResult>(string name, Func<T1, T2, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, TResult>(string name, Func<T1, T2, T3, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, TResult>(string name, Func<T1, T2, T3, T4, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, TResult>(string name, Func<T1, T2, T3, T4, T5, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, TResult> method, int priority = 0)
static ToastCommand CreateFunc<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, T16, TResult>(string name, Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, T11, T12, T13, T14, T15, T16, TResult> method, int priority = 0)
```

리턴값이 있는 커맨드를 만듭니다.