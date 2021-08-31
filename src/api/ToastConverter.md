# ToastConverter

## Method

```cs
MethodInfo Method { get; private init; }
```

컨버터를 실행할 때 실행되는 메서드입니다.

## From

```cs
Type From { get; private init; }
```

변환할 대상의 타입입니다.

## To

```cs
Type To { get; private init; }
```

컨버터가 리턴할 값의 타입입니다.

## Create

```cs
static ToastConverter Create<T, TResult>(Func<ToastContext, T, TResult> method)
```

`T` 타입의 값을 `TResult`타입으로 변환하는 컨버터를 만드는 메서드입니다.