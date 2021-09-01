# Toaster

## AddCommand()

```cs
void AddCommand(params ToastCommand[] commands)
```

토스터에 커맨드를 등록합니다.

## RemoveCommand()

```cs
void RemoveCommand(params ToastCommand[] commands)
```

등록된 커맨드를 삭제합니다.

## GetCommand()

```cs
ToastCommand GetCommand(string name)
```

커맨드를 이름으로 가져옵니다.

## GetCommands()

```cs
IReadOnlyList<ToastCommand> GetCommands()
```

등록된 모든 커맨드를 가져옵니다.

## AddConverter()

```cs
void AddConverter(params ToastConverter[] converters)
```

토스터에 컨버터를 등록합니다.

## RemoveConverter()

```cs
void RemoveConverter(params ToastConverter[] converters)
```

등록된 컨버터를 삭제합니다.

## GetConverters()

```cs
IReadOnlyList<ToastConverter> GetConverters()
```

등록된 모든 컨버터를 가져옵니다.

## TypeAlias

```cs
readonly Dictionary<string, Type> TypeAliases = {
    { "text", typeof(string) },
    { "number", typeof(long) },
    { "float", typeof(float) },
    { "bool", typeof(bool) },
    { "list", typeof(object[]) }
}
```

타입의 별명입니다. [BasicCommands.Convert](BasicCommands.md#Convert)에서 사용됩니다.

## Execute()

```cs
object Execute(string line, ToastContext context = null)
```

커맨드 라인을 실행합니다. context를 생략하면 자동으로 기본 컨텍스트를 생성합니다.

## ExecuteCommand()

```cs
object ExecuteCommand(ToastCommand cmd, object[] parameters, ToastContext context = null)
```

단일의 토스트커맨드를 실행합니다.

## ExecuteConverter()

```cs
object ExecuteConverter<T>(object obj, ToastContext context = null)
object ExecuteConverter(object obj, Type type, ToastContext context = null)
object ExecuteConverter(ToastConverter cvt, object parameter, ToastContext context = null)
```

오브젝트의 타입을 변환합니다.

## ExecuteFunction()

```cs
object ExecuteFunction(FunctionNode func, object[] parameters, ToastContext context)
```

`FunctionNode`를 실행합니다.

## ExecuteNode()

```cs
object ExecuteNode(INode node, ToastContext context = null)
```

파싱된 노드를 실행합니다.

## Parse()

```cs
INode Parse(string line)
```

커맨드 라인을 파싱합니다.