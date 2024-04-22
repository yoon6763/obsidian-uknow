#자료구조


# 분리집합

분리집합이란 **서로소 집합**이라고도 불립니다.

이름에서도 알 수 있듯,

각각의 집합이 공통 원소를 가지지 않는 집합입니다.

즉 전체 집합 U에 두 개의 집합 A, B가 있을 때

**A ∩ B =** **Ø** 가 성립됩니다

이는 집합이 두 개가 아닌 세 개 이상이여도 마찬가지로, 각각의 집합이 공통원소를 가지지 않습니다.



# Union - Find

이러한 분리집합의 구현과 연산은 Union - Find로 이루어집니다.

말 그대로, Union(병합), Find(찾기) 인데요.

![](https://blog.kakaocdn.net/dn/ma3qS/btrQm8fyE0e/oUOQUqPmaaeHLgGzJ9K1dK/img.png)

두 개의 트리셋 A와 B가 있다고 합시다.

A와 B의 자식노드들은 모두 루트(최상위 노드)를 가리키고 있습니다.

그렇다면, 이 트리 두개를 병합하려면 어떻게 해야 할까요?

![](https://blog.kakaocdn.net/dn/b4Wtem/btrQljWtqNo/pWF5MQkumY7WC2ndiUnov1/img.png)

바로 B의 루트가 A의 루트를 가리키게 하면 됩니다.

각 트리셋의 **자식 노드가 루트(최상위 노드)를 찾는 과정이 Find**,

한 트리셋의 루트가 **다른 트리셋의 루트를 가르키게 하여 트리를 병합하는 과정이 Union** 입니다.


### 코드로 구현

먼저, n개의 원소가 있다고 가정했을때, 그들의 부모를 저장할 배열 parent가 필요합니다.

    int[] parent = new int[n];



#### find(x)

![](https://blog.kakaocdn.net/dn/kPK5M/btrQn9rNNeW/GYD8sPnF60KmWFtkKwO4W1/img.png)

find는 자식 노드에서 최상위 노드를 찾는 과정입니다.

x와 x의 부모가 같다면 x를 리턴,

그렇지 않다면 재귀적으로 find를 수행합니다.

    int find(int x) { 	if (x == parent[x]) return x; 	return parent[x] = find(parent[x]); }



#### union(x,y)

![](https://blog.kakaocdn.net/dn/b4Wtem/btrQljWtqNo/pWF5MQkumY7WC2ndiUnov1/img.png)

union은 트리를 병합하는 과정입니다.


    void union(int x, int y) { 	int nx = find(x); 	int ny = find(y); 	if (nx != ny) { 		parent[nx] = ny; 	} }



