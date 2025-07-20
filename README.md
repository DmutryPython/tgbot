```mermaid
stateDiagram-v2
    [*] --> Start
    Start --> WaitingText: /start
    WaitingText --> WaitingVoice: Текстовое сообщение
    WaitingText --> [*]: /cancel
    WaitingVoice --> WaitingText: /start (ошибка)
    WaitingVoice --> Result: Голосовое сообщение (успех)
    WaitingVoice --> WaitingVoice: Голосовое сообщение (ошибка)
    WaitingVoice --> [*]: /cancel
    Result --> [*]: Предложение /start
```
