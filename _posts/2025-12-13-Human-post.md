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
대규모 시스템이나 분역 환경에서는 서비스의 목적에 따라 NATS, RabbitMQ, Redis 등 서로 다른 메시징 브로커를 선택하게 됩니다. 이번 포스팅에서는 이 세 가지 클라이언트를 하나의 UI에서 통합 관리할 수 있는 객체지향적 구조를 클래스 다이어그램과 함께 소개합니다.

## 1. 시스템 클래스 다이어그램

본 설계의 핵심은 `ChatUI`라는 메인 클래스가 다양한 클라이언트를 소유(Aggregation)하고, 각 클라이언트가 발생시키는 이벤트를 공통된 콜백 메서드로 처리하는 구조에 있습니다.



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
