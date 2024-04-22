#자료구조 
#FILO


![](https://blog.kakaocdn.net/dn/migaV/btsnxXlTyTE/TPW8IkwwNmkfElWnvwdNJK/img.png)


스택은 자료구조의 맨 위에서만 삽입과 삭제가 일어나는 자료구조 입니다.
포인터가 맨 위를 가르키고 있어, 데이터의 가장 위에서만 삽입과 삭제가 일어나지요.

가장 나중에 들어간 원소가 가장 빨리 나오는

LIFO(Last in - First out) 구조 입니다.

PUSH를 통해 원소를 삽입, POP을 통해 원소를 꺼냅니다.

![](https://blog.kakaocdn.net/dn/RY3MW/btsnwPWcgyq/6WW9sGsombMzJlvhY113N0/img.jpg)

이는 쌓아놓은 접시와 비슷합니다.

접시를 쌓을 때는 보통 가장 윗 접시부터 꺼내 쓰곤하죠?

컨트롤 + z를 눌러 뒤로가기를 하는 것도,

브라우저의 뒤로가기도 스택의 예시 중 하나입니다.


![](https://blog.kakaocdn.net/dn/cDQc7j/btsnwnZK4vq/C7C73NHLdz3kpukZOptD9K/img.png)

출력 : 10, 10,  5, 3

자바에서는 기본적으로 Stack 클래스를 지원합니다.

push를 통해 원소를  삽입하고, pop을 통해 원소를 꺼냅니다.

원소를 꺼내는 것이 아니라 맨 위에 있는 원소만 슬쩍 보고 싶다면 peek 메소드를 사용하면 됩니다.

사이즈를 알고 싶다면 stack.size()를,

비어있는지 확인하고 싶다면 stack.isEmpty()를 사용하면 됩니다.


## stack의 add vs push

stack에 원소를 넣는 방법은 두 가지가 있습니다.

![](https://blog.kakaocdn.net/dn/clY94r/btsnvEubwZ6/Q8vdqtsIzEYmk5hXzCFBv0/img.png)

바로 push와 add 인데요.

![](https://blog.kakaocdn.net/dn/bEg0YR/btsnygexrHX/GDL3chLD8VF7mwOpM0sCm0/img.png)

Stack은 Vector를 기반으로 구현되었는데,

Vector의 add 메소드가 밖으로 노출된 형태라 볼 수 있습니다.

add를 사용하여도 큰 문제는 없으나,

스택을 사용함을 보다 직관적으로 명시하기 위해 push 메소드를 사용할 것을 권장하고 있습니다.