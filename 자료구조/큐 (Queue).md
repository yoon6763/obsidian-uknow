#FIFO
#자료구조 

![](https://blog.kakaocdn.net/dn/ZgQy8/btsnujqBoNk/PxvJ4miUr3m1yAcdtViKa0/img.png)

반면에 Queue는 한쪽 끝에서만 삽입이 이루어지고, 반대쪽에서만 삭제가 일어나는 자료구조입니다.

FIFO (First - In, First - Out) 구조이지요.

넣는 과정을 Enqueue, 빼는 과정을 Dequeue라고 합니다.

![](https://blog.kakaocdn.net/dn/nBfvY/btsnrvx1MLS/ijprHxNwoo4gRWQlirLHKK/img.png)

이는 맛집에서 음식을 먹기 위해 웨이팅을 하는 것과 비슷합니다.

줄을 가장 처음 선 사람이 첫 번째로 들어가고,

두 번째로 선 사람이 두 번째로 들어갑니다.

새로 오는 사람은 줄의 맨 뒤 부터 기다려야 하죠



### 자바에서의 큐(Queue) 클래스

![](https://blog.kakaocdn.net/dn/Pxq16/btsnxV2FYOX/TqzZ3cfE4jI5GXdixTgBV1/img.png)

출력 : 3, 3, 1, 6

큐 역시 자바에서 지원하는 Queue 클래스가 있습니다.

offer를 통해 데이터를 삽입(Enqueue)하고,

peek을 통해 가장 처음에 삽입된 원소를 엿볼 수 있습니다.

poll을 통해 원소를 꺼낼 수 있죠 (Dequeue)



#### add vs offer

![](https://blog.kakaocdn.net/dn/b2LT2q/btsnvWnPCrZ/90iUH2UQDbFQPciuerDqG0/img.png)

큐에는 원소를 삽입하는데 add와 offer 두 메소드가 존재합니다.

이 둘의 차이는 무엇일까요?

![](https://blog.kakaocdn.net/dn/d5gsF7/btsnwRzIfJz/EvuUzl5vQIFHRcb58IqvW0/img.png)

큐의 내부 클래스를 파고 들어가 메소드를 찾아봤습니다.

아하! 컴퓨터의 리소스는 한정되어 있어 큐를 특정 크기 이상으로 넣는 것은 불가능합니다.

add는 더 이상 원소 삽입이 불가능할 경우, 에러를 뿜어내며 종료하고

offer는 더 이상 원소 삽입이 불거능할 경우, false를 반환한다고 하네요!

예외처리 등으로 값을 핸들링할 경우에는 add를,

false 등으로 값을 받고 싶다면 offer를 사용하면 될 것 같습니다.

#### remove vs poll

![](https://blog.kakaocdn.net/dn/cjybVZ/btsnvIcrap7/G28iNKgAcsP50VjOCLZuck/img.png)

remove와 poll의 경우도 마찬가지 입니다.

큐에서 원소를 꺼낼  때, remove의 경우 꺼낼 원소가 없다면 에러를 일으키지만,

poll의 경우 null을 반환하며 에러를 일으키지 않습니다.


### 변형 : 우선순위 큐

![](https://blog.kakaocdn.net/dn/dzUwcG/btsnukwixSe/CwGzRBXjw8dq0RkvLCXLZ1/img.png)

출력 : 2, 3, 5

큐의 종류 중 하나로 우선순위 큐가 있습니다.

큐에 들어간 원소에 특정 기준으로 우선순위를 매겨, 가장 우선순위가 높은 원소부터 꺼내는 방식인데요.

Integer 형으로 선언했지만, 클래스 내 멤버변수를 기준으로 설정할 수도 있습니다.

코딩테스트를 하다보면 굉장히 자주 쓰이는 녀석 중 하나입니다.