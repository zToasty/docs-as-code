# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    actor Student as Студент
    participant App as Приложение
    participant Search as Поиск по материалу
    participant AI as ИИ-компонент

    Student->>App: Отправляет вопрос по документу
    App->>Search: Передаёт вопрос и документ
    Search-->>App: Возвращает подходящие фрагменты и страницы
    App->>AI: Передаёт вопрос и найденные фрагменты
    AI-->>App: Формирует ответ на их основе
    App-->>Student: Показывает ответ и источник
```

## Диаграмма классов

```mermaid
classDiagram
    class Student {
        +int id
        +string name
        +uploadDocument()
        +askQuestion()
    }

    class Document {
        +int id
        +string filename
        +string content
        +int pageCount
    }

    class Question {
        +int id
        +string text
    }

    class Answer {
        +string text
        +string sourcePage
        +string sourceExcerpt
    }

    Student "1" --> "*" Document : загружает
    Student "1" --> "*" Question : задаёт
    Question "1" --> "0..1" Answer : получает
    Answer "*" --> "1" Document : ссылается на
```
