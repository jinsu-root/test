# 자료구조 (list)

struct list_head

```
struct 자료구조 {
    ...
    struct list_head * list;
}
```

# 생성
- 테스트
- LIST_HEAD(name) : name 변수를 <b>struct list_head</b> 로 선언 후 초기화
```
void main(void)
{
    LIST_HEAD(name);
    ...
}
```
- LIST_HEAD_INIT(name) : 이미 선언된 name 변수를 초기화<br>
<b>인자로 변수 이름인 name 을 전달하는 것에 주의</b>
변수로 변경시
    - 동해물
        - 백두산
```
void main(void)
{
    struct list_head head = LIST_HEAD_INIT(head);
    ...
}
```
구조체로 변경시
```
struct test_st
{
    struct list_head * head;
};
void main(void)
{
    struct test_st var =
    {
        .head = LIST_HEAD_INIT(var.head)
    };
    ...
}
```
- INIT_LIST_HEAD(&name) : <b>struct list_head * </b> name 변수를 초기화
```
void main(void)
{
    struct list_head head;
    INIT_LIST_HEAD(&head);
    ...
}
```

# 조회

    - list_for_each & list_entry
    ```
    struct list_head * it;
    struct 자료구조 * 변수;

    list_for_each(it, &헤드) {
        변수 = list_entry(it, struct 자료구조, list);
    }
    ```
    - list_for_each_entry
    - 추가
    - 제거
    - 자료구조 획득 (struct list_head 를 자료구조로 변환)




- 구조 / 특징
    - head (첫번째 node)는 data 를 가지는 구조체가 존재하지 않음을 가정
    - list_for_each / list_for_each_entry 로는 head (첫번째 node)의 구조체 접근 안함

<img src="list_head.png"/>

- struct list_head
- 함수들
    - 생성
    - 조회
    - 추가
    - 삭제
