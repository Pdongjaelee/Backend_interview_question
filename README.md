# Backend_interview_question
백엔드 개발자 면접 대비 질문 정리 공간

# 백엔드 개발자 면접 질문

## Java
<details>
<summary>JVM의 개념과 왜 필요한지 설명해주세요</summary>
<div markdown="1">

<p>자바 가상 머신(Java Virtual Machine)을 줄여 부르는 JVM의 역할은 바이트 코드로 컴파일된 자바 애플리케이션을 클래스 로더를 통해 읽어 자바 API와 함께 실행하는 것입니다.</p>
<p>JVM을 사용함으로 개발자가 작성하는 java 파일을 다양한 환경에서 실행할 수 있습니다.</p>
<p>다른 환경에서 만들어진 바이트 코드를 해당 OS의 JVM이 알맞게 기계어로 바꿔서 읽기 때문입니다.</p>
<p>즉, 모든 환경에서 사용할 수 있게 호환성을 위해 JVM이 필요합니다.</p>

</div>
</details>

<details>
<summary>JVM의 구조에 대해 설명해주세요</summary>
<div markdown="1">
<p>JVM의 구조는 클래스 로더(Class Loader), 실행 엔진(Execution engine), 실행 데이터 영역(Runtime Data Area) 등으로 이루어져 있습니다.</p>
<ul>  
<li>클래스 로더(Class Loader) : JVM 내로 바이트 코드(.class)를 로드하고, 링크를 통해 배치하는 작업을 합니다.</li>
<li>실행 엔진(Execution engine) : 클래스 로더에 의해 실행 데이터 영역에 배치된 바이트 코드(.class)를 실행하는 역할을 합니다.</li>
<li>실행 데이터 영역(Runtime Data Area) : JVM의 메모리 영역으로 Method영역, Heap 영역, Stack 영역, 네이티브 메소드 스택 영역(Native Method Library)으로 구성되어 있습니다.</li>
<ul>  
<li>Method영역 : 클래스의 멘버 변수, 메소드 정보, Type 정보, static, final 변수 등이 생성됩니다.</li>
<li>Heap 영역 : 사용자가 관리하는 인스턴스가 생성되는 공간으로 객체를 동적으로 생성하면 인스턴스가 Heap 영역의 메모리에 할당되어 사용됩니다.</li>
<li>Stack 영역 : 프로그램 실행 중 발생하는 메소드 호출과 복귀에 대한 정보를 저장합니다.</li>
<li>네이티브 메소드 스택 영역(Native Method Library) : Java 이외의 C언어와 같은 다른 언어가 필요한 경우, JNI 기술을 통해서 네이티브 메소드들이 바이트 코드로 변환되면서 사용되는 영역입니다.</li>
<li>PC Register : 스레드가 시작될 때 생성되며 현재 수행 중인 JVM 명령의 주소를 갖고 있습니다.</li>
</div>
</details>

<details>
<summary>Java 실행방식에 대해 설명해주세요</summary>
<div markdown="1">
<p>개발자가 .java로 되어있는 파일을 만들어 코드를 작성합니다. 그 파일에 작성한 코드가 자바 소스 코드가 됩니다.</p>
<p>인텔리제이같은 툴을 쓴다면 Build를 사용하여 소스파일을 컴파일합니다.</p>
<p>자바 컴파일러(javac)가 작성한 자바 소스 코드(.java)를 읽어 바이트 코드(.class)로 컴파일을 하는 것을 말합니다.</p>
<p>컴파일된 해당 바이트 코드(.class)는 JVM의 클래스 로더가 전달받습니다.</p>
 
<p>클래스 로더는 동적 로딩을 통해 필요한 클래스들을 로딩 및 링크하여 JVM내로 로드합니다.</p>
<p>JVM 내에 있는 실행 엔진(Execution engine)에 의해 기계어로 해석되어 실행 데이터 지역(Runtime Data Areas)에 배치됩니다.</p>
<p>java가 설치된 os라면 기계어로 해석된 파일을 실행할 수 있게됩니다.</p>
</div>
</details>

<details>
<summary>클래스와 인스턴스의 차이에 대해 설명해 주실 수 있을까요?</summary>
<div markdown="1">
<p>클래스는 객체가 어떤 속성을 갖는지 어떤 모양을 갖는지 미리 틀로 정해 놓는 설계도입니다.</p>
<p>인스턴스는 그 설계도를 통해 만들어진 객체를 말합니다.</p>
<p>클래스 안에서 인스턴스는 필드와 메소드만 바꿔서 다양하게 만들어 줄 수 있습니다.</p>
<p>이렇게 클래스 안에서 메소드를 실행시키는 객체를 만드는 행위를 인스턴스화라고 합니다.</p>
</div>
</details>

<details>
<summary>Annotation의 개념과 예시를 들어 설명해 주실 수 있을까요? </summary>
<div markdown="1">
<p>Annotation은 클래스와 메서드에 추가하여 각각 다양한 기능을 부여하는 역할을 합니다.</p>
<p>스프링의 mvc패턴을 구현할 때 대표적인 Annotation인 @Repository @Controller @Service 가 있습니다.</p>
<p>스프링에서 각각 클래스에 Repository, Controller, Service 역할을 명시해줍니다.</p>  
</div>
</details>
  
<details>
<summary>오버로딩과 오버라이딩 차이에 대해 설명해 주실 수 있을까요? </summary>
<div markdown="1">
<p>Override는 상속과 관련된 개념으로 부모 클래스의 메소드를 재 정의합니다.</p>
<p>Overload는 이름이 비슷하지만 상속과는 관련 없는 내용입니다.</p>
<p>Overload는 같은 메소드라도 매개변수만 다르면 정의하고 사용할 수 있는 개념입니다.</p>
<p>Overload는 같은 이름의 메소드를 여러 개 정의하고, 매개변수의 유형과 개수를 다르게 하여 다양한 유형의 호출에 응답할 수 있도록 하는 방식입니다.</p>
</div>
</details> 

<details>
<summary>오버로딩과 오버라이딩은 어떤 상황에서 사용하나요? </summary>
<div markdown="1">

<p>오버로딩은 동일한 기능을 하는 메소드를 하나의 이름으로 처리하는 것인데 예시로 println이 있습니다.</p>
<p>println은 int를 출력하든 char를 출력하든 모두 동일한 기능을 제공합니다.</p>
<p>만일 println이 오버로딩 기능이 없다면 타입에 따른 호출명을 다르게 해야합니다.</p>
<p>오버로딩이 있기 때문에 같은 기능을 하는 메서드를 하나의 이름인 println으로 사용할 수 있는 것입니다.</p>
<br>
<p>자식 클래스가 부모 클래스의 메소드를 상속 받아도 다른 기능을 사용하고자 하는 경우가 생길 수 있습니다.</p>
<p>그럴 때 오버라이딩을 사용합니다.</p>


</div>
</details> 
 
<details>
<summary>객체지향(oop)란 무엇인지 설명해주세요</summary>
<div markdown="1">
<p>필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법입니다.</p>
<p> 쉽게 정의하면 객체지향은 의존성 관리라고 말할 수 있습니다.</p>
<p> 객체지향으로 의존성을 관리함으로써 변경 영향을 최소화하고 객체마다 독립적인 개발이 가능해집니다.</p>
<p>객체 지향에는 4가지 특징이 있습니다.</p>
<ul>
<li> 캡슐화 : 데이터와 코드의 형태를 외부로부터 알 수 없게 하고, 데이터의 구조와 역할, 기능을 하나의 캡슐 형태로 만드는 방법입니다.</li>
<p>흔히 정보 은닉이라 많이 불리는데 캡슐화 방법에는 접근 제어자 private가 있습니다.</p>
<li> 추상화 : 클래스들의 공통적인 특성(변수, 메소드)들을 묶어 표현합니다.
<p>공통적인 특성이기 때문에 각각의 클래스를 확실히 구분할 수 없기에 추상화입니다.</p>
<li> 상속화 : 부모 클래스에 정의된 변수 및 메서드를 자식 클래스에서 상속받아 사용합니다.</li>
<li> 다형화 : 다양한 형태로 표현이 가능한 구조를 말합니다.</li>
<p>메시지에 의해 객체가 연산을 수행하게 될 때, 하나의 메시지에 대해 각 객체가 가지고 있는 고유한 방법으로 응답할 수 있는 방법이다.</p>
<p>다형화 지원 방법에는 오버로딩(Overloading)과 오버라이딩(Overriding)이 있습니다.</p>
</div>
</details>  

<details>
<summary>객체지향(oop)의 solid 라는 개념에 대해 설명해주세요.</summary>
<div markdown="1">

</div>
</details>   

<details>
<summary>추상 클래스와 인터페이스 차이에 대해서 설명해주세요.</summary>
<div markdown="1">

</div>
</details>    

<details>
<summary>접근제어자에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>접근 제어자는 클래스, 멤버변수, 메서드, 생성자 등에 대한 접근을 제한하는 역할을 합니다.</p>
<p>접근 제어자는 public, protected, default, private가 있습니다.</p>
<p>private는 해당 클래스에서만 접근이 가능하고, default는 해당 패키지까지, protected는 상속한 클래스까지 접근이 가능합니다.</p>
<p>public는 전체 영역에서 접근이 가능합니다.</p>
</div>
</details>     
 
<br>

## Spring
<details>
<summary>DI란 무엇인지 설명해주시고 어떤 장단점이 있는지 설명해주세요.</summary>
<div markdown="1">

안녕

</div>
</details>

<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## 데이터베이스
<details>
<summary>정규화란 무엇이고 대표적인 장점과 단점은 무엇이 있을까요?</summary>
<div markdown="1">

<p>정규화는 일정한 규칙에 따라 테이블 간에 중복된 데이터를 허용하지 않는 것입니다.</p>
<p>DB를 정규화함으로써 데이터의 중복을 막을 수 있습니다.</p>
<p>데이터의 일관성과  DB의 저장 용량 또한 줄일 수 있는 효율성 및 확장성을 보장할 수 있습니다.</p>
<p>하지만 정규화를 하면 테이블 분해로 인해 많은 조인 연산이 발생하므로 응답 시간이 느려집니다.</p>

</div>
</details>
 
<details>
<summary>모든 요소에 인덱스를 걸지 않는 이유에 대해 설명해주세요.</summary>
<div markdown="1">
<p>모든 요소에 인덱스를 걸면 데이터를 찾을 때는 빠를 수 있습니다.</p>
<p>하지만 다양한 단점이 있습니다.</p>
<p>데이터가 변경될 때마다 이 데이터를 갱신해야 합니다.</p>
<p>인덱싱 데이터도 별도로 관리해야 하므로 물리적 저장소와 메모리 사용량이 급증하게 됩니다.</p>
<p>특히 CRUD의 요소 중 R찾기를 제외하고 나머지 요소들의 성능이 극단적으로 저하됩니다.</p>  
</div>
</details> 
 
 
<details>
<summary>이상현상에 대해 설명해주세요.</summary>
<div markdown="1">


</div>
</details> 
 
<details>
<summary>DB를 사용하는 이유를 간단하게 설명해주세요.</summary>
<div markdown="1">


</div>
</details>
 
<details>
<summary>SQL, NoSQL 차이에 대해 설명해 주세요.</summary>
<div markdown="1">


</div>
</details>   
 
<details>
<summary>Redis, Memcached 의 차이에 대해 설명해주세요.</summary>
<div markdown="1">


</div>
</details>   

<details>
<summary>Redis의 작동원리 및 프로젝트에서 어떻게 사용했는지 설명해주세요.</summary>
<div markdown="1">


</div>
</details>    
 
 
<br>

## JPA
<details>
<summary>JPA에 대해서 설명해 주세요.</summary>
<div markdown="1">
<p>JPA는 JAVA에서 ORM(Object-Relational Mapping) 기술 표준으로 사용되는 인터페이스입니다.</p>
<p>실제적으로 구현된것이 아닌 구현된 클래스와 매핑을 해주기 위해 사용되는 프레임워크입니다.</p>
<p>JPA를 사용하지 않는다면 DB의 데이터 CRUD를 하나하나 쿼리를 작성해서 코딩해야 합니다.</p>
<p>JPA를 사용함으로 각각의 해당 CRUD에 맞는 쿼리를 다시 작성할 필요가 없어 필드가 추가되거나 수정할 때 유지 보수와 생산성을 높일 수 있습니다.</p>
</div>
</details>
 
<details>
<summary>JPA는 언제 필요하고 언제 필요하지 않은지 설명해주실 수 있을까요?</summary>
<div markdown="1">

JPA를 사용하지 않는다면 DB의 데이터 CRUD를 하나하나 쿼리를 작성해서 코딩해야 합니다.
JPA를 사용함으로 각각의 해당 CRUD에 맞는 쿼리를 다시 작성할 필요가 없어 필드가 추가되거나 수정할 때 유지 보수와 생산성을 높일 수 있습니다.
하지만 데이터 통계처리나 복잡한 조회가 필요한 상황에는 JPA보다는 SQL을 사용하는 것이 적합합니다.
JPA는 만들 수는 있지만 쿼리문 자체가 복잡해지고 구현이 어려우며 만들었다 해도 오타율이 높기 때문에 위와 같은 상황에는 필요하지 않습니다.

</div>
</details> 

<details>
<summary>JPA의 더티 체킹이란 무엇인가요?</summary>
<div markdown="1">

안녕

</div>
</details> 

<details>
<summary>ORM에 대해서 설명해주세요.</summary>
<div markdown="1">

안녕

</div>
</details> 
 
<br>

## 운영체제
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## 네트워크
<details>
<summary> 브라우저에 google.com 을 치면 일어나는 일련의 일들을 설명해주세요. </summary>
<div markdown="1">

<p>처음에 www.google.com을 브라우저 주소창에 입력하면,</p>
<ui>
<li>우리가 쓰는 브라우저가 URL을 Parsing(주소 해석)해서 HTTP Request Message를 만들고 os에 전송 요청을 합니다. </li>
<p>이 때, 우리의 컴퓨터는 도메인 이름을 이해하지 못하기 떄문에 Domain으로 요청이 아닌 DNS를 통해 ip 주소를 찾습니다.</p>
<li>브라우저는 캐싱된 DNS 기록을 체크합니다.</li>
<p>요청한 URL이 캐시에 없으면, ISP(nternet Service Provider)의 DNS 서버에서 다른 DNS 서버를 DNS Query를 통해 검색하여 IP 주소를 찾습니다.</p>
<li>ip 주소를 찾으면 브라우저가 서버와 TCP connection을 한다.</li>
<p>TCP/IP three-way handshake라는 프로세스를 통해서 클라이언트와 서버간 connection이 이뤄지게 되는 것입니다.</p>
<li>이제 Browser가 웹서버에 HTTP 요청을 합니다.</li>
<li>서버는 가지고 있는 웹서버에서 브라우저로부터 온 요청을 읽고 response를 생성합니다.</li>
<li>서버는 요청받은 웹페이지, 상태코드, 쿠키 등이 포함되어 있는 HTTP Response를 보냅니다.</li>
<li>브라우저가 HTML content를 보여주면 www.google.com 웹페이지를 보여주는 것입니다.</li>

</div>
</details>

<br>

## 자료구조/알고리즘
<details>
<summary> 배열, 링크드리스트를 비교하여 설명해주실 수 있을까요? </summary>
<div markdown="1">
<p>모두 데이터를 나열하는 두 자료구조 배열과 링크드리스트는 3가지의 차이점을 설명할 수 있습니다.</p>
<ul>
<li>1. 크기의 차이가 있습니다.</li>
<p>배열은 선언할 때 크기를 고정하고, 링크드리스트는 데이터를 삽입할 때마다 크기를 증가 시킵니다.</p>
<li>2. 주소의 차이가 있습니다.</li>
<p>배열은 데이터에 주소를 들어온 순서별로 순차적으로 할당해주지만 링크드리스트는 주소를 랜덤으로 할당해줍니다.</p>
<p>배열은 순차적으로 할당한 만큼 인덱스만 안다면 접근이 가능해 속도가 빠릅니다. 그에 비해 링크드리스트는 주소가 랜덤이라 하나하나 위치를 따라가서 접근해야 하므로 속도가 느립니다.</p>
<li>3. 삽입, 삭제 방법 차이가 있습니다.</li>
<p>배열은 삽입 시, 기존의 데이터들의 위치를 뒤로 이동 시키고 삭제 시, 기존의 데이터들의 위치를 삭제 한만큼 앞으로 이동시킵니다.</p>
<p>링크드리스트는 삽입 시, 리스트에 연결되어 있는 위치에 접근한 후 리스트 추가, 삭제 시 리스트에 연결되어 있는 위치에 접근하여 삭제 후 기존의 리스트들을 연결합니다.</p>
</div>
</details>
 
<details>
<summary>스택, 큐에 대해 설명해주실 수 있을까요? 어떻게 사용할 수 있을까요? </summary>
<div markdown="1">
<p>스택은 (LIFO) Last in first out 형태로 데이터를 저장하는 구조입니다.</p>
<p>가장 마지막에 들어온 데이터가 가장 먼저 나가고 가장 먼저 들어온 데이터가 가장 마지막에 나가는 구조입니다.</p>
<p>스택 활용 예시로는  1. 웹 브라우저 뒤로 가기를 하면 가장 나중에 열린 페이지부터 뒤로 가기 실행이 되는 스택 구조 2. 문서 작업에서 ctrl + z</p>
<br/>
<p>큐는 (FIFO) First in first out 형태로 데이터를 저장하는 구조입니다.</p>
<p>줄을 서서 기다리는 것을 의미하며 선입선출로 가장 먼저 들어온 데이터가 나가고 가장 마지막에 들어온 데이터가 마지막에 나가는 구조입니다.</p>
<p>예를 들자면 마치 뚫려있는 프링글스 통에 맨 밑에 과자가 먼저 빠져나가는 것입니다.</p>
<p>큐 활용 예시로는 프린트 출력이 있는데 가장 먼저 인쇄를 눌러 대기열에 오른 프린트가 먼저 출력</p>
</div>
</details>

<details>
<summary>트리, 그래프를 비교하여 설명해주실 수 있을까요? </summary>
<div markdown="1">
<p>트리는 그래프의 한 종류인 비순환 그래프에 해당되는 자료구조입니다.</p> 
<p>최상단에 하나의 루트 노드를 가지고 있고, 루트 노드에서부터 반드시 1개의 경로만을 가지고 밑에 노드로 연결되는 구조입니다.</p>
<p>1개의 경로만으로 연결되기에 트리는 사이클이 존재하지 않는 방향 그래프입니다.</p>
<p>이처럼 1개의 부모 노드만을 가지는 트리를 계층 모델이라고 부릅니다.</p>
<p>트리의 대표적인 예시로는 컴퓨터의 Dirctory 구조가 있습니다.</p>
<br/>
<p>그래프는 노드와 엣지로 이루어진 자료 구조로 방향,순환에 따라 종류를 나눌 수 있습니다.</p>
<p>그래프는 루트 노드가 없고, 노드 사이에 2개 이상의 경로가 존재할 수 있어 네트워크 모델이라고 부릅니다.</p>
<p>루트나 부모-자식 개념이 없이 연결된 그래프의 예시로는 지하철 노선도가 있습니다.</p>
</div>
</details>
 
<details>
<summary>시간복잡도와 공간복잡도가 무엇인지 설명해 주실 수 있을까요?</summary>
<div markdown="1">
<p>시간복잡도는 알고리즘이 문제를 해결하는데 걸리는 시간을 의미합니다.</p>
<p>공간복잡도는 알고리즘이 문제를 해결하는데 얼마나 많은 공간 즉 메모리를 차지 하는 지를 의미합니다.</p>
<p>프로그램에는 데이터의 양을 효율적으로 처리할 알고리즘이 필요합니다.</p>
<p>효율적인 알고리즘을 평가할 때 복잡도라는 개념이 나온건데 복잡도가 낮을수록 좋은 알고리즘이라고 합니다.</p>
</div>
</details>



<br>

## 보안/암호
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## 기타
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

# 인성면접 
<details>
<summary>개발자가 되기로 한 이유에 대해서 말씀해주실 수 있니요?</summary>
<div markdown="1">

<P>IT업계에서 일했던 저는 다양한 포지션이 함께 작업하는 프로젝트에서 개발자들을 만났습니다.</P>
<P>'IT의 꽃은 개발자'라는 말을 자주 들었던 저는 개발자들을 만나고서야 그 말을 이해했습니다.</P>
<P>제가 일했던 IT 환경은 정해진 답만 존재했고 그 답만을 위해 수동적이게 움직여야했던 환경이었습니다.</P>
<P>하지만 개발자들은 그들이 짜는 코드에 정답은 없고 누구든지 창의적인 방법을 다양하게 구현할 수 있었습니다.</P>
<P>누구든지 목표를 가지고 공부한다면 자신만의 정답으로 코드를 구현할 수 있다는 그 환경에 매력을 느꼈습니다.</P>
<P>코로나때 진행되고 지금 잠시 멈춘 더 큰 디지털화에는 그런 창의적인 개발자들이 많이 필요할것이라 생각하고 있습니다.</P>
<P>저는 다가올 더 큰 디지털화를 구축할 개발자가 되고 싶어서 도전하게 되었습니다.</P>

</div>
</details>
 
<details>
<summary>최근에 개발공부를 하고있나요?</summary>
<div markdown="1">

안녕

</div>
</details> 
 
# 프로젝트
<details>
<summary>프로젝트에 대해 설명해 주세요</summary>
<div markdown="1">
<p>프로젝트 마운틴즈는 인증을 통해 등산을 추천해 주는 서비스입니다.</p>
<p>서비스 배포는 spring boot를 기반으로 CI/CD 환경으로 구성했습니다.</p>
<p>유저에게 각 산에 대한 정보를 제공해주고 카카오맵을 통해 산의 위치도 제공해줍니다.</p>
<p>유저가 해당 산의 위치에서 사진을 인증하면 인증포인트를 주어 뱃지를 주는 서비스도 제공하고 있습니다.</p>
<p>인증포인트를 통한 뱃지와 유저간의 랭킹 시스템같은 게임적인 요소를 제공하여 등산을 보다 즐겁게 이용할 수 있게 도와주는 서비스입니다.</p>
</div>
</details>
 
<details>
<summary>프로젝트에서 본인이 맡은 역할은 무엇인지 설명해 주세요.</summary>
<div markdown="1">

페이지별 설명/ 주요 기술들 설명 역할

</div>
</details>  

<details>
<summary>프로젝트 서비스 아키텍쳐 구성에 대해 설명해 주세요.</summary>
<div markdown="1">
<p>저희 프로젝트는 크게 domain 패키지와 grobal 패키지로 구성했습니다.</p>
<p>domain에는 view에서 보여지는 메인페이지, 상세페이지 등 각각의 페이지들로 구성되어 있습니다.</p>
<p>각 페이지 패키지 안에 페이지 기능을 구현하는데 필요한 controller, dto, service 파일이 구성되어 있습니다.</p>
<p>grobal에는 페이지 단위가 아닌 전역적으로 처리해야 할 예외처리나 보안에 필요한 security, jwt, 성능을 개선할 캐싱처리, querydsl로 구성되어 있습니다.</p>

<li>(추가)도메인 주도 개발(DDD) -커스텀해서 크게 도메인/글로벌로 나눴다.</li>
</div>
</details>   
 
<details>
<summary>QueryDSL을 사용하셨는데 어떤 상황에서 사용하셨나요?</summary>
<div markdown="1">

필터를 이용해 산을 검색하는 기능에 적용했습니다.
QueryDSL을 사용하면 동적으로 데이터 처리
문자열이 아닌 자바에 내장되어 있는 코드로  쿼리를 생성하여 더 쉽고 간결합니다.
형태도 SQL문과 비슷하여 가독성이 좋습니다.
왜 다른거로는 안썼죠?
기존에 JPA만을 가지고 구현을 하려했으나 
필터 기능이 복잡한 조건을 동적 처리하는 기능이다 보니
JPA로는 코드가 너무 길고 복잡해지는 문자가 생겼습니다.
문자열을 통해서 쿼리를 만들게 되면 작성한 문자열 쿼리 중 
띄어쓰기 혹은 알파벳의 오류가 있을 경우 이를 컴파일 타임에서 잡아주지 못한다.

</div>
</details>
 
<details>
<summary>Redis 캐싱처리를 하셨는데 어떤 상황에서 사용하셨나요?</summary>
<div markdown="1">

저희는 태그 조회할 때 Redis 캐싱처리를 적용했습니다.

저희가 미리 DB에 저장해 놓은 태그가 공통적이고 반복적으로 보여지게 될 정보입니다.

매번 DB에 접근하는 것을 redis라는 인메모리 방식의 캐시를 사용하면 

사용자의 처리 속도를 더 높여줄 수 있을것 같아서 적용했습니다.


Redis 원리
DB에 있는 정보를 가져오는 것이 아니라 인메모리 방식의 캐시에 있는 정보를 가져오는 것이다.
유저가 사용했던 정보들이 캐시에 들어있다.

캐싱 시간을 정해두고 그 시간 안에 사용했던 정보들을 금방 가져와서 쓰는 방식을 사용


</div>
</details>    

 <details>
<summary>프로젝트에서 사용자 정보 관리를 어떻게 했나요?</summary>
<div markdown="1">

사용자가 초기에 가입시 입력한 개인정보는 DB에서 관리하고 있습니다.
로그인시 해당 정보를 입력하면 JWT에서 엑세스 토큰을 주어 로그인을 허용합니다.
시간을 정해서 접근 시 리프레쉬 토큰을 주는 형태로 사용자를 관리했습니다.

</div>
</details>  
 
 <details>
<summary>CORS 오류를 어떻게 해결했나요?</summary>
<div markdown="1">

CORS는 교차출처 리소스 공유로 출처가 다른 자원들을 공유할 수 있도록 해주는 보안정책입니다.
예를 들어 프론트에서 실행 중인 웹이 백엔드의 자원에 접근할 수 있는 권한을 부여하도록 해주는 개념입니다.

저희도 처음 백과 프론트가 연결할 때 CORS 에러가 발생했습니다.
백8080 프론트3000 port가 다르니까 웹 브라우저 즉 크롬에서 서로 다른 port에서 접근을 하니까 막았던 것입니다.
백에서 

백이나 프론트 한쪽에서 해당 port를 허용해주고 에러가 해결됐습니다.
저희는 백에서 security를 이용해 cors를 허용해줬습니다.

</div>
</details>

<details>
<summary>프로젝트에서 기술 외적인 문제가 있었나요?</summary>
<div markdown="1">

프론트-디자이너 다툼 -> 백엔드가 해결 -> 일정조율/ 각자 포지션별 의견수렴 조율

</div>
</details>  
 
<details>
<summary>프로젝트 기술적 문제(트러블슈팅)가 있었나요?</summary>
<div markdown="1">

필터 기능을 구현하려 할때 기존에 JPA만을 가지고 구현을 하려했으나 복잡한 조건을 동적 처리하는 기능이다 보니
JPA로는 코드가 너무 길고 복잡해지는 문제가 생겼습니다.
<li>(추가) JPA란?<li>
<li>(추가) ORM란?<li>
<li>(추가) 더티 체킹?<li>

<br>

EC2(Ubuntu)에서 default 메모리 설정으로 무중단 배포를 적용하니 신버전 배포 시 서버가 다운

EC2 인스턴스에서 확인해보니 인스턴스 상태가 faile 이어서 EC2콘솔에서 인스턴스 로그를 보니 memory kill이 떴습니다.
1G가 넘는 spring boot 파일을 두개를 실행시키다 보니 default 메모리 설정이 감당하지 못해 서버가 다운됐습니다.
swap 메모리 설정을 해줘서 신버전 업데이트때도 서버가 다운되지 않게 해결했습니다.
<li>(추가) swap메모리?</li>
<li>ci/cd란? - 어떤 툴들을 사용하셨나요? / 왜 사용했나요? / 대안은 없었나요?</li>
<li>어떤 방식을 쓰셨나요? 왜 사용했나요?</li>


</div>
</details>   
 
<details>
<summary>프로젝트에서 성능을 개선한 경험이 있나요?</summary>
<div markdown="1">
태그 조회할 때 redis 성능 개선 수치 대략적으로 설명
<li>(추가) redis 원리/개념</li>
<li>(추가) redis, 맴캐시 차이 -> 왜 redis를 썼는지 위주로</li>
<li>(추가) 캐싱의 개념</li>

</div>
</details>

<details>
<summary>기타< 기술, 개선사항, 프로젝트 설명때 말한 기능(인증시스템, 랭킹 시스템)></summary>
<div markdown="1">
회원정보 관리 / JWT/Security

검색 기능

DB들 차이(RDB VS NOSQL)

-왜 RDB를 썼는지?
-NOSQL은 어떨때 쓸까요?
-MYSQL을 왜 썼는지? 다른 선택지? ->
-트랜잭션 개념
-REST full API란?
-에자일방식
- MSA 아키텍쳐
</div>
</details>
