```mermaid
classDiagram
    class Person {
        +name: string
        +age: number
        +address: Address
    }
    class Address {
        +street: string
        +city: string
        +state: string
        +zip: string
    }
    Person "1" --> "0..*" Address
```

```mermaid
classDiagram
    class User {
        +id: int
        +name: string
        +email: string
        +register(date: datetime): void
        +login(password: string): bool
    }

    class Task {
        +id: int
        +title: string
        +description: string
        +status: string
        +due_date: datetime
        +assign(user: User): void
        +complete(): void
    }

    class Project {
        +id: int
        +name: string
        +deadline: datetime
        +add_task(task: Task): void
        +remove_task(task: Task): void
    }

    class Notification {
        +id: int
        +message: string
        +sent_at: datetime
        +send(user: User): void
    }

    User "1" --> "0..*" Task : owns
    Task "1" --> "1" Project : belongs to
    Task "1" --> "0..1" Notification : triggers
    User "1" --> "0..*" Notification : receives
```

```mermaid
graph LR
A[Start] --> B{Is the user logged in?}
B -- Yes --> C[Display dashboard]
B -- No --> D[Redirect to login]
D --> E[End]
```

```mermaid
sequenceDiagram
    participant User
    participant Server
    User->>Server: Request data
    Server->>Server: Process data
    Server-->>User:
```

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title My Gantt Chart
    section Section
    Task 1 :done, des1, 2022-01-01, 2022-01-03
    Task 2 :active, des2, 2022-01-03, 2022-01-05
    Task 3 :pending, des3, after des2, 3d
```

```mermaid
classDiagram
    class User {
        +id: int
        +name: string
        +email: string
        +password: string
        ++authenticate(password: string): bool
        ++getFullName(): string
    }
    class Post {
        +id: int
        +title: string
        +content: string
        +userId: int
        ++getUser(): User
    }
    User --> "*" Post
```

```mermaid
erDiagram
    User ||--o{ Order : places
    User {
        id int
        name string
        email string
        password string
    }
    Order {
        id int
        userId int
        total float
    }
    Product ||--o{ Order : contains
    Product {
        id int
        name string
        price float
    }
```

```mermaid
graph TD
    A[Начало] --> B{Условие?}
    B -- Да --> C[Действие 1]
    B -- Нет --> D[Действие 2]
    C --> E[Конец]
    D --> E
```

```mermaid
sequenceDiagram
    participant User
    participant API
    participant DB

    User->>API: Запрос данных
    API->>DB: Выполнить SQL-запрос
    DB-->>API: Вернуть данные
    API-->>User: Ответ
```


```mermaid
gantt
    title Проект разработки
    dateFormat  YYYY-MM-DD
    section Разработка
        Требования :a1, 2024-01-01, 5d
        Дизайн :a1, 2024-01-06, 7d
    section Тестирование
        Юнит-тесты :2024-01-13, 5d
        Интеграционные тесты :2024-01-18, 7d
```

```mermaid
tree
    root [Корень]
    root --> child1 [Дочерний 1]
    root --> child2 [Дочерний 2]
    child1 --> leaf1 [Лист 1]
    child2 --> leaf2 [Лист 2]
```

```mermaid
timeline
    title История проекта
    2023-01 --> 2023-06 : Фаза 1
    2023-07 --> 2023-12 : Фаза 2
    2024-01 --> 2024-06 : Фаза 3
```