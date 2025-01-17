---
title:  "Collection"
categories: Java
---

# Collection이란?
{: .notice--warning}

Java에서 Collection은 객체들을 담을 수 있는 컨테이너의 일반적인 인터페이스를 제공하는 프레임워크입니다. Collection 인터페이스는 Java Collections Framework의 핵심이며, 다양한 자료 구조들을 표준화된 방법으로 조작할 수 있는 메서드를 정의하고 있습니다.

# Collection의 주요 특징
{: .notice--warning}

1. 컨테이너 역할: Collection은 객체들을 저장하고 관리하는 역할을 합니다. 이 객체들은 요소(Element)라고 불리며, 이들은 단일한 단위로 취급됩니다.
2. 크기 가변성: 대부분의 구현체는 크기가 가변적이며, 동적으로 요소를 추가하거나 삭제할 수 있습니다.
3. 인터페이스의 메서드들: Collection 인터페이스는 요소들을 다루기 위한 다양한 메서드를 제공합니다. 예를 들어, add 메서드로 요소를 추가하거나, remove 메서드로 요소를 삭제할 수 있습니다.
4. 반복자(Iterator) 지원: 컬렉션의 모든 요소에 접근하기 위해 반복자(Iterator)를 제공합니다. 반복자를 사용하여 컬렉션의 요소들을 순회하고 검색할 수 있습니다.
5. 중복 요소 허용: 대부분의 컬렉션 구현체는 중복된 요소를 허용합니다. 단, Set 인터페이스를 구현한 컬렉션은 중복을 허용하지 않습니다.

# Collection의 계층 구조
{: .notice--warning}

```mathematica
Iterable
│
└─ Collection
   │
   ├── Set
   │   ├── HashSet
   │   └── TreeSet
   │
   ├── List
   │   ├── ArrayList
   │   └── LinkedList
   │
   ├── Queue
   │   ├── PriorityQueue
   │   └── LinkedList
   │
   └── Map
       ├── HashMap
       ├── TreeMap
       └── LinkedHashMap
```

- Iterable 인터페이스: 모든 컬렉션 클래스가 구현하는 인터페이스로, 반복자(Iterator)를 생성하기 위한 메서드를 정의합니다.

- Collection 인터페이스: 모든 컬렉션 클래스의 기본 인터페이스로, 다양한 컬렉션을 다루기 위한 메서드들을 정의합니다. Set, List, Queue, Map 등 다양한 하위 인터페이스를 확장합니다.

- Set 인터페이스: 중복을 허용하지 않는 요소의 집합을 나타내는 인터페이스입니다. 주요 구현체로는 HashSet, TreeSet 등이 있습니다.

- List 인터페이스: 순서가 있는 요소의 집합을 나타내는 인터페이스로, 중복을 허용합니다. 주요 구현체로는 ArrayList, LinkedList 등이 있습니다.

- Queue 인터페이스: 큐(Queue) 구조를 나타내는 인터페이스로, 요소의 추가와 제거가 특별한 순서로 이루어집니다. 주요 구현체로는 PriorityQueue, LinkedList 등이 있습니다.

- Map 인터페이스: 키와 값의 쌍으로 이루어진 요소의 집합을 나타내는 인터페이스입니다. 주요 구현체로는 HashMap, TreeMap, LinkedHashMap 등이 있습니다.