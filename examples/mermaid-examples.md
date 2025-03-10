---
marp: true
theme: ./themes/3shake-standard-theme.css
paginate: true
html: true
mermaid: true
math: katex
style: |
  :root {
    --logo-url: url("./assets/images/3shake-logo.png");
  }
  .mermaid {
    display: flex !important;
    justify-content: center !important;
    margin: 2em auto !important;
    background: transparent !important;
  }
  .mermaid svg {
    max-width: 100% !important;
    height: auto !important;
  }
---

# Mermaidダイアグラムの例

## 基本的なフローチャート

<div class="mermaid">
flowchart TD
    A([開始]) --> B{条件分岐}
    B -->|Yes| C[処理1]
    B -->|No| D[処理2]
    C --> E([終了])
    D --> E
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#f9f,stroke:#333,stroke-width:2px
</div>

また、コードブロックでの記述も試してみます:

<pre class="mermaid">
flowchart TD
    A([開始]) --> B{条件分岐}
    B -->|Yes| C[処理1]
    B -->|No| D[処理2]
    C --> E([終了])
    D --> E
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#f9f,stroke:#333,stroke-width:2px
</pre>

---

# シーケンス図の例

<pre class="mermaid">
sequenceDiagram
    participant User as ユーザー
    participant Front as フロントエンド
    participant Back as バックエンド
    participant Database as DB

    User->>Front: リクエスト送信
    Front->>Back: API呼び出し
    Back->>Database: データ取得
    Database-->>Back: 結果返却
    Back-->>Front: レスポンス
    Front-->>User: 画面表示
</pre>

---

# ガントチャートの例

<pre class="mermaid">
gantt
    title プロジェクトスケジュール
    dateFormat  YYYY-MM-DD
    
    section 計画フェーズ
    要件定義    :2025-01-01, 30d
    設計        :2025-02-01, 45d
    
    section 開発フェーズ
    実装        :2025-03-15, 60d
    テスト      :2025-05-15, 30d
    
    section リリースフェーズ
    デプロイ    :2025-06-15, 15d
    運用開始    :2025-07-01, 7d
</pre>

---

# クラス図の例

<pre class="mermaid">
classDiagram
    class User {
        +String name
        +String email
        +login()
        +logout()
    }
    class Order {
        +int orderId
        +Date orderDate
        +process()
    }
    User "1" --> "*" Order: places
</pre>

---

# ERD（Entity Relationship Diagram）の例

<pre class="mermaid">
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ ORDER_ITEM : contains
    ORDER_ITEM }|--|| PRODUCT : references
</pre>

---

# マインドマップの例

<pre class="mermaid">
flowchart TD
    A((プロジェクト管理)) --> B(スコープ)
    A --> C(スケジュール)
    A --> D(リソース)
    A --> E(品質)
    B --> B1(要件定義)
    B --> B2(優先順位付け)
    C --> C1(マイルストーン)
    C --> C2(進捗管理)
    D --> D1(人員配置)
    D --> D2(予算管理)
    E --> E1(テスト計画)
    E --> E2(レビュー)
</pre>

<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs';
mermaid.initialize({ 
  startOnLoad: true,
  theme: 'default',
  fontSize: 16
});
</script>