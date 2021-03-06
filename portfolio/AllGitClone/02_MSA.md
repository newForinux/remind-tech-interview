## 🤔 마이크로서비스 아키텍처(MSA)?

### 마이크로서비스란?

하나의 대규모 프로젝트 / 어플리케이션을 여러 개의 다른 역할을 하는 작은 단위의 모듈로 분리하여, 결합도가 느슨하며 API를 통해 통신하는 구조입니다.

마이크로서비스는 완전히 독립적으로 배포할 수 있으며, 클라우드 기반 환경에 적합합니다.

<br>

### Monolithic Architecture의 대안

애플리케이션의 모든 구성요소가 하나로 통합된 형태인 Monolithic Architecture는 프로젝트의 규모가 커질수록 코드가 방대해지고, 이는 개발자의 생산성을 저하시킬 수 있습니다.

또한 이미 적용된 기술 스택을 변경하는 것이 까다로워지고, 결과적으로 리팩토링도 어렵게 됩니다. (즉, 한 프레임워크나 언어에 지나치게 종속적이게 됩니다)

어플리케이션의 부분적 장애가 서비스 전체의 장애로 확대될 수도 있습니다.

<br>

이러한 단점을 보완하고자 MSA가 등장했으며, Monolithic의 다양한 기능을 각각 독립적으로 설계하는 방식입니다.

이렇게 되면 단일 모듈 장애로 인해 전체 서비스는 큰 영향을 받지 않고,

의존 관계가 적고 유연하므로 새로운 기술 스택을 적용하기 쉬우며,

각각 서비스의 개발이 빠르고 유지보수 또한 용이합니다.

<br>

### MSA의 특징

MSA는 <b>API를 통해서만</b> 통신합니다. 실질적인 세부 사항은 모두 추상화(abstraction)할 수 있습니다.

내부 구현 로직 등 기술적인 내용은 API에 의해 가려지게 됩니다.

또한, 각 비즈니스 로직을 담당하는 모듈은 독립적으로 배포 가능해야 하고, 재사용할 수 있어야 합니다.

REST와 같은 통신 아키텍처 또는 Kafka와 같은 message stream을 주로 사용합니다.

모듈의 통신 방법은 주로 다음과 같습니다.

<br>

- <b>RPC (Remote Procedure Call)</b> : IPC (inter-Process Communication)의 한 종류로, 언어나 프레임워크 등에 구애받지 않고 원격의(=다른 주소 공간의) 프로시저를 호출하는 방법입니다.

- <b>Message-driven</b> : 프로세스 간 메시지를 통해 통신하며, 각 메시지 큐에 있는 메시지를 꺼내 핸들링합니다. `Event-driven`이라고도 합니다.

위 방법은 모두 Server-Client 방식입니다 (Kafka는 Producer - Consumer 개념으로 설명합니다)

<br>

그러나, MSA는 monolithic보다 복잡하며, 실제 운영환경 (개발환경 X)에 배포하는 것이 쉽지 않습니다.

여러 독립적인 모듈이 서로 잘 통신하는지, 트랜잭션이 잘 유지되는지 확인해야 하기 때문입니다.


