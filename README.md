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
<summary>>객체지향(oop)의 장단점에 대해서 설명해주세요.</summary>
<div markdown="1">

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

<details>
<summary>제네릭에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>어떤 값이 하나의 참조 자료형이 아닌 여러 참조 자료형을 사용할 수 있도록 프로그래밍하는 것을 제네릭 프로그래밍이라고 합니다.</p>
<p>클래스 내부에서 지정하는 것이 아닌 외부에서 사용자에 의해 지정되는 것을 의미합니다.</p>
<p>특정 타입을 미리 지정해주는 것이 아닌 필요에 의해 지정할 수 있도록 하는 일반 타입입니다.</p>
<p>저희가 대표적으로 썼던 것이 컨트롤러 클래스에 "<T>" 를 쓰면 타입을 필요에 의해 지정하는 것을 말합니다.</p>
</div>
</details>

<details>
<summary>Error, Exception 차이에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>Error는 실행 중 일어날 수 있는 치명적 오류를 말합니다.</p>
<p>컴파일 시점에 체크할 수 없고, 오류가 발생하면 프로그램은 비정상 종료되며 개발자가 예측 불가능한 UncheckedException에 속합니다.</p>
<p>반면, Exception은 Error보다 비교적 경미한 오류이며, 개발자가 구현한 로직에서 발생한 실수나 사용자의 영향에 의해 발생합니다.</p>
<p>Exception은 개발자가 예외처리 등으로 미리 예측하여 방지할 수 있습니다.</p>
</div>
</details>

<details>
<summary>String, StringBuilder, StringBuffer 에 대해서 설명해주세요.</summary>
<div markdown="1">

안녕

</div>
</details>

## Spring
<details>
<summary>DI란 무엇인지 설명해주시고 어떤 장단점이 있는지 설명해주세요.</summary>
<div markdown="1">
<p>DI는 클래스 간에 의존성을 클래스 외부에서 주입하는 것을 말합니다.</p>
<p>DI는 단일 적인 클래스 들 간에 결합이 되어있으면 변경 사항에 서로 영향을 많이 받는데 이런 문제점을 방지하기 위해 사용하는 개념입니다.</p>
<p>DI를 사용함으로 클래스 레벨에서는 의존관계가 고정되지 않도록 하고 런타임 시에 관계를 동적으로 주입하도록 해줍니다.</p>
</div>
</details>

<details>
<summary>Spring Bean에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>Spring Bean은 스프링 컨테이너에 의해 관리되는 자바 객체를 의미합니다.</p>
<p>우리가 new 연산자로 어떤 객체를 생성했을 때 그 객체가 빈이 되는 것은 아닙니다.</p>
<p>빈이 되는 객체는 ApplicationContext.getBean()으로 얻어질 수 있는 객체입니다.</p>
<p>즉, Spring에서의 빈은 ApplicationContext가 알고있는 객체, 즉 ApplicationContext가 만들어서 그 안에 담고있는 객체를 의미합니다.</p>
<p>Spring에서는 Spring Bean을 얻기 위해  ApplicationContext.getBean() 와 같은 메소드를 사용하여 Spring 에서 직접 자바 객체를 얻어서 사욯합니다.</p>
</div>
</details>

<details>
<summary>Spring Bean 생성과정에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>Spring Bean은 객체 생성 -> 의존 설정 -> 초기화 -> 사용 -> 소멸 순서의 라이프 사이클을 가집니다.</p>
<p>@Component 어노테이션이 있으면 스프링 빈으로 자동 등록됩니다.</p>
<p>또한, @Component를 포함하는 @Controller, @Service, @Repository 어노테이션도 스프링 빈으로 자동 등록됩니다.</p>
<p>생성자에 @Autowired가 있으면 스프링이 연관된 객체를 스프링 컨테이너에 찾아서 넣어줍니다.</p>
<p>이렇게 객체 의존관계를 외부에서 넣어주는 것을 의존성 주입(DI)라 합니다.</p>
</div>
</details>

<details>
<summary>DI 종류는 어떤것이 있고, 이들의 차이는 무엇인가요?</summary>
<div markdown="1">

안녕

</div>
</details>
 
<details>
<summary>Spring에서 의존성 주입을 하는 방법은 어떤게 있을까요?</summary>
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
<summary>정규화는 왜 중요할까요?</summary>
<div markdown="1">

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
<summary>RDB, NoSQL 차이에 대해 설명해 주세요.</summary>
<div markdown="1">

RDB

<p>관계형 데이터베이스 RDB는 주로 SQL을 이용해 데이터를 조회하고 관리합니다.</p>
<p>행과 열로 나타내는 2차원 데이터로 표현하여 테이블 사이의 상호관련성을 가진 집합으로 구성됩니다.</p>
<p>테이블 사이의 관계는 외래키를 이용해 나타냅니다.</p>
<p>RDB는 초기에 테이블 사이의 의존성, 데이터 타입 등이 설계되므로 실제 작업 환경에서 변경이 어렵습니다.</p>
<p>RDB는 복잡한 쿼리와 JOIN 연산이 가능하다.</p>
<p>RDB는 다양한 집계 및 통계를 분석하는 데이터의 무결성과 일관성이 중요한 트랜잭션 업무에 적합합니다.</p>


NOSQL

<p>관계형이 아닌 데이터 모델을 총칭합니다.</p>
<p>NOSQL은 초기에 테이블 사이에 명시된 제약이나 규칙이 없으며 다양한 방식으로 데이터를 표현합니다.</p>
<p>즉, 행과 열로만 나타내는 RDB와 달리 도큐먼트 형태, 그래프 형태, 키-값 형태 등 유연하게 표현할 수 있습니다.</p>
<p>NoSQL은 구조화된 쿼리 언어가 없는 경우도 많고, 일반적으로 Join이 없다.</p>
<p>NOSQL은 자주 변경되는 데이터를 저장하거나 다양한 유형의 데이터를 처리하는데 적합합니다.</p>
</div>
</details>   
 
<details>
<summary>Redis, Memcached 의 차이에 대해 설명해주세요.</summary>
<div markdown="1">
<p>Redis, Memcached는 둘다 In-Memory 형태의 NoSQL입니다.</p>
<p>Redis, Memcached의 차이를 비교하면 Redis가 더 많은 기능을 제공하므로 Redis의 추가적인 기능으로 설명할 수 있습니다.</p>
<p>Memcached가 별도의 데이터 타입 없이 문자열만 저장한다면, Redis는 String, Hash, List 등 다양한 자료 구조를 제공합니다.</p>
<p>Redis에서 다양한 데이터형의 도움을 받을 수 있는 반면, 동일한 기능을 Memcached로 하려면 앱에서 직접 개발해야 하는 경우가 발생합니다.</p>
<br>
<p>둘의 가장 큰 차이는 데이터를 저장할 수 있는지의 여부입니다.</p>
<p>Redis는 RDB 기반으로 데이터를 저장할 수 있는 기능이 있는 반면, Memcached는 들고 있는 데이터를 저장할 수 있는 기능이 없습니다.</p>
<p>Memcached는 캐시로서의 기능을 수핼할 수 밖에 없는 반면, Redis는 캐시로도 쓰일 수 있고, 데이터 저장소로도 쓰일 수 있습니다.</p>
<p>프로젝트에서 데이터를 RDB 기반으로 관리하고 있다면, Redis만 써야합니다.</p>
</div>
</details>   

<details>
<summary>Redis의 작동원리 및 프로젝트에서 어떻게 사용했는지 설명해주세요.</summary>
<div markdown="1">


</div>
</details>    

<details>
<summary>외래키의 개념에 대해서 설명해주세요.</summary>
<div markdown="1">


</div>
</details>

<details>
<summary>수직적 확장, 수평적 확장에 대해서 설명해주세요.</summary>
<div markdown="1">


</div>
</details>
 
<details>
<summary>트랜잭션에 대해서 설명해주세요(4대 특징 포함).</summary>
<div markdown="1">


</div>
</details> 
 
<details>
<summary>ERD를 구성할 때 중요한 점을 어떤걸까요?.</summary>
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
<p>더티 체킹이란 상태 변경 검사라는 의미로 트랜잭션 안에서 엔티티의 변경이 일어나면 변경 내용을 자동으로 DB에 반영하는 JPA의 특징입니다.</p>
</div>
</details> 

<details>
<summary>ORM에 대해서 설명해주세요.</summary>
<div markdown="1">

안녕

</div>
</details> 

<details>
<summary>트랜잭션에 대해서 설명해주세요.</summary>
<div markdown="1">

안녕

</div>
</details>
 
 <details>
<summary>FetchType에서 즉시로딩과 지연로딩에 대해서 설명해주세요.</summary>
<div markdown="1">

FetchType.LAZY

</div>
</details>

<details>
<summary>JPA 연관관계 매핑 @OneToMany @ManyToOne @OneToOne @ManyToOne에 대해서 설명해주세요.</summary>
<div markdown="1">

FetchType.LAZY

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

<details>
<summary>싱글 스레드와 멀티스레드에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>우리가 프로그램을 실행하는 상태를 프로세스라고 합니다.</p>
<p>스레드는 그 프로세스 내에서 실제로 작업을 수행하는 주체를 의미합니다.</p>
<p>프로세스에서 한 개의 작업만 한다면 싱글 스레드이고, 한 개 이상의 작업을 한다면 멀티 스레드라고 합니다.</p>
<p>예를 들면 크롬을 열어 게임만 다운로드 받고있으면 싱글 스레드입니다.</p>
<p>그러다 검색도 하고 영상도 본다면 멀티 스레드인 것입니다.</p>
</div>
</details>

<details>
<summary>HTTP와 HTTPS의 차이점에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>HTTP와 HTTPS의 차이점은 SSL 인증서입니다.</p>
<p>기존 HTTP는 서버에서 브라우저로 전송되는 정보가 암호화되지 않는 문제가 있습니다.</p>
<p>즉, 데이터가 중간에 쉽게 도난당할 수 있습니다.</p>
<p>HTTPS는 SSL 인증서를 통해 통신을 암호화해 HTTP의 보안 문제를 해결한 프로토콜입니다.</p>
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
<p>배열은 정적인 자료구조이므로 검색기능에는 유용하나 수정, 삭제가 많은 기능에는 적절하지 않습니다.</p>
<p>링큰드리스트는 동적인 자료구조이므로 검색 속도가 느려 검색기능에는 적절하지 않으나 수정,삭제 등 갱신을 해야하는 기능에는 유욯합니다.</p>
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

<details>
<summary>MSA 아키텍쳐에 대해서 설명해주세요.</summary>
<div markdown="1">

안녕

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
<summary>에자일방식에 대해 설명해주세요.</summary>
<div markdown="1">
<p>에자일방식이란</p>
<p>작업 계획을 짧은 단위로 세우고 시제품을 만들어 나가는 사이클을 반복함으로써 고객의 요구 변화에 유연하고도 신속하게 대응하는 개발 방법론을 말합니다.</p>
<br>
<p>에자일 방식의 반대는 전통적 개발 방법론인 워터폴 방식이 있습니다.</p>
<p>장기적 관점에서 계획을 정교하게 세우고 사전에 단계별로 정해놓은 기준을 충족하지 않으면 다음으로 넘어가지 않는 특징이 있다.</p>
<p>워터폴 방식은 엄격한 심사를 중시하다 보니 시간과 비용의 낭비가 증가하게 된다.</p>
<p>기술이 빠르게 변하고 유저의 needs도 빠르게 변하는 지금 워터풀 방식으로 하기엔 시대착오적이다.</p>
</div>
</details>

<details>
<summary> CI/CD에 대하여 설명해주세요.</summary>
<div markdown="1">
<li>CI는 지속적 통합이라는 뜻으로</li>
<p>개발을 진행하면서 여러 명이 하나의 프로젝트에 수정을 진행해도 지속적으로 통합되면서 관리할 수 있음을 의미합니다.</p>
<p>예를 들어 Github 프로젝트에 여러 명이 코드를 업데이트하면 github action 같은 ci툴이 수정 사항을 병합합니다.</p>
<p>병합하면서 코드에 문제가 있는지 테스트까지 해주는 부분이 CI과정입니다.</p>
<br>
<li>CD는 지속적 배포 혹은 제공으로 CI의 연장선입니다.</li>
<p>CI의 결과물을 배포하는 작업을 자동화하는 것입니다.</p>
<p>예를 들어 Github actions같은 CI툴로 병합,테스트가 완료되어 Codedepoly같은 배포툴로 이동하면 해당 파일을 서버로 보내 배포를 합니다.</p>
</div>
</details>

<details>
<summary>싱클톤 패턴에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>싱글톤 패턴은 단 하나의 인스턴스를 생성해 사용하는 디자인 패턴입니다.</p>
<p>즉, 생성자의 호출이 반복적으로 이루어져도 실제로 생성되는 객체는 최초 생성된 객체를 반환 해주는 것입니다.</p>
<p>인스턴스가 1개만 존재해야 한다는 것을 보장하고 싶은 경우와</p>
<p>동일한 인스턴스를 자주 생성해야 하는 경우에 주로 사용합니다.</p>
<p>이미 생성된 인스턴스를 활용함으로써 메모리 낭비를 방지할 수 있고 속도 측면에서도 장점이 있습니다.</p>
<p>또한 싱글톤으로 생성된 객체는 전역성을 띄기 때문에 다른 객체와 공유가 용이합니다.</p>
<p>하지만 만약 여러 클래스의 인스턴스에서 싱글톤 인스턴스의 데이터에 동시에 접근하게 된다면 동서성 문제가 생길 수 있습니다.</p>
</div>
</details>

<details>
<summary>싱클톤 패턴의 대표적인 예시에 대해서 설명해주세요.</summary>
<div markdown="1">
<p>싱글톤 패턴의 대표적인 예시는 Spring Bean 입니다.</p>
<p>스프링의 빈 등록 방식은 기본적으로 싱글톤 스코프이고, 스프링 컨테이너는 모든 빈들을 싱글톤으로 관리합니다.</p>
<p>스프링에서 bean 생성시 별다른 설정이 없으면 default로 싱글톤이 적용됩니다.</p>
<p>스프링은 컨테이너를 통해 직접 싱글톤 객체를 생성하고 관리하는데, </p>
<p>요청이 들어올 때마다 매번 객체를 생성하지 않고, 이미 만들어진 객체를 공유하기 때문에 효율적인 사용이 가능합니다.</p>
</div>
</details>

# 인성면접 
<details>
<summary>개발자가 되기로 한 이유에 대해서 말씀해주실 수 있니요?</summary>
<div markdown="1">

<p>개발자는 '이러면 더 좋을 텐데'라는 고민을 실현할 수 있는 직업입니다.</p>
<p>더 나은 것을 위한 고민을 정확한 논리 과정을 통해 구현하면 삶을 발전시킬 수 있습니다.</p>
<p>계속된 고민과 리팩토링을 통해 한 달 어쩌면 하루를 발전시킬 수 있는 이 직업은 저에게 너무 매력적입니다.</p>
<br>
<p>회사에서 일을 하는 것에 희열을 느끼고 재밌어하는 것은 쉽지 않다고 생각했습니다.</p>
<p>하지만 프로젝트를 하면서 협업을 통해 기획을 하고 어려운 문제들을 해결했을 때 희열과 즐거움은 그 생각을 바꿔놨습니다.</p>
<p>지금은 단순한 프로젝트였지만 다가올 현업에서 서비스를 발전시켰다는 희열이 이 직업을 기대하게 합니다.</p>
<p>개발자란 끊임없이 노력하고 성장하고, 실력이 무기고, 실력으로 인정받는 매력적인 직업인 것 같습니다.</p>
<p>현재 제가 공부하고 있는 자바로 어디까지 구현할 수 있는지 궁금한 저는 끊임없이 성장하는 개발자가 되고 싶습니다.</p>
</div>
</details>
 
<details>
<summary>최근에 개발공부를 하고있나요?</summary>
<div markdown="1">

<p>어떤 매개체</p>
<p>기획, </p>
<p>책보면서 저희가 했던 프로젝트랑 연계해서 공부하고 있다.</p>

</div>
</details> 
 
<details>
<summary>개발에 어떤 흥미가 있나요?</summary>
<div markdown="1">

<p>개발공부 내용</p>
<p>자바로 어디까지 할 수 있는지 궁금하다.</p>
<p>IOT도 생각해보고 true/false 값 줘서 만드는</p>

</div>
</details> 

<details>
<summary>성격의 장점과 단점에 대해 말해주세요.</summary>
<div markdown="1">

</div>
</details> 

<details>
<summary> 팀리더를 하셨는데, 하면서 어려우셨던 점과 어떻게 해결하셨는지 알려주세요.</summary>
<div markdown="1">

</div>
</details> 

<details>
<summary> 입사를 하게 된다면 있었으면 하는 문화와 없었으면 하는 문화가 있을까요?</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 만약에 입사를 하게 되신다면 저희 회사에게 이득이 될 만한 일이 있을까요?</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 억대 연봉을 받는 개발자의 강점은 무엇일까요?</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 개발을 할 때 중요하다고 생각하는 부분에 대해서 말씀해주세요.</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 개발자란 무엇이라고 생각하나요?</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 제일 자신있는 스택은 어떤 것인가요?</summary>
<div markdown="1">
<p>JAVA입니다.</p>
<p>최근까지 프로젝트에서 다뤘던 언어도 JAVA기반이고 JAVA 개발자가 되고 싶어 JAVA스터디도 진행했습니다.</p>
<p>스터디와 개인 공부를 했던 JAVA가 제일 자신있는 스택입니다.</p>
</div>
</details>  

<details>
<summary> 다양한 개발 포지션이 있는데 백엔드를 선택하게 된 이유가 있나요?</summary>
<div markdown="1">

</div>
</details>  

<details>
<summary> 본인이 생각하는 이상적인 개발 환경이 있나요?</summary>
<div markdown="1">

</div>
</details>  

<br> 
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
<summary>MYSQL(RDB)을 왜 사용하셨나요?</summary>
<div markdown="1">
<br>
<p>저희가 사용한 MYSQL은 RDB입니다.</p>
<p>저희 프로젝트 같은 경우 다양한 산들과 유저들의 인증 데이터가 중복이 배제되어야 하고 엔티티 간에 관계를 정의해야합니다.</p>
<p>또한 복잡한 조건을 주어 검색을 하는 기능들이 있기에 SQL을 사용해 데이터를 가져와 줄 RDB인 MYSQL을 사용했습니다.</p>
</div>
</details>
 
<details>
<summary>RDB중에서도 MYSQL을 사용한 이유가 있나요? 혹시 다른 선택지는 있나요? -</summary>
<div markdown="1">
<p>MYSQL은 일단 다른 RDB에 비해 빠르고 안정적이며 사용하기 쉽다.</p>
<p>고사양을 요구하지 않으며 무료입니다.</p>
<p>웹환경에 맞게 설계되어 있기 때문에 웹 서비스를 구현하는 저희 프로젝트에서는 MYSQL을 선택했습니다.</p>
<br>
<p>다른 RDB로는  Maria DB, MS-SQL 등이 있습니다.</p>
<p>일단 처음 RDB구현에 MYSQL을 사용한 이유는</p>
<p>가장 대중적인 DB이다 보니 많은 유저 경험과 레퍼런스가 있어 처음 구현과 오류 해결에 더 유리하다 판단되어 사용하게 되었습니다.</p>
<p>추후 RDB구현에 좀 더 미래 지향적인 RDB를 사용한다면 Maria DB도 사용해 보려고합니다.</p>
<p>Maria DB도 MySQL을 포크한 서비스라서 어떻게 보면 많은 유저 경험과 레퍼런스가 있습니다.</p>
<p>또한 오픈소스이기 떄문에 기업에 인수된 MySQL보다 정책적인 면에서 더 안정적이고 업데이트가 활발할거 같습니다.</p>
<br>
</div>
</details>
 
<details>
<summary>REST full API에 대한 개념과 프로젝트에 어떻게 적용하셨는지 설명해주세요.</summary>
<div markdown="1">
<p>REST란 자원을 이름으로 구분하여 해당 자원의 정보를 주고 받는 모든 것을 의미합니다.</p>
<p>즉,HTTP URI를 통해 자원을 명시하고, HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD를 적용하는 것을 의미합니다.<p>
<p>REST API 설계 규칙은 세가지 정도를 설명드릴 수 있습니다.<p>
<li>첫번째는 URI는 정보의 자원을 표현해야 합니다.</li>
<p>자원을 표현할 때는 동사보다는 명사를 사용해야하고 소문자를 사용해야합니다.</p>
<li>두번쨰는 자원에 대한 행위는 HTTP 메서드로 사용해야 합니다.</li>
<p>단, URI에 HTTP메서드가 들어가면 안됩니다.</p>
<li>세번째는 URI에 행위에 대한 동사 표현이 들어가면 안됩니다.</li>
<p>CRUD 기능을 나타내는 것은 URI에 사용하지 않습니다.</p>
<p>RESTful API의 목적은 성능 향상에 있는 것이 아니라 이해도 및 호환성을 높이는 것입니다.</p>
<p>RESTful하지 못한 경우라면 CRUD 기능을 모두 POST로만 처리하는 API가 있습니다.</p>
</div>
</details>

<details>
<summary>프로젝트에서 잘하지 못했다고 생각하는 부분이 있나요?</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>프로젝트에서 어떤 배포 방식을 사용했나요? </summary>
<div markdown="1">

</div>
</details>
 
<details>
<summary>Nginx는 왜 사용했나요? </summary>
<div markdown="1">

</div>
</details>

  
<details>
<summary>기타< 기술, 개선사항, 프로젝트 설명때 말한 기능(인증시스템, 랭킹 시스템)></summary>
<div markdown="1">
<li>회원정보 관리 / JWT/Security</li>
<li>검색 기능</li>
</div>
</details>
