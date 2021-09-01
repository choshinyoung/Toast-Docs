# ToastContext

커맨드 또는 컨버터에 `Toaster` 오브젝트를 전달하는 클래스입니다. 이 클래스를 상속하는 커스텀 컨텍스트를 만들어 특정 데이터를 전달할 수 있습니다.

## Toaster

```cs
Toaster Toaster { get; internal set; }
```

현재 이 커맨드 또는 컨버터를 실행중인 토스터 오브젝트입니다.

## ToastContext()

```cs
ToastContext()
ToastContext(Toaster toaster)
```

컨텍스트를 생성합니다. `toaster`를 지정하지 않았다면 실행 시 자동으로 실행중인 토스터를 대입합니다.