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
speech-analyst-bot/
├── .env                    # Файл окружения (токены)
├── bot.py                  # Основной скрипт бота
├── audio_processor.py      # Обработка аудио
├── text_analyzer.py        # Анализ текста
├── report_generator.py     # Генерация отчетов
├── config.py               # Конфигурация
├── requirements.txt        # Зависимости
└── README.md               # Инструкции
