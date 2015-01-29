![kafka_logo](C:\Users\Public\Pictures\Sample Pictures)  Apache Kafka(아파치 카프카)
=======
##### 높은 처리량을 분산한 메세징 시스템.

## Kafka 0.8.1 문서
현재 버전: [0.8.2-베타](http://kafka.apache.org/082/documentation.html) 이전 버전: [0.7.x,](http://kafka.apache.org/07/documentation.html)[0.8.0.](http://kafka.apache.org/08/documentation.html)
* [1.시작하기](http://kafka.apache.org/08/documentation.html#gettingStarted)
 * [1.1 소개](http://kafka.apache.org/08/documentation.html#introduction)
 * [1.2 사용 사례](http://kafka.apache.org/08/documentation.html#uses)
 * [1.3 빠른 시작](http://kafka.apache.org/documentation.html#quickstart)
 * [1.4 에코시스템](http://kafka.apache.org/documentation.html#ecosystem)
 * [1.5 업그레이드](http://kafka.apache.org/documentation.html#upgrade)
* [2.API](http://kafka.apache.org/documentation.html#api)
 * [2.1 프로듀서 API](http://kafka.apache.org/documentation.html#producerapi)
 * [2.2 고수준 컨슈머 API](http://kafka.apache.org/documentation.html#highlevelconsumerapi)
 * [2.3 단순 컨슈머 API](http://kafka.apache.org/documentation.html#simpleconsumerapi)
 * [2.4 카프카 하둡 컨슈머 API](http://kafka.apache.org/documentation.html#kafkahadoopconsumerapi)
* [3.환경설정](http://kafka.apache.org/documentation.html#configuration)
 * [3.1 브로커 설정](http://kafka.apache.org/documentation.html#brokerconfigs)
 * [3.2 컨슈머 설정](http://kafka.apache.org/documentation.html#consumerconfigs)
 * [3.3 프로듀서 설정](http://kafka.apache.org/documentation.html#producerconfigs)
 * [3.4 새 프로듀서 설정](http://kafka.apache.org/documentation.html#newproducerconfigs)
* [4.디자인](http://kafka.apache.org/documentation.html#design)
 * [4.1 동기부여](http://kafka.apache.org/documentation.html#majordesignelements)
 * [4.2 고집](http://kafka.apache.org/documentation.html#persistence)
 * [4.3 능률](http://kafka.apache.org/documentation.html#maximizingefficiency)
 * [4.4 프로듀서](http://kafka.apache.org/documentation.html#theproducer)
 * [4.5 컨슈머](http://kafka.apache.org/documentation.html#theconsumer)
 * [4.6 메세지 전달의 의미](http://kafka.apache.org/documentation.html#semantics)
 * [4.7 복제](http://kafka.apache.org/documentation.html#replication)
 * [4.8 로그 다짐](http://kafka.apache.org/documentation.html#compaction)
* [5.보완](http://kafka.apache.org/documentation.html#implementation)
 * [5.1 API 디자인](http://kafka.apache.org/documentation.html#apidesign)
 * [5.2 네트워크 계층](http://kafka.apache.org/documentation.html#networklayer)
 * [5.3 메시지](http://kafka.apache.org/documentation.html#messages)
 * [5.4 메세지 형식](http://kafka.apache.org/documentation.html#messageformat)
 * *[5.5 로그](http://kafka.apache.org/documentation.html#log)
 * [5.6 분산](http://kafka.apache.org/documentation.html#distributionimpl)
* [6.작동법](http://kafka.apache.org/documentation.html#operations)
 * [6.1 기본 카프카 작동법](http://kafka.apache.org/documentation.html#basic_ops)
   + [토픽 추가와 제거](http://kafka.apache.org/documentation.html#basic_ops_add_topic)
   + [토픽 수정](http://kafka.apache.org/documentation.html#basic_ops_modify_topic)
   + [정상종료](http://kafka.apache.org/documentation.html#basic_ops_restarting)
   + [균형의 리더십](http://kafka.apache.org/documentation.html#basic_ops_leader_balancing)
   + [컨슈머 위치 확인](http://kafka.apache.org/documentation.html#basic_ops_consumer_lag)
   + [클러스터 간의 데이터 미러링](http://kafka.apache.org/documentation.html#basic_ops_mirror_maker)
   + [클러스터 확장](http://kafka.apache.org/documentation.html#basic_ops_cluster_expansion)
   + [해체 브로커](http://kafka.apache.org/documentation.html#basic_ops_decommissioning_brokers)
   + [증가 복제 인자](http://kafka.apache.org/documentation.html#basic_ops_increase_replication_factor)
 * [6.2 데이타 센터](http://kafka.apache.org/documentation.html#datacenters)
 * [6.3 중요한 CONFIGS](http://kafka.apache.org/documentation.html#config)
   + [중요한 서버 CONFIGS](http://kafka.apache.org/documentation.html#serverconfig)
   + [중요한 클라이언트 CONFIGS](http://kafka.apache.org/documentation.html#clientconfig)
   + [운영서버 CONFIGS](http://kafka.apache.org/documentation.html#prodconfig)
 * [6.4 자바 버전](http://kafka.apache.org/documentation.html#java)
 * [6.5 하드웨어 및 OS](http://kafka.apache.org/documentation.html#hwandos)
    + [OS](http://kafka.apache.org/documentation.html#os)
    + [디스크 및 파일시스템](http://kafka.apache.org/documentation.html#diskandfs)
    + [응용프로그램 vs OS 세척 관리](http://kafka.apache.org/documentation.html#appvsosflush)
    + [리눅스 세척 행동](http://kafka.apache.org/documentation.html#linuxflush)
    + [Ext4 노트](http://kafka.apache.org/documentation.html#ext4)
 * [6.6 모니터링](http://kafka.apache.org/documentation.html#monitoring)
 * [6.7 주키퍼](http://kafka.apache.org/documentation.html#zk)
    + [안정버전](http://kafka.apache.org/documentation.html#zkversion)
    + [Operationalization](http://kafka.apache.org/documentation.html#zkops)

### 1.시작하기
#### 1.1 소개
카프카가 분산,분할,커밋 로그 서비스를 복제합니다. 이것은 메세징 시스템의 기능을 독특한 디자인으로 제공합니다.  

모두 무엇을 의미하는가?  

먼저, 몇 개의 기본적인 메세징 용어를 살펴보자:  
 - 카프카는 메세지의 피드를 _토픽_이라고 불리는 범주에 유지합니다.
 - 우리는 카프카 토픽 _프로듀서_에게 매세지를 게시하는 프로세스를 부를 것입니다.
 - 우리는 토픽에 등록하고 발행된 메세지 _컨슈머_의 공급을 처리하는 프로세르를 부를 것입니다.
 - 카프카는 _브로커_라고 불리는 각각 하나 이상의 서버로 구성된 클러스터로 실행합니다.  

그래서,고수준에서, 프로듀서들은 메세지들을 네트워크를 통해 결과적으로 컨슈머에게 그들을 제공하는 카프카 클러스터에게 보냅니다. 이와 같이:  

![](C:\Users\Public\Pictures\Sample Pictures "producer_consumer")  

클라이언트와 서버 간의 소통은 단순하고,고성능,언어 불가지론 [TCP 프로토콜](https://cwiki.apache.org/confluence/display/KAFKA/A+Guide+To+The+Kafka+Protocol)이다. 우리는 카프카를 위해 자바 클라이언트를 제공하지만, 클라이언트들은 [많은 언어](https://cwiki.apache.org/confluence/display/KAFKA/Clients)들을 이용가능하다.  

#####토픽 및 로그
카프카가 제공하는 높은 수준의 추상화에 첫 다이빙 하자-토픽.(Let's first dive into the high-level abstraction Kafka provides-the topic.)  
토픽은 카테고리 또는 메세지가 게시되는 피드 이름입니다. 각 토픽을 위해서, 카프카 클러스터는 분할 된 로그를 다음과 같이 유지:  

![]()

각 파티션은 지속적으로 커밋 로그에 추가하는 메시지의 불변의 순서를 정렬합니다. 파티션 안에 있는 메세지는 ,할당 된 각 순차 ID 번호고 고유 파티션 내에서 각 메세지를 식별하는 _오프셋_ 이라고 불립니다.

카프카 클러스터는 모든 발행 된 메세지를 그들이 소비되었는지 아닌지에 따라 구성 가능한 시간 기간동안 보유합니다. 예를 들어, 로그보존이 이틀로 설정된다면, 다음 이틀 동안 메세지가 게시 된 후 소비 할 수 있고, 그 후에는 공간을 확보하기 위해 삭제됩니다. 카프카의 수행은 능률적으로 데이터 크기에 대하여 일정해서 많은 양의 데이터를 보유하는 것에 문제가 없습니다.  

실제로 당 컨슈머 기준으로 유지하는 유일한 메타 데이터는 로그에 컨슈머의 위치를 "오프셋"으로 부릅니다. 컨슈머에 의해 제어된 오프셋: 보통 컨슈머는 메세지를 읽을 때 선형 오프셋을 진행시키지만, 실제로 위치는 컨슈머에 의해 제어되고 그것이 원하는 임의의 순서로 메세지를 사용 할 수 있습니다. 예를 들어 컨슈머는 재처리 이전 오프셋을 재설정 할 수 있습니다.  

이 기능들의 결합은 카프카 컨슈머들이 매우 인색하다는 의미입니다. 즉, 그들은 클러스터나 다른 컨슈머들에 대한 큰 영향없이 드나들 수 있습니다. 예를 들어, 너는 우리의 명령 줄 도구들을 기존에 있는 어느 컨슈머들에 의해 소비되는 어떤 것의 변화없이 어떤 토픽의 내용인 "꼬리" 에 사용 할 수 있습니다.  

로그에 있는 파티션들은 몇몇의 목적들을 제공합니다. 첫째로, 그들은 로그를 하나의 서버에 딱 맞는 크기 이상으로 조정하도록 허락합니다. 각각의 개별 파티션은 이것을 진행하는 서버들에 적합해야 하지만, 토픽은 임의의 양의 데이터를 조절할 수 있어서 많은 파티션들을 가질 수 있습니다. 두 번째는 그들은 더 많은 비트에 대한 병행의 단위로써 행동합니다.  

##### 분산  

로그의 파티션들은 파티션의 공유요청과 데이터를 처리하는 각각의 서버와 카프카 클러스터 안에 있는 서버들을 걸쳐 분산합니다. 각 파티션은 고장 허용 범위를 위해 설정가능한 서버의 수를 걸쳐서 복제합니다.  

각각의 파티션은 "리더" 로써 일을 하는 하나의 서버와 "팔로워" 로써 일을 하는 제로 또는 더 많은 서버들을 가집니다. 리더는 팔로워들이 수동적으로 리더를 복사할 동안 파티션을 위한 모든 읽고 쓰는 요청들을 다룹니다. 만약 리더가 실패했을 때, 팔로워들 중 하나는 자동으로 새로운 리더가 될 수 있습니다. 각 서버는 리더로써 몇몇의 파티션들을 위해서 그리고 팔로워는 다른 것들을 위해서 수행해서 로드는 클러스터 내에 잘 균형 잡혀있습니다.  

#####프로듀서

프로듀서들은 그들이 선택한 토픽에 데이터를 게시합니다. 프로듀서는  토픽내에서 어떤 파티션에 어떤 메세지를 지정할 지에 대한 선택에  책임이 있습니다. 이것은 단순히 로드 균형을 잡기 위해서 라운드-로빈 방식으로 수행 되거나 이것은 어떤 의미의 파티션 기능(메세지에서 어떤 키에 기초해서 말하는)에 따라 수행 될 수 있습니다. 두 번째에서 파티션의 사용에 대해서 더 자세히 있습니다.

#####컨슈머

메세징은 전통적으로 두가지 모델이 있다: [대기행렬](http://en.wikipedia.org/wiki/Message_queue)과 [발행-구독](http://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern). 대기행렬에서, 컨슈머의 풀은 서버로부터 읽을 수 있고, 각 메세지는 그들 중 하나에게 갑니다; 발행-구독에서는 메세지는 모든 컨슈머들에게 보도됩니다. 카프카는 이 소비자 그룹을 동시에 일반화시킨 한 컨슈머 추상화를 제공합니다.  

컨슈머는 스스로를 컨슈머 그룹 이름으로 라벨을 매기고, 토픽에 게시한 각각 메세지는 각 구독 컨슈머 그룹내에서 즉시 한 컨슈머에게 전달됩니다. 컨슈머 인스터스는 별도의 프로세스 또는 별도의 기계에 있을 수 있습니다.  

모든 컨슈머 인스턴스가 같은 컨슈머 그룹이라면, 이것은 컨슈머 이상 으로 전통적인 큐 밸런싱 로드처럼 작동합니다.  

모든 컨슈머 인스턴스가 다른 컨슈머 그룹이라면, 이것은 발행-구독처럼 작동하고 모든 메세지들은 모든 컨슈머들에게 보도됩니다.  

그러나,흔히,우리는 토픽들이 각각의 "논리적 구독자"에 대해서 적은 수의 컨슈머 그룹들을 가지고 있는 것을 발견할 수 있습니다. 각 그룹은 확장성과 내고장성에 대해 많은 컨슈머 인스턴스로 구성됩니다. 구독은 한 프로세스 대신 컨슈머의 클러스터인 곳에서 발행-구독의 의미가 다가 아닙니다.  

카프카도 전통적인 메세징 시스템보다 더 강한 순서 보장이 있습니다.  

전통적인 큐를 보유한 메세지-서버에 주문하고, 여러 컨슈머가 큐로 부터 소비하고 나서 서버가 그들이 저장한 순서로 메세지들을 나눠줍니다. 그러나, 비록 서버가 순서대로 메세지들을 나눠줄지라도, 메세지들은 컨슈머에게 비동기적으로 전달될 수 있습니다, 그래서 그들은 다른 컨슈머에게 순서에 맞지 않게 도달할 수 있습니다. 이것은 병렬 소비의 존재하에서 효과적으로 메세지의 순서가 틀렸다는 것을 의미합니다. 메세징 시스템은 자주 이것을 한 프로세스가 큐로 부터 소비하하도록 허락하는 "독점적인 컨슈머" 개념을 가짐으로써 이것을 해결합니다,하지만 물론 이것은 프로세스의 병행이 없다는 것을 의미합니다.  

![A]t text]()

카프카는 더 잘합니다. 토픽내에서 병렬 파티션의 개념을 가짐으로써, 카프카는 컨슈머 프로세스들의 풀 이상으로 순서보장과 로드 균형을 제공할 수 있습니다. 이것은 토픽안에서 컨슈머 그룹에 있는 컨슈머들에게 파티션을 지정함으로써 성취합니다.그래서 각 파티션은 정확히 그룹에 있는 한 컨슈머에 의해서 소비됩니다. 이렇게함으로써 우리는  컨슈머는 유일한 파티션의 리더고 순서대로 데이터를 소비하는 것을 증명합니다. 많은 파티션들이 있기 때문에 이것은 여전히 많은 컨슈머  인스턴스를 통해 로드를 균형 맞춥니다. 그러나 파티션 보다 더 많은 컨슈머 인스턴스는 없다는 것을 주목해야 합니다.  

카프카는 토픽안에 다른 파티션들 사이가 아닌 같은 파티션내에서 메세지를 통해 전체 순서를 제공합니다. 키에 의해 파티션 데이터의 능력과 결합된 퍼-파티션 순서는 대부분의 어플리케이션에 충분합니다.(Per-partition ordering combined with the ability to partition data by key is sufficient for most applications.) 그러나,너가 메세지를 통해 전체 순서를 필요로 한다면 이것은 단지 하나의 컨슈머 프로세스를 의미할 것이지만 이것은 하나의 파티션이 있는 토픽으로 달성 할 수 있습니다.  

##### 보증

높은 수준에서 카프카는 다음과 같은 보장을 제공:

* 특정 토픽 파티션에 프로듀서가 보낸 메세지는 그들이 보낸 순서대로 첨부됩니다. 즉,메세지 M1은 M2 메세지와 같은 프로듀서에 의해 전송된 경우,M1이 먼저 전송되면 M1은 M2보다 더 낮은 오프셋을 가지고 로그에서 더 일찍 나타납니다.
* 컨슈머 인스턴스는 그들이 로그에 저장한 순서대로 메세지를 봅니다.
* 복제 계수 N이 있는 토픽을 들어, 우리는 로그에 커밋하는 메세지들을 잃지않고 N-1 서버 장애까지 허용할 수 있습니다.

이 보증에 대한 자세한 내용은 문서의 디자인 섹션에서 나옵니다.  

####1.2 사용사례

여기에서 아파치 카프카에 대한 인기있는 사용사례 몇개를 설명합니다. 기능에 대한 개요에 대해선 이 [블로그 게시물](For an overview of a number of these areas in action, see this blog post. )을 참조하세요.

#####메세징

카프카는 더 전통적인 메세지 브로커에 대한 대체로 잘 작동합니다. 메세지 브로커들은 다양한 이유로 사용됩니다.(데이터 프로듀서로부터 프로세싱 분리,처리되지 않은 메시지를 버퍼에 저장,등등) 대부분의 메세징 시스템에 비해 카프카는 처리량,파티션닝 건설,복제,그리고 큰 규모의 메세지 프로세싱 응용프로그램을 위한 좋은 솔루션인 장애허용이 더 발달했습니다.  

우리의 경험에서 메세징 사용들이 종종 비교적 낮은 처리량이지만,낮은 엔드투엔드 지연을 요구할 수 있고 종종 카프카가 제공하는 강한 내구성 보증들에 의존합니다.  

이 도메인에서 카프카는 [ActiveMQ](In this domain Kafka is comparable to traditional messaging systems such as ActiveMQ or RabbitMQ. ) 또는 [RabbitMQ](https://www.rabbitmq.com/)와 같은 전통적인 메세징 시스템들과 맞먹습니다.

##### 웹사이트 활동 추적

카프카의 오리지널 사용사례는 실시간 publish-subscribe 피드의 세트로 유저 활동 추적 파이프라인을 재설정할 수 있습니다. 이것은 사이트 활동(페이지 뷰,검색,또는 다른 유저가 쓰는 활동들)이 활동유형 당  하나의 토픽을 중심 토픽에 게시하는것을 의미합니다. 이런 피드는 실시간 처리,실시간 모니터링,그리고 하둡 또는 오프라인 처리와 기록을 위한 오프라인 데이터 웨어하우싱 시스템으로 로딩하는 것들을 포함한 사용사례의 범위를 구독할 수 있습니다.  

활동 추적은 종종 많은 활동 메세지들을 각각의 유저 페이지 뷰에 발생시키는 매우 높은 볼륨입니다.

##### 통계

카프카는 종종 작동 모니터링 데이터를 위해 사용됩니다. 이것은 운영 데이터의 중앙집권화된 피드들을 생성하기 위해 분산된 응용 프로그램에서 통계통합을 포합합니다.(This involves aggregating statistics from distributed applications to produce centralized feeds of opertional data.)

##### 로그 집합

많은 사람들은 로그 통합 솔루션을 위해 대체로 카프카를 사용합니다. 로그 집합은 전형적으로 서버를 실제 로그 파일을 모으고 처리를 위해 그것들을 중심지(아마도 파일 서버 또는 HDFS)에 넣습니다. 카프카는 파일의 세부사항을 다르게 끌어내고 메세지의 스트림으로 이벤트 데이터나 로그의 클리너 추상화를 제공합니다. 이것은 낮은 지연처리와 다양한 데이터 소스들을 위해 더 쉽게 지원하고 데이터 소비를 분산하는 것을 허용합니다. 스크라이브(Scribe) 또는  플럼(Flume)과 같은 로그 중심의 시스템에 비해,카프카는 동등하게 좋은 성능,복제에 기인하는 더 강한 내구성 보장,그리고 더 낮은 엔드투엔드 지연을 제공합니다.

##### 스트림 프로세싱

많은 사용자가 적절한 데이터가 원시 데이터의 토픽으로부터 소비되어지고 집계되고,농축되고,또는 그렇지 않으면 더 소비를 위해 새로운 카프카 토픽으로 변환되는 데이터의 처리를 끝냅니다.(Many users end up doing stage-wise processing of data where data is consumed from topics of raw data and then aggregated,enriched,or otherwise transformed into new Kafka topics for further consumption.) 예를 들어, 기사 추천에 대한 처리흐름은 RSS 피드에서 기사항목을 크롤하고 "기사" 토픽에 이것을 게시합니다; 추가의 프로세싱은 정규화시키는 것을 도와주거나 이 항목을 cleaned 기사 항목의 토픽에 중복을 제거할 수 있습니다; 마지막 단계는 유저에게 이 내용을 일치하도록 시도할 수 있습니다. 이것은 개별 토픽중 실시간 데이터 플로우의 그래프를 생성합니다.[스톰(Storm)](https://github.com/nathanmarz/storm)과 [삼자(Samza)](http://samza.apache.org/)는 변환의 이러한 종류의 구현을 위한 인기있는 프레임워크입니다.

##### 이벤트 소싱(Event Sourcing)

[이벤트 소싱](http://martinfowler.com/eaaDev/EventSourcing.html)은 상태 변경이 기록의 순서대로 로그되는 어플리케이션 디자인의 스타일입니다. 매우 큰 저장된 로그 데이터를 위한 카프카의 지원은 이 스타일에 내장된 어플리케이션을 위해 이것을 훌륭한 백엔드로 만듭니다.

##### 커밋 로그(Commit Log)

카프카는 분산 시스템에 대한 외부의 커밋로그의 일종으로 역할을 할 수 있습니다. 로그는 실패노드가 자신의 데이터를 복원하는 재동기 메커니즘으로 노드와 행동 사이의 데이터를 복제하는 것을 도와줍니다. 카프카에서 [로그 압축](http://kafka.apache.org/documentation.html#compaction)기능은이 사용을 지원하는데 도와줍니다. 이 사용에서 카프카는 [아파치 부기계](http://zookeeper.apache.org/bookkeeper/) 프로젝트와 비슷합니다.

#### 1.3 빠른 시작

이 튜토리얼은 당신이 새롭게 시작하고 기존의 카프카나 주키퍼 데이터에 존재하지 않는 것으로 가정합니다.
##### 1단계: 코드를 다운로드

0.8.1.1 버전및 un-tar를 [다운로드](https://www.apache.org/dyn/closer.cgi?path=/kafka/0.8.1.1/kafka_2.9.2-0.8.1.1.tgz)
	> tar-xzf kafka_2.9.2-0.8.1.1.tgz
	> cd kafka_2.9.2-0.8.1.1

##### 2단계: 서버를 시작

카프카는 주키퍼를 사용해서 만약에 너가 이미 그것을 가지고 있지 않으면 너는 먼저 주키퍼 서버를 시작해야합니다. 너는 빠르고 간편한 단일노드 주키퍼 인스턴스를 얻기위해서 카프카와 함께 편리한 스크립트 패키지를 사용할 수 있습니다.
	> bin/zookeeper-server-start.sh config/zookeeper.properties
	[2013-04-22 15:01:37,495] INFO Reading configurtion from: config/zookeeper.properties(org.apache.zookeeper.serer.quorum.QuorumPeerConfig)

이제 카프카 서버를 시작:
	> bin/kafka-server-start.sh config/server.properties
	[2013-04-22 15:01:47,028] INFO Verifying properties (kafka.utils.VerifiableProperties)
    [2013-04-22 15:01:47,051] INFO Property socket.send.buffer.bytes is overridden to 1048576 (kafka.utils.VerifiableProperties)
    ...

##### 3단계: 토픽을 생성

하나의 파티션과 하나의 복제로 "테스트"라는 이름의 토픽을 만들어라:
	> bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test

만약에 우리가 토픽 명력 목록을 실행하면 우리는 이제 그 토픽을 볼 수 있습니다:
	> bin/kafka-topics.sh --list --zookeeper localhost: 2181
	test

대안적으로,존재하지 않는 토픽을 게시할때 수공으로 토픽을 만드는 것 대신에 너는 또한 너의 브로커들을 토픽 자동생성에 설정할 수 있습니다.

##### 4단계: 몇몇의 메세지들을 전송

카프카는 파일 또는 표준입력에서 입력을 하고 이것을 카프카 클러스터에 메세지로 발송하는 명령 행 클라이언트가 함께 제공됩니다. 자동적으로 각 라인은 별도의 메세지로 보내질 것입니다.  

프로듀서를 실행한 다음에 서버에 보내기 위한 몇 가지 메세지를 콘솔에 입력합니다.
	> bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
	This is a message
    This is another message

##### 5단계: 컨슈머를 시작

카프카는 또한 표준출력에 메세지를 덤프아웃하는 명령 행 컨슈머가 있습니다.
	> bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning
	This is a message
    This is another message

만약 다른 터미널에서 각각의 위의 명령어를 실행한경우 너는 지금 메세지를 프로듀서 터미널에 입력하고 그들은 컨슈머 터미널에서 나타나는 것을 볼 수 있어야합니다.  

명령 행 도구의 모든 것은 추가적인 옵션이 있습니다; 인수없이 명령을 실행하는 것은 더 자세하게 그들을 기록하는 사용정보를 보여줍니다.

#####  6단계: 다수의 브로커 클러스터 설정

지금까지 우리는 하나의 브로커에 대해 실행했습니다,하지만 그건 재미가 없습니다. 카파카에서,하나의 브로커는 단지 크기 하나의 클러스터입니다,그래서 더 많은 몇 가지 브로커 인스턴스 시작 외에 큰 변화가 없습니다. 하지만 바로 그것을 느낄수 있습니다, 우리의 클러스터를 세 개의 노드로 확장하자.(여전히 우리의 로컬 머신에서)  

먼저 우리는 각각의 브로커들을 위한 설정파일을 만듭니다:
	> cp config/server.properties config/server-1.properties
	> cp config/server.properties config/server-2.properties

이제 이 새로운 파일들을 편집하고 다음에 따르는 속성을 설정합니다:

	config/server-1.properties:
    broker.id=1
    port=9093
    log.dir=/tmp/kafka-logs-1

	config/server-2.properties:
    broker.id=2
    port=9094
    log.dir=/tmp/kafka-logs-2

brkoer.id 특성은 클러스터안에 있는 각각의 노드들의 독특하고 영구적인 이름입니다. 우리는 포트를 중단시키고 우리는 이것들을 같은 기계에서 실행해야 하기때문에 디렉토리를 로그해야하고 우리는 같은 포트에 기록하거나 각각 다른 데이터를 덮어쓰기를 시도하는 브로커들을 보호하기를 원합니다.  

우리는 이미 주키퍼를 가지고 있고 우리의 단일 노트를 시작합니다,그래서 우리는 단지 두 개의 새로운 노드가 필요합니다:
	> bin/kafka-server-start.sh config/server-1.properties &
	...
    > bin/kafka-server-start.sh config/server-2.properties &
    ...

이제 세 개의 복제 인자로 새로운 토픽을 생성합니다:
	> bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 1 --topic my replicate-topic

좋아,지금 우리는 클러스터를 가지고 있다 하지만 우리가 지금 어느 브로커가 무엇을 하는지 우리는 어떻게 알까? 그것을 보여주기 위해서 "describe 토픽" 명령을 실행시킨다:
	> bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic my-replicated-topic
	Topic:my-replicated-topic      PartitionCount:1    ReplicationFactor:3  Configs:
           Topic: my-replicated-topic        Partition: 0   Leader: 1      Replicas:  1,2,0  Isr: 1,2,0

출력에 대한 설명이 여기있다. 첫 번째 줄은 모든 파티션의 요약을 제공하고, 각각의 추가 라인은 하나의 파티션에 대한 정보를 제공합니다. 우리가 이 토픽에 대한 하나의 파티션을 가지고 있기 때문에 하나의 라인이 있습니다. 
* "리더"는 주어진 파티션에 대한 모든 읽고 쓰는 책임이 있는 노드이다. 각 노드는 파티션의 무작위로 선택된 부분에 대한 리더가 될 것입니다.
* "복제품"은 그들이 리더인지 아닌지 또는 심지어 그들이 현재 살아있는지 여부에 관계없이 이 파티션에 대한 로그를 복제하는 노드의 목록입니다. ("replicas" is the list of nodes that replicate the log for this parition regardless of whether they are the leader or even if they are currently alive)
* "ISR"은 "동기화" 복제본의 집합입니다. 이것은 현재 살아있고 리더에게 캐치업하는 복제본 목록의 부분집합입니다.

예에서 노드1은 토픽의 유일한 파티션의 리더입니다.  

우리는 우리가 어디에 그것이 있는지 보기위해 만든 원래의 토픽에 같은 명령을 실행할 수 있습니다:
	> bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic test
	Topic:test      PartitionCount:1        ReplicationFactor:1     Configs:
          TopicL test      Partition: 0     Leader: 0     Replicas: 0       Isr: 0

그래서 저기에 놀라운 일이 없다- 원래의 토픽은 복제본이 없고 우리가 이것을 만들때 우리의 클러스터 안에 있는 유일한 서버인 서버 0에 있습니다.  

우리의 새로운 토픽에 몇 가지의 메세지를 게시하자:
	> bin/kafka-console-producer.sh --broker-list localhost:9092 --topic my-replicated-topic
	...
    my test message 1
    my test message 2
    ^C

이제 이 메세지를 사용하자:
	> bin/kafka-console-consumer.sh --zookeeper localhost:2181 --from-beginning --topic my-replicated-topic
	...
    my test message 1
    my test message 2
    ^C

장애허용능력을 테스트하자. 브로커 1은 리더로 행동합니다.그래서 이것을 죽이겠다:
	> ps | grep server -1.properties
 	7564 ttys002    0:15.91   /System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home/bin/java ...
     > kill -9 7564

리더쉽은 노예의 하나로 전환했고 노드 1은 동기화 복제 세트에 더 이상 있지 않는다:
	> bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic my-replicated-topic
	Topic:my-replicated-topic      PartitionCount:1    ReplicationFactor:3   Configs:
       Topic: my-replicated-topic     Partition: 0     Leaer: 2  Replicas:1,2,0  Isr:2,0

그러나  원래 쓰기를 했던 리더가 다운됬을지라도 메세지는 여전히 소비가 가능합니다.
	> bin/kafka-console-consumer.sh --zookeeper localhost:2181 --from-begining --topic my-replicated-topic
	...
    my test message 1
    my test message 2
    ^C

#### 1.4 에코시스템

외부 카프카와 메인 분산을 통합 도구의 과잉이 있습니다. [에코시스템 페이지](https://cwiki.apache.org/confluence/display/KAFKA/Ecosystem)는 스트림 처리 시스템,하둡 통합,모니터링,그리고 배치도구를 포함하는 이들 중 많은 것을 나열합니다.

#### 1.5 이전 버전으로 부터의 업그레이드

##### 0.8.0에서 부터 0.8.1까지 업그레이드

0.8.1은 0.8과 완전히 호환됩니다. 업그레이드는 단순히 그것을 중단시키고,코드를 업그레이드하고,그리고 이것을 재시작함으로써 한번에 한 브로커를 수행할 수 있습니다.

##### 0.7에서부터 업그레이드

0.8,복제본을 추가한 버전은,우리의 이전버전들과 호환되지 않는 첫번째 버전입니다: 주된 변화는 API,주키퍼 데이터 구조,그리고 프로토콜 및 환경설정에서 만들어졌습니다. 0.7에서 0.8.x까지의 업그레이드는 이송을 위한 [특별한 도구](https://cwiki.apache.org/confluence/display/KAFKA/Migrating+from+0.7+to+0.8)가 필요합니다. 이 이송은 컴퓨터가 작동하지 않는 시간없이 수행됩니다.

### 2. API

#### 2.1 프로듀서 API

	/**
     *  V: 메세지의 타입
     *  K: 메세지와 연관된 옵션 키의 타입
    */
    class kafka.javaapi.producer.Producer<K,V>  {
      public Producer(ProducerConfig config);

    /**
     * 하나의 토픽에 데이터를 전송,키에 의한 분할,둘 중 하나 사용
     * 동기 또는 비동기 프로듀서
     * @param 메세지는 토픽,키 그리고 메세지 데이터를 요약한 프로듀서 데이터 객체 
     */
    public void send(KeyedMessage<K,V> message);

    /**
     * 이 API를 다수의 토픽에 데이터를 보내기 위해 사용
     * @param 메세지들은 토픽,키 그리고 메세지 데이터를 요약한 프로듀서 데이터 객체의 목록
     */
    public void send(List<KeyedMessage<K,V>> messages);

    /**
     * API 닫기는 모든 카프카 브로커에 프로듀서 풀(pool) 연결을 닫습니다
     * /
     public void close(); 
    }

너는 프로듀서 API를 사용하는 방법을 배울 수 있는 이 예를 따를 수 있습니다.

#### 2.2 고수준 컨슈머 API

    class Consumer  {
       /**
        * 컨슈머커넥터를 생성
        * 
        * @param 설정은 최소한으로,컨슈머와 주키퍼의 그룹피아이디를  명시해야한다.
        *  문자열 주키퍼.커넥트 연결
        */
    public static kafka.javaapi.consumer.ConsumerConnector createJavaConsumerConnector(ConsumerConfig config); 
    }

    /**
     *  V: 메세지의 타입
     *  K: 메세지와 연관된 옵션 키의 타입
     */
    public interface kafka.javaapi.consumer.ConsumerConnector {
    /**
     * 각 토픽에 대한 타입 T의 메세지 스트림의 목록을 작성
     * 
     * @param topicCountMap은  (topic, #streams) 쌍의 맵
     * @param 디코더는 메세지를 T로 바꿔주는 디코더이다.
     * @return은 (topic,list of KafkaStream) 쌍의 맵
     *      목록에 있는 항목의 수는 #streams 이다. 각 스트림은 지원한다.
     *      메세지/메타데이터 쌍의 반복자.
     */
    public <K,V> Map<String, List<KafkaStream<K,V>>>
     createMessageStreams(Map<String, Integer> topicCountMap, Decoder<K> keyDecoder, Decoder<V> valueDecoder);

    /**
     * 디폴트 디코더를 사용해서,각 토픽에 대한 타입 T의 메세지 스트림의 목록을 작성
     */
    public Map<String, List<KafkaStream<byte[], byte[]>>> createMessageStreams(Map<String, Integer> topicCountMap);

    /**
     * 와일드 카드와 일치하는 토픽에 대한 메세지 스트림의 목록을 작성
     * 
     * @param 토픽필터는 (화이트리스트 또는 블랙리스트 캡슐화)에 가입하는 어떤 토픽을 명시해야하는 토픽필터이다.
     * @param 넘스트름은 반화하는 메세지 스트림의 수
     * @param 키디코더는 메세지 키를 해독하는 디코더이다.
     * @param 밸류디코더는 메세지 자체를 해독하는 디코더이다
     * @return 카프카스트림의 목록. 각 스트림은 MessageAndMetadata 요소의 반복자를 지원합니다.
     */
    public <K,V> List<KafkaStream<K,V>>
     createMessageStreamByFilter(TopicFilter topicFilter, int numStreams, Decoder<K> keyDecoder, Decoder<V> valueDecoder);

    /**
     * 디폴트 디코더를 사용해서,와일드 카드와 일치하는 토픽에 대한 메세지 스트림의 목록을 작성
     */
    public List<KafkaStream<byte[], byte[]>> createMessageStreamsByFilter(TopicFilter topicFilter, int numStreams);

    /**
     * 하나의 스트림으로,디폴트 디코더를 사용해서,와일드 카드와 일치하는 토픽에 대한 메세지 스트림의 목록을 작성
     */
    public  List<KafkaStream<byte[], byte[]>> createMessageStreamByFilter(TopicFilter topicFilter);

    /**
     * 이 커넥터에 연결되는 모든 토픽/파티션의 오프셋을 커밋
     */
    public void commitOffsets();

    /**
     * 커넥터 종료
     */
    public void shutdown();
    }

너는 고수준 컨슈머 API를 어떻게 사용하는 지 배울 수 있는 [이 예](https://cwiki.apache.org/confluence/display/KAFKA/Consumer+Group+Example)를 따를 수 있습니다.

#### 2.3 단순한 컨슈머 API

    class kafka.javaapi.consumer.SimpleConsumer {
    /**
     * 토픽에서 메세지의 세트를 가져옵니다.
     * 
     * @param 요청 토픽 이름,토픽 파티션,오프셋 바이트 시작,가져올 수 있는 최대 바이트 수를 명시합니다.
     * @retrn 가져온 메시지의 세트
     */
    public FetchResponse fetch(kafka.javaapi.FetchRequest request);

    /**
     * 주제의 순서에 대한 메타데이터 가져오기.
     * 
     * @param 요청 버전ID,클라이언트ID,토픽의 순서를 명시.
     * @return 요청에서 각 주제에 대한 메타데이터.
     */
    public kafka.javaapi.TopicMetadataResponse send(kafka.javaapi.TopicMetadataRequest request);

    /**
     * 주어진 시간전에 유효한 오프셋(최대사이즈 까지)의 목록을 가져오기.
     * 
     * @param [[kafka.javaapi.OffsetRequest]] 객체를 요청.
     * @return [[kafka.javaapi.OffsetResponse]] 객체.
     */
    public kafka.javaapi.OffsetResponse getOffsetBefore(OffsetRequest request);

    /**
     * 단순컨슈머 닫기.
     */
    public void colse();
    }

대부분의 응용프로그램에서, 고수준 컨슈머 API는 충분합니다. 몇몇의 응용프로그램은 아직 고수준 컨슈머에서 드러나지않은 특징을 원합니다.(예를 들어,컨슈머를 재시작할때 초기 오프셋을 설정) 그들은 대신에 낮은수준의 단순한 컨슈머 API를 사용할 수 있습니다. 논리는 좀 더 복잡하고 너는 [여기](https://cwiki.apache.org/confluence/display/KAFKA/0.8.0+SimpleConsumer+Example)에 있는 예를 따를 수 있습니다.

#### 2.4 카프카 하둡 컨슈머 API

하둡에 데이터를 집계하고 로딩에 대한 수평 확장가능한 솔루션을 제공하는 것은 우리의 기본 사용 사례중 하나입니다. 이 사용사례를 지원하기 위해서, 우리는 병렬 카프카 클러스터로 부터 데이터를 가져오는 많은 맵 작업을 생성하는 하둡에 기초한 컨슈머를 제공합니다. 이것은 매우 빠른 풀 기반의 하둡 데이터 로드 능력을 제공합니다.(우리는 몇 안되는 카프카 서버와 네트워크를 완전히 포화할 수 있습니다.)

하둡 컨슈머에 대한 사용정보는 [여기](https://github.com/linkedin/camus/)에서 찾을 수 있습니다.

### 3. 환경설정

카프카는 설정에 대한 [특성 파일 형식](http://en.wikipedia.org/wiki/.properties)으로 키-값(key-value) 쌍을 사용합니다. 이 값은 파일이나 프로그램에서 제공할 수 있습니다.

#### 3.1 브로커 설정 

필수적인 구성은 다음과 같다:

* broker.id
* log.dirs
* zookeeper.connect

토픽 레벌 설정 및 디폴트는 [아래](http://kafka.apache.org/documentation.html#topic-config)에서 더 자세히 논의됩니다.

속성|디폴트|서술
-----|-------------|--------------
broker.id |         |각각의 브로커는 음이 아닌 정수 ID에 의해 고유의 방법으로 식별됩니다. 이 ID는 브로커의 "이름"의 역할을 하고 브로커가  혼란스러워하는 컨슈머 없이 다른 호스트/포트로 이동할 수 있습니다. 너는 이것이 고유하는 한 너가 원하는 아무 숫자를 선택할 수 있습니다.
log.dirs | /tmp/kafka-logs | 카프카 데이터가 저장되는 하나 이상의 디렉토리들의 쉼표로 구분된 목록입니다. 생성된 각각의 새로운 파티션은 현재 가장 적은 파티션을 가진 디렉토리에 배치됩니다.
port | 6667 | 서버가 클라이언트 연결을 허용하는 포트입니다. 
zookeeper.connect | null | 호스트이름 형식에서 주키퍼 연결 스트링을 지정: 호스트이름과 포트가 너의 주키퍼 클러스터의 노드에 대한 호스트와 포트인 포트, 호스트가 다운되었을때 다른 주키퍼 노드들을 통해 연결할 수 있도록하려면 너는 또한 hostname1: port1,hostname2:port2,hostname3:port3 형태에서 다양한 호스트들을 지정할 수 있습니다. 주키퍼는 또한 너가 특정 경로 아래에서 이 클러스터를 보여주는 모든 카프카 데이터를 만들수 있는 "chroot" 경로를 추가하도록 허락합니다. 이것은 다수의 카프카 클러스터 또는 같은 주키퍼 클러스터에 있는 다른 응용프로그램을 설정하는 방법입니다. 이 작업을 수행하기위해서 path/chroot/path 아래에서 모든 이 클러스터의 데이터를 넣을수 있는hostname1:port1,hostname2:port2,hostname3:port3/chroot/path 형태의 연결 스트링을 제공합니다. 너는 이 경로를 브로커를 시작하기 전에 스스로 만들 수 있어야 하고 컨슈머는 같은 연결 스트링을 사용해야합니다. 
message.max.bytes | 1000000 | 서버가 받을 수 있는 메세지의 최대 크기. 이 속성은 너의 컨슈머가 사용하는 최대 페치 사이즈 또는 다루기 힘든 프로듀서가 컨슈머가 사용하기에 너무 큰 메세지 게시와 협조 관계에 있다는 것이 중요합니다.
num.network.threads | 3 | 네트워크 요청들을 다루는 서버가 사용하는 네트워크 스레드(thread)의 수. 너는 아마도 이것을 바꿀 필요가 없습니다.
num.io.threads | 8 | 서버가 요청을 실행하기 위해서 사용하는 I/O 스레드의 수. 너는 적어도 너가 디스크를 가지고 있는 만큼 많은 스레드를 가져야합니다.
background.threads | 4 | 파일 삭제와 같이 다양한 백그라운드 처리 작업을 위해 사용하는 스레드의 수. 너는 이것을 바꿀 필요가 없습니다.
queued.max.requests | 500 | 네트워크 스레드 전에 I/O 스레드에 의해 처리를 위해 대기 할 수 있는 요청의 수는 새로운 요청에서 읽는 것을 멈춥니다.
host.name | null | 브로커의 호스트이름. 이것이 설정되면, 이것은 단지 이 주소에 바인드합니다. 이것이 설정이 안됬다면, 이것은 모든 인터페이스에 바인드하고,ZK에 하나를 게시합니다.
advertised.host.name | null | 이것이 설정된다면 이것은 이것에 연결하기 위한 프로듀서,컨슈머,그리고 다른 브로커에게 제공되는 호스트이름입니다.(If this is set this is the hostname that will be given out to producers, consumers, and other brokers to connect to.)
advertised.port | null | 연결 설정에 사용하는 프로듀서,컨슈머,그리고 다른 브로커에게 제공하는 포트.
socket.send.buffer.bytes | 100*1024 | 서버가 소켓 연결을 선호하는SO_SNDBUFF 버퍼.
socket.receive.buffer.bytes | 100*1024 | 서버가 소켓 연결을 선호하는 SO_RCVBUFF 버퍼.
socket.request.max.bytes | 100x1024x1024 | 서버가 허용할수있는 최대 요청 크기. 이것은 메모리 부족으로부터 서버를 예방하고 자바 힙 크기보다 작아야합니다.
num.partitions | 1 | 파티션 카운트가 토픽 생성 시간에 주어지지않은 경우,토픽 당 파티션의 디폴트 수.
log.segment.bytes | 1024x1024x1024 | 토픽 파티션에 대한 로그는 세그먼트 파일의 디렉토리로 저장합니다. 이 설정은 새로운 세그먼트가 로그에 롤 오버되기 전에 세그머느 파일이 증가 할 수 있는 크기를 조절합니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config) 참조)에 오버라이딩할 수 있습니다.
log.roll.hours | 24*7 | 이 설정은 log.segment.bytes크기에 도달하지 않더라도 새로운 로그 세그먼트를 돌아가게 하라고 카프카를 강요할 것입니다. 이 설정은 토픽다 기초([토픽당 구성 섹션](http://kafka.apache.org/documentation.html#topic-config) 참조)에 오버라이딩할 수 있습니다.
log.clenup.policy | delete | 이것은 값을 지우거나 콤팩 둘 중 하나를 씁니다. 삭제를 설정한 경우 로그 세그먼트는 그들이 크기 제한 또는 설정된 시간에 도달할때 지울 것 입니다. 콤팩으로 설정한 경우 로그 콤팩션은 쓸모가 없는 기록들을 지우는 데 사용될 것입니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.retention.{minutes,hours} | 7 days | 그것이 지워지기 전에 로그 세그먼트를 유지하기 위한 시간의 양,즉 모든 토픽에 대한 디폴트 데이터 유지 윈도우. log.retention.minutes 와 log.retention.bytes 둘다 양쪽 모두 설정되어 있는 경우 우리는 어느 제한을 초과할때 세그먼트를 삭제합니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.retention.bytes | -1 | 각 토픽파티션에 대한 로그에서 보유하는 데이터의 양. 토픽에 대한 보유하고 있는 전체 데이터를 얻는 파티션의 수로 곱해서 이것은 당-파티션 한계가 있습니다.(Note that this is the limit per-partition so multiply by the number of partitions to get the total data retained for the topic.) 또한 log.retention.hours 와 log.retention.bytes 둘다 설정된다면 우리는 제한이 초과될때 세그먼트를 삭제합니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.retention.check.interval.ms | 5 minutes | 우리가 아무 로그 세그먼트가 보유 기간을 충족시키는 삭제에 대한 자격이 있는지 체크하는 기간입니다.
log.cleaner.enable | false | 로그 콤팩션을 실행하기 위해서 이 설정은 사실로 설정해야 합니다.
log.cleaner.threads | 1 | 로그 컴팩션에서 로그를 청소하기 위해 사용하는 스리드의 수.
log.cleaner.io.max.bytes.per.second | None | I/O 로그 클리너의 최대 양은 로그 콤팩션을 수행하는 동안 할 수 있습니다. 이 설정은 라이브 요청 서빙에 영향주는 걸 피하기 위한 클리너에 대해 제한을 설정하는 걸 허용합니다.
log.cleaner.dedupe.buffer.size | 500x1024x1024 | 버퍼 로그 클러너의 크기는 청소하는동안 인덱싱 및 로그 중복제거를 위해서 사용합니다. 더 큰 더 나은 충분한 메모리가 제공됩니다.
log.cleaner.io.buffer.size | 512*1024 | 로그 청소하는 동안 사용되는 I/O 청크의 크기. 너는 아마도 이것을 바꿀 필요가 없습니다.
log.cleaner.io.buffer.load.factr | 0.9 | 로그 청소에 사용되는 해시 테이블의 로드 요소.너는 아마도 이것을 바꿀 필요가 없습니다.
log.cleaner.backoff.ms | 15000 | 어느 로그가 청소가 필요한 경우 검사 사이의 간격.
log.cleaner.min.cleanable.ratio | 0.5 | 이 설정은 얼마나 자주 로그 컴팩터가 로그를 청소하기 위해 시도 했는지 조절합니다.([로그 컴팩션](http://kafka.apache.org/documentation.html#compaction)이 가능한지 추정). 자동으로 우리는 콤팩트가 된 로그의 반이상인 곳에서 로그 청소하는 걸 피할 수 있습니다. 이 비율은 복제(50%에서 대부분의 로그 50%로 복제 될 수 있습니다.)에 의한 로그에서 소비되는 최대 공간 경계를 이룹니다. 높은 비율은 더 적고,보다 효율적으로 클리닝하는걸 의미하지만 로그에서 더 많은 공간을 쓰는 것도 의미합니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.cleaner.delete.retention.ms | 1 day | 보유하는 시간의 양은 컴팩트 된 토픽 로그에 대한 탐스톤 표시를 삭제합니다. 이 설정은 또한 그들이 마지막 단계의 유효한 스냅샷을 얻을 수 있도록 0 오프셋에서 시작하면 컨슈머가 읽기를 완료해야하는 시간에 바운드를 제공합니다.(그들이 그들의 스캔을 완료하기전에 그렇지 않으면 삭제 탐스톤이 수집될 수 있습니다.) 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.index.size.max.bytes | 10x1024x1024 | 각 로그 세그먼트의 오프셋 인덱스를 허용하는 바이트의 최대 크기. 우리는 항상 이 많은 공간과 함께 스파스 파일을 미리 할당할 수 있고 로그를 굴릴 때 이것을 아래로 감소할 수 있습니다. 인텍스가 채워지면 우리가 log.segment.bytes.limit 에 도달하지 않더라도 우리는 새로운 로그 세그먼트를 굴릴 수 있습니다. 이 설정은 토픽당 기초([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참조)에 오버라이딩할 수 있습니다.
log.index.interval.bytes | 4096 | 우리가 오프셋 인덱스에 항목을 추가하는 바이트 간격. 페치 요청을 실행할때 서버는 시작하고 페치를 종료하는 로그에 정확한 위치를 찾을 수 있는 이 많은 바이트들까지에 대한 선형 검색을 수행해야합니다. 그래서 이 값을 더 크게 설정하는 것은 더 큰 인덱스 파일(그리고 좀 더 많은 메모리 사용량)을 의미하지만 더 적은 스캐닝을 의미합니다. 그러나 서버가 로그 어펜드당 하나 이상의 인덱스 항목을 추가하지 않습니다.(log.index.interval 이상의 메세지의 가치를 추가할지라도) 일반적으로 너는 아마도 이 값을 엉망으로 만들 필요는 없습니다.
log.flush.interval.messages | None | 우리가 로그에 fsync를 강요하기전에 로그 파티션에 쓰여진 메세지의 수. 이것을 더 낮게 설정하는 것은 더 자주 데이터를 디스크에 싱크할수 있지만 성능에 주된 영향을 줍니다. 우리는 일반적으로 사람들이 단일 서버 fsync 보다 내구성을 위한 복제를 이용하는것을 권고합니다,그러나 이 설정은 특정 추가로 사용 할 수 있습니다.
log.flush.scheduler.interval.ms | 3000 | 로그 플러셔가 어느 로그가 디스크로 플러시할 자격이 있는지 체크하는 MS의 주파수.
log.flush.interval.ms | None | fsync 사이의 최대 시간은 로그를 부릅니다. log.flush.interval.messages와 결합해 사용하는 경우 어느 기준이 충촉될 때 로그는 플러시됩니다.
log.delete.delay.ms | 60000 | 우리가 그들이 메모리 안 세그먼트 인덱스로 부터 제거돈 후 로그파일주위를 가지고 있는 시간의 기간. 이 시간의 기간은 어느 진행중인 읽기를 잠금없이 방해하지 않고 완성할 수 있습니다. 너는 일반적으로 이것을 바꿀 필요가 없습니다
log.flush.offset.checkpoint.interval.ms | 60000 | 우리는 복구 로그에 대한 마지막 플러시 포인트인 체크 포인트가 있는 주파수. 너는 이것을 바꿀 필요가 없습니다.
auto.create.topics.enable | true | 서버에 있는 토픽의 자동생성을 가능하게 합니다. 이것이 true로 설정된 경우 생산,소비,또는 존재하지 않는 토픽에 대한 메타데이터를 가져오기 위한 시도는 자동으로 디폴트 복제 요소와 파티션의 번호와 함께 이것을 생성합니다.
controller.socket.timeout.ms | 30000 | 복제본에 파티션 관리 컨트롤러의 명령에 대한 소켓 타임아웃.
controller.message.queue.size | 10 | 컨트롤러와 브로커 간 채널에 대한 버퍼 사이즈.
default.replication.factor | 1 | 자동으로 생성되는 토픽에 대한 디폴트 복제 요소.
replica.lag.time.max.ms | 10000 | 팔로워가 시간의 윈도우에 대한 아무 페치 요청을 전송하지 않은 경우,리더는 ISR(복제본 동기화)로부터 팔로워를 제거할 수 있고 죽은걸로 취급할 수 있습니다.
replica.lag.max.messages | 4000 | 복제본이 리더 뒤에 이 많은 메세지보다 떨이질 경우,리더는 ISR로부터 팔로워를 제거할 수 있고 이것을 죽은걸로 취급할 수 있습니다.
replica.socket.timeout.ms | 30*1000 | 네트워크 소켓 타임아웃은 데이터를 복제하라고 리더에게 요청합니다.
replica.socket.receive.buffer.bytes | 64*1024 | 네트워크 소켓 리시브 버퍼는 데이터를 복제하라고 리더에게 요청합니다.
replica.fetch.max.bytes | 1024*1024 | 복제 요청 패치에 있는 각각의 파티션에 대해 가져오는 것을 시도하는 메세지 바이트의 수는 리더에게 전송됩니다.
replica.fetch.wait.max.ms | 500 | 리더 복제에 의해 전송되는 패치 요청에서 리더에게 도달하는 데이터에 대한 최대 대기 시간.
replica.fetch.min.bytes | 1 | 리더 복제에서 패치 요청에 대한 각 패치 응답을 기다리는 최소의 바이트. 바이트가 충분하지 않은 경우, 많은 바이트가 도착하는 이  replica.fetch.wait.max.ms까지 기다립니다.
num.replica.fetchers | 1 | 리더에서 메세지를 복제하는 데 사용되는 스레드의 수. 이 값을 늘리는 것은 팔로워 브로커에 I/O 병렬 처리 수준을 높일 수 있습니다.
replica.high.watermark.checkpoint.interval.ms | 5000 | 복구를 다루는 디스크에 이것의 높은 워터마크를 저장하는 각각의 복제본을 가진 주파수
fetch.purgatory.purge.interval.requests | 10000 | 퍼게토리 요청 패치의 제거 간격(요청 수).
producer.purgatory.purge.interval.requests | 10000 | 프로듀서 요청 패치의 제거 간격(요청 수).
zookeeper.session.timeout.ms | 6000 | 주키퍼 세션 타임 아웃. 서버가 이 시간내에 주키퍼에 하트비트 실패한경우 서버가 죽은걸로 취급합니다. 이것을 너무 낮게 설정하면 서버는 잘못하여 죽은 걸로 간주; 이것을 너무 높게 설정하면 이것은 진짜 죽은 서버를 인식하는데 너무 오랜 시간이 걸릴 수 있습니다.
zookeeper.connection.timeout.ms | 6000 | 클라이언트가 주키퍼 연결을 설정하기 위해 기다리는 최대 시간.
zookeeper.sync.time.ms | 2000 | 얼마나 멀리 ZK팔로워가 ZK리더 뒤에 있는지.
controlled.shutdown.enable | false | 브로커의 통제된 중단을 활성화합니다. 활성화된경우, 브로커는 자기를 중단하기전에 모든 리더들을 다른 몇몇의 브로커들로 움직일 수 있습니다. 이것은 중단하는동안 윈도우 비가동률을 줄입니다.
controlled.shutdown.max.retries | 3 | 부정 종료를 실행하기 전에 성공적으로 제어된 종료를 완료하는 재시도 횟수
controlled.shutdown.retry.backoff.ms | 5000 | 종료 시도 사이의 백오프 시간.
auto.leader.rebalance.enable | false | 이것을 활성화한경우 컨트롤러는 자동으로 이것이 가능하면 주기적으로 각 파티션에 대한 "선호"복제에 리더쉽을 반환함으로써 브로커 간 파티션에 대한 리더쉽을 맞추려고 시도할 것입니다.
leader.imbalance.per.broker.percentage | 10 | 브로커당 허용하는 리더 불균형의 퍼센트. 컨트롤러는 이 비율이 브로커당 설정된 값을 넘어가는 경우 리더쉽을 재균형합니다.
leader.imbalance.check.interval.seconds | 300 | 리더 불균형을 확인하는 주파수.
offset.metadata.max.bytes | 1024 | 클라이언트가 그들의 오프셋에 저장할 수 있는 메타데이터의 최대 양.

브로커 설정에 대한 자세한 내용은 스칼라 클래스 kafka.server.KafkaConfig에서 찾을 수 있습니다.

##### 토픽수준의 설정

주제에 대한 적절한 설정은 글로벌 디폴트와 조절 토픽당 오버라이드 둘 다 가지고있습니다. 토픽당 설정이 주어지지않으면 글로벌 디폴트가 사용됩니다. 오버라이드는 하나이상의 --config 옵션을 제공하면서 토픽생성시간에 설정할 수 있습니다. 이 예는 *my-topic*라는 토픽을 사용자최대메세지크기와 플러시비율과 함께 생성:
	> bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic my-topic --partitions 1
	      --replication-factor 1 --config max.message.bytes=6400 --config flush.messages=1

또 오버라이드는 토픽 명령은 바꾸거나 대안토픽명령을 사용하여 늦게 설정할 수 있습니다. 이 예는 *my-topic*에 대한 최대 메세지 크기 업데이트:
	> bin/kafka-topics.sh --zookeeper localhost:2181 --alter --topic my-topic
	   --config max.message.bytes=12800

오버라이드를 제거하는 것도 할 수 있다.
	> bin/kafka-topics.sh --zookeeper localhost:2181 --alter --topic my-topic
	   --deleteConfig max.message.bytes

다음은 토픽수준의 설정입니다. 서버 디폴트 속성(Server Default Property) 제목, 서버 설정에 이 디폴트를 설정하는 아래에 제공된 이 속성에 대한 서버의 디폴트 설정은 너가 명시된 오버라이드가 업는 토픽에 주어진 디폴트를 바꾸는 걸 허용합니다.

속성 | 디폴트 | 서버 디폴트 속성(Server Default Property) |      묘사      |
----|-------|----------------------------------------|---------------|
cleanup.policy | delete | log.cleanup.policy | "컴팩트" 또는 "삭제" 중 하나인 스트링입니다. 이 스트링은 이전 로그 세그먼트에서 사용하는 보존정책을 지정합니다. 디폴트 정책("삭제")은 그들의 보존시간 또는 제한시간에 도달하면 이전 세그먼트를 버립니다. "컴팩트"설정은 토픽에 [로그 컴팩션](http://kafka.apache.org/documentation.html#compaction)을 가능하게 합니다.
delete.retention.ms | 86400000(24 hours) | log.cleaner.delete.retention.ms | [로그 압축된](http://kafka.apache.org/documentation.html#compaction) 토픽에 대해 삭제 표시 마커들을 유지하는 시간. 또 이 설정은 그들이 마지막 단계의 유효한 스냅샷을 얻을 수 있도록 오프셋0에서 부터 시작하면 컨슈머가 읽기를 완료해야하는 시간에 바운드를 제공합니다.(그렇지 않으면 그들이 자신의 스캔을 완료하기전에 삭제 표시가 수집될 수 있습니다.)
flush.messages | None | log.flush.interval.messages | 이 설정은 우리가 로그에 기록된 데이터의 fsync를 강제로하는 간격을 지정할 수 있습니다. 예를들어 이것이 1로 설정되면 우리는 모든 메세지후에 fsync로 할 것입니다; 이것이 5로 설정되면 우리는 모든 다섯개 메세지 후에 fsync로 할 것입니다. 일반적으로 우리는 너에게 이것을 설정하지 말고 내구성을 위해 복제를 사용하고 더 효과적이기 때문에 운영체제의 백그라운드 플러시 능력을 허용하라고 추천합니다. 이 설정은 토픽당 기초에 오버라이딩 할 수 있습니다.([토픽당 설정 섹션](http://kafka.apache.org/documentation.html#topic-config)을 참고)
flush.ms | None | log.flush.interval.ms | 이 설정은 로그에 기록된 데이터의 fsync를 강제로 하는 시간 간격을 지정할 수 있습니다. 예를 들어, 이것이 1000으로 설정된다면 우리는 1000ms를 지난 후에 fsync를 할 것입니다. 일반적으로 우리는 너가 이것을 설정하지 않고 내구성을 위해서 복제를 사용하고 더 효과적이기 때문에 운영체제의 백그라운드 플러시 능력을 허용하라고 추천합니다.
index.interval.bytes | 4096 | log.index.interval.bytes | 이 설정은 카프카가 오프셋 인덱스에 인덱스 항목을 추가하는 빈도를 조절합니다. 디폴트 설정은 우리가 메세지를 거의 모든 4096바이트를 인덱스한다고 보장합니다. 더 인덱싱하는 것은 로그안에 정확한 위치에 더 가깝게 이동해서 읽는걸 허용하지만 인덱스가 커집니다. 너는 아마도 이것을 바꿀 필요가 없습니다.
max.message.bytes | 1,000,000 | message.max.bytes | 이것은 가장 큰 메세지 크기입니다. 카프카는 이 토픽에 추가할 수 있습니다. 너가 사이즈를 증가시키면 그들이 이 크기에 메세지를 페치할 수 있도록 너는 또한 너의 컨슈머의 페치사이즈도 증가시켜야 한다는걸 주의해야합니다.
min.cleanable.dirty.ratio | 0.5 | log.cleaner.min.cleanable.ratio | 이 설정은 로그 컴팩터가 로그를 청소하는 시도의 빈도를 조절합니다([로그 컴팩션](http://kafka.apache.org/documentation.html#compaction)이 사용가능하다고 가정). 기본적으로 우리는 50%이상의 로그가 압축되있는 로그를 청소하는걸 피해야 합니다. 이 비율은 복제에 의한 로그에 낭비하는 최대 공간을 바운드합니다(50%에서 로그의 대부분의 50%는 복제될 수 있습니다). 더 높은 비율은 더 낮고,더 효과적인 청소를 의미하지만 로그에 공간을 더 낭비하는 것도 의미합니다.
retention.bytes | None | log.retention.bytes | 이 설정은 우리가 "삭제"보유정책을 사용하는 경우 우리가 공간 확보를 위해서 이전 로그 세그먼트를 버리기전에 로그가 성장할 수 있는 최대 크기를 제어합니다. 기본적으로 시간제한만 크기제한이 없습니다.
retention.ms | 7 days | log.retention.minutes | 이 설정은 우리가 "삭제"보유정책을 사용하는 경우 우리가 공간 확보를 위해서 이전 로그 세그먼트를 버리기전에 로그가 성장할 수 있는 최대 크기를 제어합니다. 이것은 얼마나 빨리 컨슈머가 그들의 데이터를 읽을 수 있는지를 나타낸 SLA를 나타냅니다.
segment.bytes | 1 GB | log.segment.bytes | 이 설정은 로그에 대한 세그먼트 파일을 제어합니다. 유지와 청소는 항상 한번에 파일을 수행합니다. 그래서 더 큰 세그먼트 크기는 더 낮은 파일을 의미하지만 유지를 통해 덜 세분화된 것을 제어합니다.(Retention and cleaning is always done a file at a time so a larger segment size means fewer files but less granular control over retention).
segment.index.bytes | 10 MB | log.index.size.max.bytes | 이 설정은 오프셋을 파일 위치로 맵핑하는 인덱스의 사이즈를 조절합니다. 우리는 이 인덱스 파일을 미리 할당하고 이것을 로그 롤 후에 수축합니다. 너는 일반적으로 이 설정을 바꿀 필요가 없습니다.
segment.ms | 7 days | log.roll.hours | 이 설정은 세그먼트 파일이 기억이 삭제되거나 오래된 데이터를 압축하는 걸 완전히 보장하지 않더라도 어떤 카프카가 롤에 로그를 강요한 후 시간기간을 조절합니다.

#### 3.2 컨슈머 설정

필수 컨슈머 설정은 다음과 같습니다:
* group.id
* zookeeper.connect

속성 | 디폴트 | 서술
----|-------|------
group.id | | 유일하게 컨슈머가 속해있는 소비자프로세스의 그룹을 식별하는 스트링. 같은 그룹id를 설정함으로써 다수의 프로세스들은 그들이 같은 컨슈머 그릅의 일부분이라는걸 나타냅니다.
zookeeper.connect | | 호스트와 포트가 주키퍼 서버의 호스트와 포트인 형식 hostname:port에 있는 주키퍼 연결 스트링을 명시합니다. 주키퍼 기계가 다운될 때 다른 주키퍼를 통해 연결하기 위해서 너는 또한 형식 hostname1:port1,hostname2:port2,hostname3:port3에 있는 다수의 호스트를 명시해야합니다. 또 서버는 글로벌 주키퍼 명칭공간에 어떤 경로아래에 데이터를 넣는 주키퍼 연결 스트링의 부분으로 주키퍼 chroot 경로를 가질 수 있습니다. 그렇다면 컨슈머는 연결 스트링에서 같은 chroot 경로를 사용해야 합니다. 예를들어 /chroot/path 의 chroot 경로를 주기위해 너는 hostname1:port1,hostname2:port2,hostname3:port3/chroot/path 같은 연결 스트링을 제공해야합니다.
consumer.id | null | 설정되지 않앗으면 자동으로 생성됩니다.
socket.timeout.ms | 30*1000 | 네트워크 요청을 위한 소켓 타임아웃. 실제 타임아웃 세트는  max.fetch.wait + socket.timeout.ms 될 것입니다.
socket.receive.buffer.bytes | 64*1024 | 네트워크 요청을 위한 소켓 리시브 버퍼
fetch.message.max.bytes | 1024*1024 | 각 페치 요청의 각 토픽파티션에 대한 페치를 시도하는 메세지 바이트의 수. 이런 바이트는 각 파티션에 대한 메모리로 읽혀질 것입니다, 그래서 이것은 컨슈머에 의해 사용되어지는 메모리를 조절하는데 도움을 줍니다. 페치 요청 크기는 적어도 서버가 허용하거나 프로듀서를 컨슈머가 페치할 수 있는 것보다 더 크게 메세지를 전송하는 것이 가능한 최대 메세지크기만큼 커야합니다.
auto.commit.enable | true | 사실이면,주기적으로 이미 컨슈머가 가져온 메세지의 주키퍼 오프셋 커밋. 이 커밋된 오프셋은 새로운 컨슈머가 시작되는 위치로서 프로세스가 실패할때 사용되어질 것입니다.
auto.commit.interval.ms | 60*1000 | 컨슈머 오프셋을 주키퍼에 커밋하는 MS에 주파수.
queued.max.message.chunks | 10 | 소비에 대해 버퍼하는 메세지 청크의 최대 수. 각 청크는 fetch.message.max.bytes 까지 할 수 있습니다.
rebalance.max.retries | 4 | 새로운 컨슈머가 컨슈머 그룹에 합류할때 컨슈머의 세트가 각 컨슈머에 파티션을 할당하는 "재균형" 로드를 시도합니다. 컨슈머의 세트가 바뀔때 이 임무가 일어나는 동안 재균형은 실패하고 다시 시도합니다. 이 설정은 포기하기전에 시도의 최대수를 조절합니다.
fetch.min.bytes | 1 | 페치 요청에 대한 서버가 반환할 수 있는 데이터의 최소양. 사용할 수 있는 데이터가 부족하면 요청은 요청에 답하기전에 많은 데이터를 축적하는 것을 기다릴 것입니다.
fetch.wait.max.ms | 100 | 즉시 fetch.min.bytes를 만족하는 데이터가 부족할때 페치 요청에 답하기전에 서버가 막는 최대시간.
rebalance.backoff.ms | 2000 | 재균형하는 동안 재시도 간의 백오프 시간.
refresh.leader.backoff.ms | 200 | 이것의 리더를 잃은 파티션의 리더를 결정하기전에 대기하는 시간이 백오프 시간.
auto.offset.reset | largest | 오프셋이 범위를 벗어나거나 주키퍼에 초기화 오프셋이 없을 때 해야 할 일:     ^ 최소 : 자동으로 오프셋을 가장 작은 오프셋으로 리셋.  ^최대 : 자동으로 오프셋을 가장 큰 오프셋으로 리셋  ^다른것 : 예외를 컨슈머에게 던지다.
consumer.timeout.ms | -1 | 지정한 간격 후 메세지가 소비를 불가능한 경우 컨슈머에게 타임아웃 예외를 던지다.
client.id | group id value | 클라이언트ID는 호출 추적을 도와주기 위해 각 요청으로 보내지는 사용자가 지정한 스트링입니다. 이것은 논리적으로 요청하는 어플리케이션을 구별합니다.
zookeeper.session.timeout.ms | 6000 | 주키퍼 세션 타임아웃. 소비자가 이 기간동안 주키퍼에 하트비트를 실패하면 이것은 죽은걸로 취급되고 재균형이 발생할 것 입니다.
zookeeper.connection.timeout.ms | 6000 | 주키퍼에 연결하는 동안 클라이언트가 기다리는 최대시간.
zookeeper.sync.time.ms | 2000 | ZK팔로워가 얼마나 멀리 ZK지도자 뒤에 있을 수 있는지

컨슈머 설정에 대한 자세한 내용은 스칼라 클래스 kafka.consumer.ConsumerConfig에서 찾을 수 있습니다.

#### 3.3 프로듀서 설정

프로듀서를 위한 필수 구성 특성은 다음과 같습니다:
* metadata.broker.list
* request.required.acks
* producer.type
* serializer.class

속성 | 디폴트 | 서술 |
----|-------|------|
metadata.broker.list | | 이것은 부트스트래핑을 위하고 프로듀서는 이것을 메타데이터(토픽,파티션,그리고 복제본)를 얻기위해서 사용합니다. 실제 데이터를 전송하는 소켓 연결은 메타데이터에서 반환된 브로커 정보에 기반하여 설정합니다. 형식은 host1:port1,host2:port2이고, 목록은 브로커의 일부 또는 브로커의 일부를 가리키는 VIP가 될 수 있습니다.
request.required.acks|  0 | 이 값은 생산요청이 완성됫다고 취급될 때 조절합니다. 특히,얼마나 다른 브로커가 그들의 로그에 데이터를 커밋하고 이것을 리더에게 알릴 수 있을까? 전형적인 값은  ^ 0, 프로듀서가 절대 브로커 확인을 기다리지 않는 것을 의미합니다(0.7과 같은 행동).이 옵션은 가장 낮은 지연을 제공하지만 가장 약한 내구성 보장을 제공하기도 합니다(어떤 데이터는 서버가 실패할때 손실될 수도 있습니다). ^ 1, 리더 복제본이 데이터를 수신한 후 프로듀서가 확인을 얻는 것을 의미합니다. 이 옵션은 서버가 성공적으로 요청을 승인할때까지 클라이언트가 기다리는 더 나은 내구성을 제공합니다(지금은 죽은 리더에 기록되어있지만 아직 복제되지 않은 메시지만 손실됩니다). ^ -1, 모든 동기화 복제본이 데이터를 받은 후에 프로듀서가 확인을 얻는 것을 의미합니다. 이 옵션은 최상의 내구성을 제공하고,우리는 적어도 동기 복제에 하나가 남아있는 한 어떤 메세지도 손실되지 않음을 보장합니다.
request.timeout.ms | 10000 | 클라이언트에게 에러를 다시 보내기전에 request.required.acks 요건을 충족시키는 시도를 기다리는 시간.
producer.type | sync | 이 파라미터는 메세지가 백그라운드 스러드에 비동기로 보내지는지 를 명시합니다. 유효한 값은 비동기 전송을 위한(1) 비동기통신이고 동기 전송을 위한 (2) 동기통신입니다. 프로듀서가 비동기로 설정함으로써 우리는 요청(처리량이 좋은)을 같이 배치할 수 있지만 보내지 않은 데이터를 떨어뜨리는 클라이언트 기계의 가능성을 엽니다.
serializer.class | kafka.serializer.DefaultEncoder | 메세지의 직렬 클래스. 디폴트 인코더는 byte[]를 받고 같은 byte[]를 반환합니다.
key.serializer.class | | 키의 시리얼 클래스(아무것도 주어지지 않은 경우 메세지와 같은 디폴트).
partitioner.class | kafka.producer.DefaultPartitioner | 하위 토픽 사이에 메세지를 구획하는 파티션 클래스. 디폴트 파티셔너는 키의 해시에 기초합니다.
compression.codec | none | 이 파라미터는 이 프로듀서에 의해 발생된 모든 데이터에 대한 압축코덱을 명시할 수 있습니다. 유효한 값은 "none","gzip" 그리고 "snappy"입니다.
compressed.topics | null | 이 파라미터는 압축이 특정 토픽에 대해 변해야 하는지를 설정할 수 있습니다. 압축 코덱이 NoCompressionCodec 이외만 있는 경우 명시된 토픽에 대한 압축을 할 수 있습니다. 압축된 토픽의 목록이 비어있다면, 모든 토픽에 명시된 압축 코덱을 가능하게 해야합니다. 압축 코덱이 NoCompressionCodec인 경우, 압축은 모든 토픽에 대해 사용할 수 없습니다.
message.send.max.retries | 3 | 이 속성은 생산자가 자동으로 실패한 전송 요청을 재시도하게 합니다. 이 속성은 이런 실패가 발생할때 재시도 횟수를 명시합니다. 0이 아닌 값을 여기에 설정하는 것은 메세지가 보내지지만 확인 응답이 손실되게 하는 네트워크 에러의 경우에 중복을 초래할 수 있는 걸 주목.
retry.backoff.ms | 100 | 각 재시도 전에, 프로듀서는 새로운 리더가 뽑혀 있는지 확인하기 위해서 관정한련된 토픽의 메타데이터를 새로 고칩니다. 리더 선거가 다소 시간이 걸리니까, 이 속성은 메타데이터를 새로 고치기전에 프로듀서가 기다리는 시간을 명시해야 합니다.
topic.metadata.refresh.interval.ms | 600*1000 | 실패(파티션 잃음,리더 사용불가...등등)할때 일반적으로 프로듀서는 브로커로부터 토픽 메타데이터를 새로 고칩니다. 이것은 또한 정기적으로 조사합니다(기본:매 10분마다 600000ms). 너가 이 음의 값으로 설정하면, 메타데이터는 실패만 얻을 것입니다. 너가 이것을 0으로 설정하면, 메타데이터는 각 메세지가 보내진후(권장하지 않음) 새로 고쳐 얻을 것입니다. 중요 노트: 새로 고침 메세지가 전송된 후에만 일어납니다,그래서 프로듀서가 메세지를 보내지 않은 경우 메타데이터는 새로 고쳐지지 않습니다.
queue.buffering.max.ms | 5000 | 비동기 모드일때 데이터를 버퍼하는 최대 시간. 예를 들어 100의 설정은 한번에 보내는 메세지의 100ms와 함께 배치를 시도합니다. 이것은 처리량을 향상시키지만 버퍼링 때문에 메세지 배달 지연을 추가합니다.
queue.buffering.max.messages | 10000 | 프로듀서가 차단해야하거나 데이터를 떨어뜨리기 전에 비동기모드를 사용할 때 프로듀서를 줄지어 보내지 않은 메세지의 최대 수.(The maximum number of unsent messages that can be queued up the producer when using async mode before either the producer must be blocked or data must be dropped).
queue.enqueue.timeout.ms | -1 | 비동기모드로 실행할때 메세지를 떨어트리기 전에 막는 시간과 버퍼는 queue.buffering.max.messages에 도달합니다. 큐가 찬 경우 0으로 설정하면 0이벤트가 즉시 인큐하거나 삭제됩니다(프로듀서 전송 요청은 차단하지 않습니다). -1로 설정하면 프로듀서는 무기한으로 차단하고 기꺼이 전송을 삭제하지 않습니다.
batch.num.messages | 200 | 비동기모드를 사용할때 한 배치에서 보내지는 메세지의 수. 프로듀서는 이 메세지의 수가 보낼 준비 또는 queue.buffer.max.ms에 도달 할때까지 기다릴 것입니다.
send.buffer.bytes | 100*1024 | 소켓 쓰기 버퍼 크기
client.id | "" | 클라이언트 id는 호출추적을 도와주기 위해 각 요청에 전송 유저가 지정한 스트링입니다. 이것은 논리적으로 요청하는 어플리케이션을 구별합니다.

프로듀서 설정에 대한 자세한 내용은 스칼라 클래스 kafka.producer.ProducerConfig 에서 볼 수 있습니다.

#### 3.4 새 프로듀서 설정

우리는 기존에 존재하는 프로듀서 대체에 노력하고 있습니다. 이제 코드는 트렁크에서 사용가능하고 베타 품질로 취급될 수 있습니다. 다음은 새로운 프로듀서를 위한 설정입니다.

이름 | 타입 | 디폴트 | 중요성 | 서술  |
----|------|-------|-------|------|
bootstrap.servers | list | | high | 카프카 클러스터에 초기연결설정을 위해 사용한 호스트/포트 쌍의 목록. 데이터는 부트스트래핑에 대해 여기에 지정되는 서비에 관계없이 모든 서버를 통해 균형있게 로드될 것입니다-이 목록은 단지 서버의 풀세트를 발견하기 위해 사용한 초기 호스트에만 영향을 줍니다. 이 목록은 형식 host1:port1,host2:port2에 있어야 합니다. 이런 서버가 단지 전체 클러스터 멤버쉽(동적으로 변화할 수 있는)을 발견하기 위한 초기 연결에만 사용되기 때문에, 이 목록은 전체 서버의 세트를 포함할 필요는 없습니다(하지만 서버가 다운된 경우,너는 하나이상을 원할지도 모릅니다). 목록에 이용가능한 서버가 없는 경우 데이터를 보내는 것은 이용이 가능할때까지 실패할 것입니다.
acks | string | 1 | high | 완료 요청을 고려하기전에 프로듀서는 리더에게 받으라고 요청하는게 확인 횟수 입니다. 이것은 전송된 기록의 내구성을 조절합니다. 다음 설정은 일반적이다: acks = 0 0으로 설정한 경우 프로듀서는 모든 서버에서의 승인을 기다리지 않습니다. 기록은 즉시 소켓버퍼에 추가하거나 전송을 고려합니다. 보장은 서버가 이 경우에 기록을 받았다고 할 수 없고 재시도 설정이 적용되지 않습니다(일반적으로 클라이언트는 모든 실패를 알지못해서). 각 레코드에 다시 주어진 오프셋은 항상 -1로 설정됩니다. acks = 1 이것은 리더가 자신의 로컬 로그에 기록을 작성할 수 있지만 모든 팔로워에서 전체 확인을 기다리지 않고 응답한다는 의미입니다. 이 경우 리더는 기록을 확인후에 즉시 실패하지만 팔로워가 다음 복제전에 기록은 삭제됩니다. acks = all 이것은 리더가 기록을 확인하기 위해 동기 복제의 전체 세트를 기다린다는 의미입니다. 이것은 기록이 적어도 동기복제가 남아있는한 손실되지 않는다는 것을 보장합니다. 이것은 가장 강한 이용가능한 보장입니다. ^ acks=2와 같은 다른 설정들은 또한 가능하고, 주어진 확인의 수를 요구하지만 일반적으로 이것은 덜 유용합니다.
buffer.memory | long | 33554432 | high | 프로듀서 메모리의 전체 바이트는 서버로 전송 대기중인 버퍼 기록을 사용할 수 있습니다. 기록이 서버에 그들을 보내는 것보다 더 빠르게 보내면 프로듀서는 막거나 block.on.buffer.full에 의해 명시한 선호에 기반한 예외를 쓰로우 합니다. 이 설정은 프로듀서가 사용하는 전체 메모리에 대략 일치해야하지만, 버퍼링을 위해 프로듀서가 모든 메모리를 사용하지 않기 때문에 하드 바인딩하지 않습니다. 일부 추가 메모리는 기내 요청 유지뿐만 아니라 압축(압축이 가능한 경우)에 사용되어집니다.
compression.type | string | none | high | 프로듀서에 의해 생선된 모든 데이터에 대한 압축 타입. 디폴트는 none 입니다(즉,압축 없음). 유효한 값은 none,gzip,또는 snappy입니다. 압축은 데이터의 전체 배치라서, 배치의 효능은 또한 압축 비율에 영향을 줍니다(더 배치하는 것은 더 나은 압축을 의미).
retries | int | 0 | high | 0보다 큰 값을 설정하는 것은 클라이언트가 잠재적으로 일시적인 에러와 함께 실패를 보내는 누군가의 아무 기록을 다시 보내게 합니다. 이 재시도는 클라이언트가 에러를 받을 때 기록을 다시 보내는 경우와 다르지 않습니다. 두개의 기록이 하나의 파티션에 보내는 경우 때문에 재시도를 허용하는 것은 잠재적으로 기록의 순서를 바꾸고, 첫 번째는 실패하고 재시도하지만, 두 번째는 성공하고나서,두번째 기록이 첫번째로 나타날 수 있습니다.
batch.size | int | 16384 | medium | 프로듀서는 다수의 기록이 같은 파티션에 보내질때마다 더 적은 수의 요청으로 배치 기록을 시도합니다. 이것은 클라이언트와 서버 모두의 성능을 도와줍니다. 이 설정은 바이트에 디폴트 배치 크기를 조절합니다. 어떠한 시도도 이 크기보다 더 큰 배치 기록을 만들 수 없습니다. 브로커에 보낸 요청은 다수의 배치, 전송 될 수 있는 데이터와 각 파티션에 하나를 포함합니다. 작은 배치 크기는 덜 일반적이게 배칭을 만들고 처리량을 줄일 것입니다(제로의 배치크기는 완전히 배치 해제됩니다). 매우 큰 배치 크기는 우리가 항상 추가기록의 예상에 지정된 배치 크기의 버퍼를 할당하는 것과 같이 좀 더 쓸데없이 메모리를 사용합니다.
client.id | string | | medium | 요청을 할 때 서버에 전달하는 id 스트링. 이것의 목적은  요구에 포함되는 논리 어플리케이션 이름을 허용함으로써 단지 아이피/포트 이후 요청의 소스를 추적할 수 있어야 합니다. 그 어플리케이션은 아무 로깅과 통계 이외의 기능적인 목적이 없어서 이것이 원하는 스트링으로 설정합니다.
linger.ms | long | 0 | medium | 하나의 일괄 요청에 대한 전송요청 사이에 도착한 아무 기록과 결합한 프로듀서 그룹. 일반적으로 이것은 레코드가 발송될 수 있는 것보다 더 빨리 도착할때 로드아래에서만 발생합니다. 그러나 어떤 경우에는 클라이언트는 심지어 보통의 로드아래에서 요청횟수를 줄이기를 원합니다. 이 설정은 이것을 인공 지연의 적은양을 추가하면서 해냅니다.-즉,바로 기록을 보내기 보다는 프로듀서가 전송이 같이 배치되도록 다른 기록들이 전송되기 위해 주어진 지연까지 기다릴 것 입니다. 이것은 TCP에 네이글의 알고리즘과 유사하다고 생각할 수 있습니다. 이 설정은 배치에 대한 지연에 상한을 제공 : 우리가 파티션에 대한 기록의 배치 크기 가치를 얻을 때 이것은 바로 설정에 관계없이 보내질 것입니다,하지만 이 파티션에 대한 축적된 많은 바이트들이 우리가 가진 것보다 적으면 우리는 지정된 시간동안 보여주기 위한 더 많은 기록을 기다리기 위해 '링거(linger)'할 것입니다. 이 설정은 0으로 기본값을 설정합니다(즉,지연 없음). 예를들어, linger.ms=5로 설정하는 것은 전송요청횟수를 감소시키는 효과를 얻을수 있지만 로드의 absense에 전송기록 지연의 5ms까지 추가할 수 있습니다.
max.request.size | int | 1048576 | medium | 요청의 최대크기. 또한 이것은 효과적으로 최대 기록 크기에 덮어씌웁니다. 이것과 다른 기록 크기에 서버는 자신의 캡을 가지고 있습니다. 이 설정은 생산자가 큰 요청을 전송하지 않기 위해 한 요청에 전송할 수 있는 기록 배치의 수를 제한합니다.
receie.buffer.bytes | int | 32768 | medium | 데이터를 읽을 때 쓰는 TCP 리시브 버퍼의 크기.
send.buffer.bytes | int | 131072 | medium | 데이터를 전송할 때 쓰는 TCP 센드 버퍼의 크기.
timeout.ms | int | 30000 | medium | 이 설정은 프로듀서가 acks 설정으로 지정한 승인 요청을 만족시키기 위해 서버가 팔로워로부터 승인을 기다리는 최대시간을 조절합니다. 타임아웃이 지날 때 요청된 승인수가 충분하지 않으면 에러가 반환됩니다. 이 타임아웃은 서버측에서 측정되고, 요청 네트워크 지연에 포함되지 않습니다.
block.on.buffer.full | boolean | true | low | 우리의 메모리 버퍼가 소진될 때 우리는 새 기록(블록)을 받는 걸 멈추거나 에러를 보내야 합니다. 기본적으로 이 설정은 true이고 우리는 차단합니다,하지만 일부 시나리오에서는 막는 것은 바람직하지 않고 바로 에러를 보내는 것이 더 좋습니다. 이것을 false로 설정하는 것은 그것을 이뤄낼 것입니다 : 기록이 전송되고 버퍼공간이 가득 차면 프로듀서가 BufferExhaustedException을 보냅니다.
metadata.fetch.timeout.ms | long | 60000 | low | 처음 데이터는 우리가 어느 서버 호스트가 토픽의 파티션인지 알기 위해서 그 토픽에 대한 메타데이터를 패치해야하는 토픽에 전송됩니다. 이 설정은 클라이언트에게 다시 예외를 보내기 전에 우리가 성공 패치 메타데이터 를 기다리는 것을 차단하는 최대시간을 조절합니다.
metadata.max.age.ms | long | 300000 | low | 비록 우리가 앞서는 어떤 파티션 리더십 변화를 못 볼지라도 우리가 메타데이터의 새로고침을 강요받은 이후의 밀리초 시간은 새로운 아무 브로커나 파티션들을 발견합니다.
metric.reporters | list | [] | low | 메트릭 리포터로 사용하는 클래스의 목록. MetricReporter 인터페이스를 구현하는 것은 새로운 메트릭 생성을 알려주는 클래스에 연결할 수 있습니다. JMxReporter는 항상 JMX통계등록을 포함합니다.
metrics.num.samples | int | 2 | low | 메트릭을 계산하기 위해 유지한 샘플의 수.
metrics.sample.window.ms | long | 30000 | low | 메트릭스 시스템은 고정된 윈도우 크기를 넘어 변경가능한 샘플의 수를 유지합니다. 이 설정은 윈도우의 크기를 조절합니다. 예를 들어 우리는 각각 30초 동안 측정된 두 개의 샘플을 유지할 수 있습니다. 윈도우가 만료될 때 우리는 지우고 가장 오래된 윈도우를 덮어 씁니다.
reconnect.backoff.ms | long | 10 | low | 연결이 실패할때 주어진 호스트를 재연결하는 시도전 기다리는 시간. 이것은 클라이언트가 반복적으로 타이트 루프에서 호스트에 연결을 시도하는 경우를 방지합니다.
retry.backoff.ms | long | 100 | low | 주어진 토픽파티션에 실패한 생산 요청을 재시도하기 전에 기다리는 시간. 이것은 타이프 루프에서 전송-실패 반복을 방지합니다.

### 4. 디자인

#### 4.1 동기부여

우리는 카프카를 [큰 회사가 가지고 있는](http://kafka.apache.org/documentation.html#introduction) 모든 실시간 데이터 피드를 다루는 통합된 플랫폼으로서 활동할 수 있도록 디자인합니다. 이것을 하기 위해서 우리는 사용 사례의 상당히 광범위한 세트를 통해 생각했습니다.  

이것은 실시간 로그 집계와 같은 높은 볼륨 이벤트 스트림을 지원하기 위해 높은 처리량을 가져야 합니다.  


이것은 오프라인 시스템으로 부터 정기적인 데이터 로드를 지원할 수 있는 큰 데이터 백로그로 적절하게 처리해야합니다.  

이것은 또한 시스템이 더 전통적인 메세징 사용사례를 다루기 위해 낮은 지연 배달을 처리하는 것을 의미합니다.  

우리는 파티션,분산,이 새로운 것을 생성하는 피드들의 실시간 처리,파생 피드를 지원해주길 원합니다. 이것은 우리의 파티셔닝 과 컨슈머 모델에 동기부여합니다.  

마지막 스트림이 일하기 위해 다른 데이터 시스템에 공급되는 경우에,우리는 기계 고장의 존재에 고장허용범위를 새로운 시스템으로 보장해야합니다.  

마지막 스트림이 일하기 위해 다른 데이터 시스템에 공급되는 경우에,우리는 기계 고장의 존재에 고장허용범위를 새로운 시스템으로 보장해야합니다. 우리는 다음 섹션에서 디자인의 몇가지 요소를 소개할 것입니다.  

#### 4.2 고집

##### 파일 시스템을 두려워 하지 마세요!

카프카는 크게 저장 및 메세지를 캐싱 하는 파일시스템에 의존합니다. 집요한 구조가 경쟁력 있는 성능을 제공할 수 있는 의심많은 사람들이 만든 "디스크는 느리다"라는 일반적인 인식이 있습니다. 사실 디스크는 사용하는 방법에 따라 사람들이 기대한 것보다 더 빠르거나 더 느릴수 있습니다; 그리고 적절히 디자인한 디스크 구조는 종종 네트워크처럼 빠르게 할 수 있습니다.  

디스크 성능에 대한 중요한 사실은 하드드라이브의 처리량이 지난 십년동안 디스크 시크의 지연으로 나뉜 것입니다. 결과적으로 선형성능은 여섯 개의 7200rpm SATA RAID-5 배열은 약 600MB/sec 이지만 임의의 쓰기의 성능은 오직 약 100k/sec-6000X이상의 차이와 함께 [JBOD](http://en.wikipedia.org/wiki/Non-RAID_drive_architectures)설정에 기록됩니다. 이 선형 읽기와 쓰기는 예측가능한 모든 사용패턴의 대부분이고,운영체제에 의해 활용됩니다. 최신 운영체제는 미리 읽기와 큰 피지컬 쓰기에 큰 블록 배수와 더 작은 그릅 논리적 쓰기에 데이터를 프리패치하는 나중에쓰기 기술들을 제공합니다. 이 문제에 대한 더 자세한 내용은 [ACM Queue article](http://queue.acm.org/detail.cfm?id=1563874)에서 찾을 수 있습니다; 그들은 실제로 [어떤 경우에는 순차적인 디스크 접근이 무작위 메모리 접근보다 더 빠를 수 있는 것을](http://deliveryimages.acm.org/10.1145/1570000/1563874/jacobs3.jpg) 발견합니다.  

이 성능차이의 보상을 위해서 최신운영체제는 그들의 디스크 캐싱을 위한 메인 메모리의 사용에 점점더 적극적이되었습니다. 최신 OS는 적절히 모든 자유로운 메모리를 