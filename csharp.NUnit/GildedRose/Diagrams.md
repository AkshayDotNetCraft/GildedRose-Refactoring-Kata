```mermaid
classDiagram
    class Program {
        +Main(string[] args)
        -CreateItems() : IList<Item>
    }

    class GildedRose {
        -IList<Item> Items
        +GildedRose(IList<Item> Items)
        +UpdateQuality()
    }

    class Item {
        +ItemData Data
        +Item(string name, int sellIn, int quality)
        +UpdateQuality()
        +UpdateSellIn()
        +HandleExpired()
        -IncreaseQuality()
        -DecreaseQuality()
        -UpdateBackstagePassQuality()
    }

    class ItemData {
        +string Name
        +int SellIn
        +int Quality
        +ItemData(string name, int sellIn, int quality)
    }

    Program --> GildedRose
    GildedRose --> Item
    Item --> ItemData
```
```mermaid
flowchart TD
    A[Main Method] --> B[Create Items]
    B --> C[Create GildedRose Instance]
    C --> D[Loop for Days]
    D --> E[Print Item State]
    E --> F[Update Quality]
    F --> G[Update Item Quality]
    F --> H[Update Item SellIn]
    F --> I[Handle Item Expired]
```
```mermaid
sequenceDiagram
    participant User
    participant Program
    participant GildedRose
    participant Item

    User ->> Program: Run Application
    Program ->> Program: Create Items
    Program ->> GildedRose: Create Instance
    Program ->> GildedRose: UpdateQuality
    GildedRose ->> Item: UpdateQuality
    Item ->> Item: UpdateQuality
    Item ->> Item: UpdateSellIn
    Item ->> Item: HandleExpired
    Program ->> User: Print Item State
```
```mermaid
classDiagram
    class Program {
        +Main(string[] args)
        -CreateItems() : IList<Item>
    }

    class GildedRose {
        -IList<Item> Items
        +GildedRose(IList<Item> Items)
        +UpdateQuality()
    }

    class Item {
        +ItemData Data
        +Item(string name, int sellIn, int quality)
        +UpdateQuality()
        +UpdateSellIn()
        +HandleExpired()
        -IncreaseQuality()
        -DecreaseQuality()
        -UpdateBackstagePassQuality()
    }

    class ItemData {
        +string Name
        +int SellIn
        +int Quality
        +ItemData(string name, int sellIn, int quality)
    }

    Program --> GildedRose
    GildedRose --> Item
    Item --> ItemData
```
```mermaid
graph TD
    A[User] --> B[Console Application]
    B --> C[GildedRose Class]
    C --> D[Item Class]
    D --> E[ItemData Class]
```
```mermaid
%% C4 Context Diagram
graph TD
    subgraph SystemContext [System Context]
        User[User]
        System[GildedRose Application]
    end
    User -->|Uses| System
```
```mermaid
%% C4 Container Diagram
graph TD
    subgraph System [GildedRose Application]
        subgraph Backend [Backend]
            Program[Program]
            GildedRose[GildedRose]
            Item[Item]
            ItemData[ItemData]
        end
    end
    User[User] -->|Uses| Program
    Program --> GildedRose
    GildedRose --> Item
    Item --> ItemData
```
```mermaid
%% C4 Component Diagram
graph TD
    subgraph Program [Program]
        Main[Main Method]
        CreateItems[CreateItems Method]
    end
    subgraph GildedRose [GildedRose]
        UpdateQuality[UpdateQuality Method]
    end
    subgraph Item [Item]
        UpdateQualityItem[UpdateQuality Method]
        UpdateSellIn[UpdateSellIn Method]
        HandleExpired[HandleExpired Method]
        IncreaseQuality[IncreaseQuality Method]
        DecreaseQuality[DecreaseQuality Method]
        UpdateBackstagePassQuality[UpdateBackstagePassQuality Method]
    end
    subgraph ItemData [ItemData]
        Properties[Properties: Name, SellIn, Quality]
    end
    User[User] -->|Uses| Main
    Main --> CreateItems
    Main --> UpdateQuality
    UpdateQuality --> UpdateQualityItem
    UpdateQualityItem --> UpdateSellIn
    UpdateQualityItem --> HandleExpired
    UpdateQualityItem --> IncreaseQuality
    UpdateQualityItem --> DecreaseQuality
    UpdateQualityItem --> UpdateBackstagePassQuality
    Item --> Properties
```
```mermaid
%% C4 Code Diagram
graph TD
    subgraph Program [Program]
        Main[Main Method]
        CreateItems[CreateItems Method]
    end
    subgraph GildedRose [GildedRose]
        UpdateQuality[UpdateQuality Method]
    end
    subgraph Item [Item]
        UpdateQualityItem[UpdateQuality Method]
        UpdateSellIn[UpdateSellIn Method]
        HandleExpired[HandleExpired Method]
        IncreaseQuality[IncreaseQuality Method]
        DecreaseQuality[DecreaseQuality Method]
        UpdateBackstagePassQuality[UpdateBackstagePassQuality Method]
    end
    subgraph ItemData [ItemData]
        Properties[Properties: Name, SellIn, Quality]
    end
    User[User] -->|Uses| Main
    Main --> CreateItems
    Main --> UpdateQuality
    UpdateQuality --> UpdateQualityItem
    UpdateQualityItem --> UpdateSellIn
    UpdateQualityItem --> HandleExpired
    UpdateQualityItem --> IncreaseQuality
    UpdateQualityItem --> DecreaseQuality
    UpdateQualityItem --> UpdateBackstagePassQuality
    Item --> Properties

