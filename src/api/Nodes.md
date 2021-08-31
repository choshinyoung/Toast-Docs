# Nodes

## INode

커맨드 라인을 파싱하면 이 타입의 값을 리턴합니다. `ValueNode`, `TextNode`, `ListNode`, `FunctionNode`, `VariableNode`, `CommandNode`, `GroupNode`는 이 인터페이스를 상속합니다.

## ValueNode

`number`, `float`, `bool` 등을 저장하는 클래스입니다.

### Value

```cs
readonly object Value
```

## TextNode

문자열을 저장하는 클래스입니다. 문자열 보간을 사용할 수 있습니다.

### Values

```cs
readonly object[] Values
```

문자열 또는 문자열 보간에 사용된 값을 저장합니다.

## ListNode

리스트를 저장하는 클래스입니다.

### Value

```cs
readonly INode[] Value
```

## FunctionNode

함수를 저장하는 클래스입니다.

### Parameters

```cs
readonly string[] Parameters
```

함수의 파라미터 변수의 이름들입니다.

### Lines

```cs
readonly INode[] Lines
```

함수의 본문입니다.

## VariableNode

파라미터가 없는 커맨드를 저장하는 클래스입니다. `CommandNode`와 똑같이 취급될 수 있습니다.

### Name

```cs
readonly string Name
```

변수 또는 커맨드의 이름입니다.

## CommandNode

커맨드를 저장하는 클래스입니다.

### Command

```cs
readonly ToastCommand Command
```

해당 커맨드가 실행할 `ToastCommand`입니다.

### Parameters

```cs
readonly INode[] Parameters
```

커맨드의 인자(Argument)입니다.

## GroupNode

`(`, `)`로 묶인 `INode`를 저장하는 클래스입니다.

### Values

```cs
readonly INode[] Values
```