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
<summary>토글 접기/펼치기</summary>
<div markdown="1">

</div>
</details>

<br>

## Spring
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## 데이터베이스
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## JPA
<details>
<summary>토글 접기/펼치기</summary>
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
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

<br>

## 자료구조/알고리즘
<details>
<summary> 배열, 링크드리스트를 비교하여 설명해주실 수 있을까요? </summary>
<div markdown="1">
모두 데이터를 나열하는 두 자료구조 배열과 링크드리스트는 3가지의 차이점을 설명할 수 있습니다
1. 크기의 차이가 있습니다.
- 배열은 선언할 때 크기를 고정하고, 링크드리스트는 데이터를 삽입할 때마다 크기를 증가 시킵니다.
2. 주소의 차이가 있습니다.
- 배열은 데이터에 주소를 들어온 순서별로 순차적으로 할당해주지만 링크드리스트는 주소를 랜덤으로 할당해줍니다.
- 배열은 순차적으로 할당한 만큼 인덱스만 안다면 접근이 가능해 속도가 빠릅니다. 그에 비해 링크드리스트는 주소가 랜덤이라 하나하나 위치를 따라가서 접근해야 하므로 속도가 느립니다.
3. 삽입, 삭제 방법 차이가 있습니다.
- 배열은 삽입 시, 기존의 데이터들의 위치를 뒤로 이동 시키고 삭제 시, 기존의 데이터들의 위치를 삭제 한만큼 앞으로 이동시킵니다.
- 링크드리스트는 삽입 시, 리스트에 연결되어 있는 위치에 접근한 후 리스트 추가, 삭제 시 리스트에 연결되어 있는 위치에 접근하여 삭제 후 기존의 리스트들을 연결합니다.

</div>
</details>
 
<details>
<summary>스택, 큐에 대해 설명해주실 수 있을까요? 어떻게 사용할 수 있을까요? </summary>
<div markdown="1">

스택은 (LIFO) Last in first out 형태로 데이터를 저장하는 구조입니다.
가장 마지막에 들어온 데이터가 가장 먼저 나가고 가장 먼저 들어온 데이터가 가장 마지막에 나가는 구조입니다.
큐는 (FIFO) First in first out 형태로 데이터를 저장하는 구조입니다.
줄을 서서 기다리는 것을 의미하며 선입선출로 가장 먼저 들어온 데이터가 나가고 가장 마지막에 들어온 데이터가 마지막에 나가는 구조입니다.
예를 들자면 마치 뚫려있는 프링글스 통에 맨 밑에 과자가 먼저 빠져나가는 것입니다.

</div>
</details>

<details>
<summary>트리, 그래프를 비교하여 설명해주실 수 있을까요? </summary>
<div markdown="1">

비선형 데이터 구조에 속하는 트리와 그래프를 비교할 때 일단, 트리는 그래프의 한 종류이므로 그래프를 먼저 설명해야 합니다.
그래프는 노드와 엣지로 이루어진 자료 구조로 방향,순환에 따라 종류를 나눌 수 있는데 그 중 비순환 그래프에 트리가 해당됩니다.

트리는 최상단에 하나의 루트 노드를 가지고 있지만, 그래프는 루트 노드가 없습니다.
루트 노드에서 양쪽으로 하나씩 연결되어 내려오는 구조인 트리는 노드 사이에 반드시 1개의 경로 만을 가지며 사이클이 존재하지 않는 방향 그래프입니다.
1개의 부모 노드만을 가지는 트리를 계층 모델로 부르고, 2개 이상의 경로가 가능한 노드들로 이루어진 그래프는 네트워크 모델이라고 부릅니다.

</div>
</details>
 
<details>
<summary>토글 접기/펼치기</summary>
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
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>

# 인성면접 관련질문
<details>
<summary>토글 접기/펼치기</summary>
<div markdown="1">

안녕

</div>
</details>
