# [Workbook 6] Mapping Service

**※ Overview**

**이** **장에서는**  

- **기본적인 MAP의 기능을 살펴보고**
- **한** **데이터** **형식에서** **다른** **데이터** **형식으로** **매핑하는** **플로우** **서비스를** **생성합니다.**

---

**※ Content**

- **Map 구문은**
    - 값을 설정하는데 사용됩니다.
    - 파이프라인으로부터 변수를 drop하는데 사용됩니다.
    - 하나의 변수에서 다른 변수로 데이터를 연결하는데 사용됩니다.
    - 복사하는 동안 데이터를 변형하는데 사용됩니다.
    
    ---
    
- **암묵적 Mapping**
    - 디자이너는 하나의 flow내에 같은 이름, 데이터 타입이 적합한 변수들을 암묵적으로 연결하거나 매핑합니다.

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled.png)

---

- **조건적 Mapping**
    - Mapping 연결에 조건을 둘 수 있습니다.
    - Mapping 연결선을 클릭하고 Copy condition property를 설정 할  수 있습니다.

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%201.png)

---

- **Set Value를 사용한 Mapping**
    - Integration Server 는 Set Value와 함께 변수를 대체할 수 있습니다:
        - “Perform Variable Substitution”체크하기
        - 파이프라인 변수를 %value%로 식별
        - Documents를 /root/subnode/key로 탐색(복사/붙여넣기 시도)
    
    ![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%202.png)
    

---

- **내용이 많은 Document Mapping**
    - 양쪽 스크롤링이 가능합니다:
        - Transformers 은 확장된다면 , 싱글 스크롤링 모드는 Transformer가 collapse 될 때까지 사용됩니다.

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%203.png)

---

- **Transformers**
    - Transformers는 Map 작업 내에서 발생하는 서비스 입니다.
    - Transformers는
        - 독립적으로 실행됩니다.
        - 종속 할 수 없습니다.
        - 파이프라인 변수를 암묵적으로 매핑하지 않습니다.
        - 출력값이 파이프라인에 자동으로 추가되지 않습니다.
        - 가장 효과적인 매핑 방법이 될 수 있습니다(전체 파이프라인을 복사하고 전달 할 수 있습니다.)

---

- **Mapping Indices**
    - 배열의 개별 요소를 매핑할 수 있습니다. 이렇게 하려면, Indices property를 편집하고 입/출력값 변수를 설정합니다.
    - 그러면 새로운 동작을 보여주기 위해 선이 파란색으로 바뀝니다.

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%204.png)

---

- **WmPublic Package Transformer 함수**
    - WmPublic 패키지는 많은 유용한 Transformer 서비스를 포함합니다.
    - [pub.date](http://pub.date) 폴더의 예: 문자열 필드에 현재 날짜를 삽입하는 방법
    
    ![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%205.png)
    

---

- **대부분이 실수하는 Mapping Error**
    - 실수로 파이프라인 내에 있는 Value값을 덮어쓰지 않도록 합니다
    
    ![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%206.png)
    

---

- **입력값 & 출력값**
    - 항상 무엇인가는 선언한 출력값에 매핑되어야 합니다.
    - 항상 사용하지 않는 필드는 드랍처리 합니다.
    - 선언된 입력값은 첫 서비스 단계의 파이프라인에서 자동으로 나타납니다.
    - 선언된 출력값은 서비스의 마지막 단계에서 파이프라인에 자동으로 나타납니다. 필요한 경우에는 같은 이름의 변수를 선언 해야합니다.

**※ Steps**

1.  **PurchaseOrder.maps 폴더에서 orderRequestToCanonical라는 Flow Service를** **생성하세요.** 

1. **‘name’라는** **문자열** **변수를** **입력값으로 설정하세요.**
2. **출력값으로  ‘outputName’과 ’date’를 출력값으로 설정하세요**.

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/31ab12b3-131d-4d61-b5e4-0b8b66811844.png)

**2.서비스에 MAP을** **추가하세요.**

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%207.png)

**3.**  **MAP 단계에서** **Transformer에** **string:toUpper서비스를** **추가하세요 . 다음** **변수를** **Transformer로** **그리고 Transformer 에서pipeline out의 변수들로** **매핑하세요:**

1. **name을 Transformer의 inString으로** **매핑하세요.**
2. **Transformer의** **값을 outputName로** **매핑하세요.**

![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%208.png)

1. **MAP 단계에서 Transformer에** **date:getCurrentDateString 서비스를** **추가하여 현재 날짜가 지정한 패턴으로 출력 되도록 설정하세요.**
    1. **Transformer에서 MMMM dd, yyyy패턴으로** **설정하세요.**
    2. **Transformer의** **값을 date로** **매핑하세요.**
    
    ![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/98514b54-25bd-45e5-876a-0b79e7c9a500.png)
    
2. **서비스를** **저장하고 입력값을 넣어 실행 후 결과창을 확인하세요.
특히 현재 날짜 및 대문자로 바뀐 name값을 확인하십시오.**
    
    ![Untitled](%5BWorkbook%206%5D%20Mapping%20Service%20515462f4d3da435293d124ff1de7bb73/Untitled%209.png)
    

**※ Check Your Understanding**

1. Transformer와 일반 서비스 간의 차이는 무엇인가요?
2. 원하는 Transformer가 Transformer 드롭다운 목록에 없는 경우 어떻게 해야하나요?

개발자가이드 개념 내용 CONTENT항목으로 추가

도큐먼트 없는 관계로 STEP내용 간단하게 변경 (LOOP내용 삭제→질문 3번 삭제( “왜 ProductLineItems를 LOOP하여 처리해야 했나요? ProductLineItems에서 Items로 직접 매핑하지 않는 이유는 무엇인가요?”))