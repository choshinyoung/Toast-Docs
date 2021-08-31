# BasicConverters

기본적인 컨버터를 미리 정의해 모아둔 클래스입니다.

## All

```cs
static ToastCommand[] All
```

모든 기본 컨버터를 모아둔 배열입니다.

## StringToNumber

```cs
static ToastConverter[] StringToNumber
```

문자열을 숫자로 변환하는 컨버터를 모아둔 배열입니다.

### StringToByte

```cs
(ToastContext, string) => byte)
```

`string`을 `byte`로 변환합니다.

### StringToSbyte

```cs
(ToastContext, string) => sbyte)
```

`string`을 `sbyte`로 변환합니다.

### StringToShort

```cs
(ToastContext, string) => short)
```

`string`을 `short`로 변환합니다.

### StringToUshort

```cs
(ToastContext, string) => ushort)
```

`string`을 `ushort`로 변환합니다.

### StringToInt

```cs
(ToastContext, string) => int)
```

`string`을 `int`로 변환합니다.

### StringToUint

```cs
(ToastContext, string) => uint)
```

`string`을 `uint`로 변환합니다.

### StringToLong

```cs
(ToastContext, string) => long)
```

`string`을 `long`으로 변환합니다.

### StringToUlong

```cs
(ToastContext, string) => ulong)
```

`string`을 `ulong`으로 변환합니다.

### StringToFloat

```cs
(ToastContext, string) => float)
```

`string`을 `float`로 변환합니다.

### StringToDouble

```cs
(ToastContext, string) => double)
```

`string`을 `double`로 변환합니다.

### StringToDecimal

```cs
(ToastContext, string) => decimal)
```

`string`을 `decimal`로 변환합니다.

## Others

```cs
static ToastConverter[] Others
```

기타 컨버터를 모아둔 배열입니다.

### StringToObjectArray

```cs
(ToastContext, string) => object[])
```

`string`을 `char` 배열로 변환합니다.

### StringToChar

```cs
(ToastContext, string) => char)
```

길이가 1인 문자열을 `char`로 변환합니다.