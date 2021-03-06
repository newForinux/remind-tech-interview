## 🤔 정적 분석, AST?

### 정적 분석이란
정적 분석이란 프로그램을 실행하지 않고 소스 코드를 분석하는 것입니다.

본 프로젝트에서는 Java의 `OOP` 관련 개념을 적절히 사용했는지 확인하기 위해 일부 개념을 적용했습니다.

고려한 OOP 개념은 캡슐화, 추상화(인터페이스), 다형성(오버라이딩, 오버로딩), 상속성(상위클래스 상속) 등이며,

채점자가 직접 코드를 열어보지 않고도 요구되는 개념을 적용해 프로그램을 작성했는지 확인하고자 했습니다.

이를 위해 소스 코드의 AST를 분석하는 Eclipse JDT 라이브러리를 사용했습니다.

<br>

### AST란
AST (Abstract Syntax Tree)는 소스 코드를 언어의 문법으로 분리하여 컴퓨터가 이해할 수 있는 구조로 분리시킨 트리를 말합니다.

추상 문법은 각 프로그래밍 언어의 문법, 문단의 역할 등을 표현하는 규칙으로, 데이터의 구조나 종류를 포함합니다.

Eclipse JDT에 포함된 AST 클래스에서 사용할 수 있으며, 모듈화된 Java 라이브러리를 추가해 파싱할 수 있습니다.

<br>

ASTVisitor 클래스를 호출해 트리를 순회하면서 요구하는 문법을 찾을 수 있으며,

부모 또는 자식 클래스, 인터페이스, 캡슐화 여부, 클래스, 패키지 및 메소드 사용 여부까지 판별할 수 있습니다.

그 외에, 스레드 사용, 커스텀 자료구조 및 예외처리 클래스도 검사하는 로직을 구현했습니다.

<br>

### OOP의 원칙을 아세요?
OOP의 5대 원칙은 <b>SOLID</b>라고 부릅니다.

각각 SRP, OCP, LSP, DIP, ISP로 말할 수 있습니다.

* <b>SRP (Single Responsibility Principle, 단일 책임 원칙)</b> : 객체는 하나의 책임만 가집니다. 클래스가 여러 책임을 가지면 결합도가 높아질 수 있습니다.
* <b>OCP (Open-Closed Principle, 개방-폐쇄 원칙)</b> : 기존 코드를 변경하지 않고도 기능을 추가할 수 있어야 합니다.
* <b>LSP (Liskov Substitution Principle, 리스코프 치환 원칙)</b> : 자식 클래스는 최소한 부모 클래스에서 가능한 행위를 할 수 있어야 합니다.
* <b>DIP (Dependency Inversion Principle, 의존 역전 원칙)</b> : 의존 관계를 맺을 때, 거의 변화가 없는 것에 의존해야 합니다. 추상화된 인터페이스나 상위 클래스를 둘어 변화에 영향받지 않게 하는 것입니다.
* <b>ISP (Interface Segregation Principle, 인터페이스 분리 원칙)</b> : 클라이언트는 사용하지 않는 인터페이스에 의존하면 안 됩니다. 단일 책임 원칙과 같은 문제의 다른 해결책으로, 인터페이스를 작은 단위로 분리시키는 것입니다.

<br>

### 관점 지향 프로그래밍(AOP)을 아세요?
기존프로그래밍에서 각 객체 별로 처리했던 것을 관점 별로 외부에서 접근하는 프로그래밍입니다.

객체 지향 프로그래밍을 보조하여 더욱 객체 지향답게 하는 프로그래밍 방법론이라고 합니다.

코드의 규모가 커질수록 객체 지향 모듈 내에서도 중복되는 코드가 발생할 수 있는데,

이 중복되는 기능을 횡단으로 공통 모듈화하여 재활용성을 극대화합니다.

