# 리스트List\_D2

## ArrayList

> 동적 가변 크기 기능이 내재되어 있는 배열과 비슷한 자료구조를 원할 때는 보통 ArrayList를 사용한다. ArraysList는 필요에 따라 크기를 변화시킬 수 있으면서도 O\(1\)의 접근 시간\(Access Time\)을 유지한다. 통상정으로 배열이 가득 차는 순간, 배열의 크기를 두 배로 늘린다. 크기를 두 배 늘리는 시간은 O\(n\)이지만, 자주 발생하는 일이 아니라서 상환 입력 시간\(amortized insertion time\)으로 계산했을 때 여전히 O\(1\)이 된다.
>
> #### 상환 입력 시간은 왜 O\(1\)이 되는가
>
> 크기가 N인 배열의 크기를 늘릴 때마다 얼마나 많은 원소를 복사해야 하는지 역으로 계산해 볼 수 있다. 배열의 크기를 K로 늘리면 그 전 배열의 크기는 K/2이었을 것이므로 K/2만큼의 원소를 복사해야 한다.
>
> | 첫 번째 | 1개의 원소 복사 |
> | :--- | :--- |
> | 두 번째 | 2개의 원소 복사 |
> | ....... |  |
> | 이전 | N/4 개의 원소 복사 |
> | 마지막 | N/2 개의 원소 복사 |
>
> N개의 원소를 삽입하기 위해서 복사해야 하는 원소의 총 개수는 1 + 2 + ...... + N/8 + N/4 + N/2 으로 N보다 작다.
>
> 따라서 N개의 원소를 삽입할 때 소요되는 작업은 O\(N\)이 된다.
>
> 배열의 상황에 따라 최악의 경우에 O\(N\)이 소요되는 삽입 연산도 존재하지만 평균적으로 각 삽입은 O\(1\)이 소요된다.
>
> ### 장점
>
> 데이터 참조가 쉽다
>
> ### 단점
>
> 데이터 삭제시 데이터의 이동\(복사\)가 많이 일어난다.
>
> 대량의 데이터 삭제시 내부적인 처리량이 늘어나 상당한 성능저하를 불러옴.

## LinkedList

> 연결리스트는 차례로 연결된 노드를 표현해주는 자료구조이다.
>
> 단방향 연결리스트에서 각 노드는 다음 노드를,
>
> 양방향 연결리스트에서 각 노드는 다음 노드와 이전 노드를 함께 가리키다.
>
> 배열과 달리 연결리스트에서는 특정 인덱스를 상수 시간에 접근할 수 없다.
>
> 리스트에서 K번째 원소를 찾고 싶다면 처음부터 K번 루프를 돌아야 한다.
>
> 장점은 리스트의 시작 지점에서 아이템을 추가하거나 삭제하는 연산을 상수 시간에 할 수 있다는 점이다.
>
> #### 정리
>
> **장점**
>
> 노드의 삽입, 삭제 작업이 용이하다.
>
> 기억공간이 연속적으로 놓여있지 않아도 저장이 가능하다.
>
> **단점**
>
> 접근 속도가 느리다 \(노드들이 포인터로 연결되어 있어 포인터를 찾아가는 시간이 필요하다.\)  
> 시간 복잡도 O\(N\)
>
> 연결 리스트 중에서 중간 노드의 연결이 끊어지면 그 다음 노드를 찾기 힘들다.
>
> 연결을 위한 링크\(포인터\) 부분이 필요하기 때문에 ArrayList나 배열에 비해 기억공간 이용 효율이 좋지 않다.

