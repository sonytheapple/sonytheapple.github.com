---
layout: post
title:  "다중 메시징 프로토콜을 지원하는 Chat UI 설계 및 구조 분석"
date:   2025-12-18
excerpt: "ㅎㅎㅎㅎㅎㅎㅎㅎㅎㅎㅎㅎㅎ"
tag:
- markdown 
- syntax
- sample
- test
- jekyll
comments: true
---
다양한 메시징 브로커(NATS, RabbitMQ, Redis)를 하나의 인터페이스에서 관리하기 위한 객체지향 시스템 구조를 설계했습니다. 본 포스팅에서는 클래스 다이어그램을 통해 각 객체의 역할과 관계를 분석합니다.

## 1. 클래스 다이어그램 (Class Diagram)

아래 다이어그램은 메인 UI와 각 메시징 클라이언트 간의 **집합(Aggregation)** 관계 및 **이벤트 콜백** 구조를 보여줍니다.



```mermaid
classDiagram
    class ChatUI {
        -box: String
        -nickname: String
        +nats: NatsClient
        +rabbit: RabbitClient
        +redis: RedisClient
        +initUI()
        +on_message(msg)
        +send_message()
        +combo_boxChanged()
        +ButtonClicked()
    }

    class NatsClient {
        +nc: NATS
        +message_callback: function
        +connect() Task
        +publish(text) Task
        +close() Task
    }

    class RabbitClient {
        +conn: BlockingConnection
        +thread: Thread
        +message_callback: function
        +connect()
        +publish(text)
        +close()
    }

    class RedisClient {
        +redis_conn: Redis
        +thread: Thread
        +message_callback: function
        +connect()
        +publish(text)
        +close()
    }

    ChatUI o-- NatsClient : aggregates
    ChatUI o-- RabbitClient : aggregates
    ChatUI o-- RedisClient : aggregates

    NatsClient ..> ChatUI : calls on_message()
    RabbitClient ..> ChatUI : calls on_message()
    RedisClient ..> ChatUI : calls on_message()
