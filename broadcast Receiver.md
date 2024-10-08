## 개념
1. 시스템에서 발생한 브로드캐스트 메시지를 수신하는 역할을 합니다.
2. 브로드캐스트 메시지는 시스템에서 발생하는 다양한 이벤트를 의미하며, 예를 들어 배터리 부족, 네트워크 상태 변경, 앱 설치/제거 등의 이벤트가 포함됩니다. 이러한 이벤트는 시스템이나 다른 앱에서 발생할 수 있으며, Broadcast Receiver는 이러한 이벤트를 수신하여 적절한 처리를 할 수 있습니다.
3.  개발자가 정의한 앱에서 발생시키는 브로드캐스트 메시지도 수신할 수 있습니다. 이를 통해 앱 내에서 이벤트를 처리하거나, 다른 앱에 메시지를 전달하는 등의 다양한 작업을 수행할 수 있습니다.
4. 시스템이나 다른 앱에서 보내는 브로드케스트 메시지를 받아서 처리합니다.
5. 디자인 패턴 중 publish-subscribe 형태 처럼 한쪽에서는 이벤트를 제공하기만 하고 한쪽에서는 이벤트를 받기만 합니다.
6. 앱들끼리도 미리 사전에 정의한 Action을 주고 받을 수 있습니다.
## 암시적 브로드캐스트
* AndroidManifast 파일에 브로드캐스트 리시버와 인텐트를 등록하여 사용
* 액티비티의 라이프사이클과 무관하게 작동, 앱이 설치되면 즉시 사용가능하며, 등록과 해지가 자유롭지 못하다.
* 안드로이드버전 오레오 이후에는 사용이 지양되었다.
* 암시적 브로드캐스트는 특정 리시버(수신자)를 지정하지 않고, 조건에 맞는 모든 리시버에게 메시지를 전달합니다.

## 명시적 브로드캐스트
* 동적으로 브로드캐스트 리시버를 생성, 호출, 종료하는 방법이다.
* 생명주기가 onReceive()이다.
* 리시버를 만들어 방송되는 시스템 이벤트들을 수신하고(원하는 것만), OnReceive()에서 어떤 행동을 발생시킬지 정합니다.
* 앱 A가 특정 이벤트가 발생했을 때 앱 B의 브로드캐스트 리시버에게만 메시지를 보내고 싶다면, 이 경우 명시적 브로드캐스트를 사용합니다.


## 왜 사용하는지?
1. 시스템에서 발생하는 다양한 이벤트(예: 배터리 상태 변경, 네트워크 연결 상태 변경, 부팅 완료 등)를 애플리케이션이 수신하고 처리할 수 있습니다
2. 다른 애플리케이션이 보낸 브로드캐스트 메시지를 수신하여 해당 메시지에 대한 적절한 처리를 할 수 있습니다. 예를 들어, 특정 작업을 완료했음을 알리기 위해 브로드캐스트를 보낼 수 있습니다
## 문제점 
* 비동기성: BroadcastReceiver는 비동기적(서대로 진행하는 것이 아니라 한번에 여러개가 진행되는 것과 마찬가지)으로 동작하기 때문에 실행 순서를 보장할 수 없습니다.
* 보안 이슈: 민감한 데이터를 전송할 때는 다른 앱에 의해 수신될 가능성이 있으므로 주의해야 합니다.악의적인 목적을 갖고 수행하는 경우에는 사용자가 받는 알림(메시지, 전화 등)을 중간에서 가로채는 행위를 할 수 있으며, 특정한 상황에서만 발생하는 작업을 우회하여 수행하도록 조작할 수 있다

