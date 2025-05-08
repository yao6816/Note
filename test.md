```mermaid
graph TD
    A[開始] --> B{輸入行駛里程 (meters)}
    B --> C{meters < 1500?}
    C -- 是 --> D[fee = 85]
    D --> E[輸出車資 (fee)]
    C -- 否 --> F[meters - 1500]
    F --> G[餘數 = (meters - 1500) % 200]
    G --> H{餘數 == 0?}
    H -- 是 --> I[fee = 85 + 5 * (meters - 1500) / 200]
    I --> E
    H -- 否 --> J[fee = 85 + 5 * (1 + (meters - 1500) / 200)]
    J --> E
    E --> K[結束]
```
