classDiagram
    direction LR
    
    class Vehicle {
        <<abstract>>
        +String model
        +int year
        +void start()
    }

    class Car {
        -String licensePlate
        +Engine engine
        +void drive()
    }

    class Bicycle {
        -int numberOfGears
        +void ride()
    }
    
    class Engine {
        +int horsepower
        +String fuelType
    }

    Vehicle <|-- Car : 상속 (Inheritance)
    Vehicle <|-- Bicycle : 상속 (Inheritance)
    Car "1" *-- "1" Engine : 포함 (Composition)
