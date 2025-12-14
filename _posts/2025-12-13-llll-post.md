---
layout: post
title:  "Mermaid를 활용한 인간 진화 과정 클래스 다이어그램"
date:   2025-12-13 20:29:00 +0900
excerpt: "인간은 신기한거야"
tag:
- markdown 
- syntax
- sample
- test
- jekyll
comments: true
---

안녕하세요! 오늘은 UML(통합 모델링 언어) 다이어그램을 블로그에 쉽게 구현할 수 있게 해주는 **Mermaid** 문법을 사용하여 **인간 진화 과정**을 클래스 다이어그램으로 모델링해 보았습니다.

이 다이어그램은 주요한 '종(Species)'을 클래스로 표현하고, '상속(Inheritance)' 관계를 통해 진화적 계통을 시각적으로 나타냅니다.

---

### 🧬 인간 진화 과정 클래스 다이어그램

아래 Mermaid 코드를 사용하여 렌더링한 결과입니다.



```mermaid
classDiagram
    direction LR

    class Hominidae {
        +Family
        -Bipedalism
        -BrainSize
    }

    class Australopithecus {
        +Genus
        +SmallBrain
        +FullyBipedal
    }

    class Homo {
        +Genus
        +LargeBrain
        +ToolUse
    }

    class Habilis {
        +Species
        +SimpleStoneTools (Oldowan)
    }

    class Erectus {
        +Species
        +FireControl
        +MigratedOutOfAfrica
        +AdvancedTools (Acheulean)
    }

    class Neanderthalensis {
        +Species
        +RobustBuild
        +ComplexCulture
    }

    class Sapiens {
        +Species
        +ModernAnatomy
        +ComplexLanguage
        +Art
    }

    Hominidae <|-- Australopithecus : 진화 (Evolution)
    Hominidae <|-- Homo : 진화 (Evolution)

    Australopithecus <|-- Habilis : 진화 (Evolution)

    Homo <|-- Habilis : Genus
    Homo <|-- Erectus : Genus
    Homo <|-- Neanderthalensis : Genus
    Homo <|-- Sapiens : Genus

    Habilis --> Erectus : 진화 (Evolution)
    Erectus --> Sapiens : 진화 (Evolution)
    Erectus --> Neanderthalensis : 진화 (Evolution)

    note for Erectus "Homo Ergaster 포함 가능"
    note for Neanderthalensis "유럽 및 아시아"
    note for Sapiens "현생 인류 (Modern Humans)"
