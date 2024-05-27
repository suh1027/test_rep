# [Workbook 14] Create JDBC Adapter Services

**※ Overview**

이번 장에서는, insert 와 select JDBC Adapter services 를 생성할 수 있습니다. 상위 Flow service 와 결합할 수 있습니다. 이들을 함께 사용하면 database 의 데이터로 쉽게 작업할 수 있습니다.

---

**※ Steps**

1.  최상위 폴더 아래 IF0013를 생성한 후 그 아래 svc, adpt 폴더를 생성합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled.png)

2.  IS Server에서 Adapter Connection Alias를 생성합니다.

1. IS Server 에 설정한 사용자 이름과 비밀번호로 로그인 후  좌측 Adapters →webMethods Adapter for JDBC 클릭
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/15a2d6c8-9f90-49fd-b99b-960e2516f04b.png)
    
    b. webMethods Adapter for JDBC Connection클릭
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%201.png)
    

   c. DB접속 정보 입력 후 Test Connection 성공하면 Save Connection 클릭

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%202.png)

d. 생성 된 커넥션 확인 후 Enbled의 no를 yes로 변경

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%203.png)

e. Designer 해당 패키지 새로고침하여 생성 된 커넥션 확인 

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%204.png)

1. **adpt 아래 IF0013_ORA_I_01** 라는 새 Adapter Service 를 생성합니다. 
    
    a. Adapter Service Type으로 JDBC Adapter를 선택합니다.
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%205.png)
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%206.png)
    
    b. Adapter Service Type으로 JDBC Adapter를 선택합니다.
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%207.png)
    
    c.다음  Adapter Connection Alias 로 **CUDO_Conn.ORA:CUDO_SJH**를 선택합니다.
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%208.png)
    

d.마지막으로 InsertSQL을 template으로 선택하고 Finish을 클릭합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%209.png)

e. 생성된 JDBC Adapter Service insertOrderHeader를 다음과 같이 Configure(구성)합니다:

1.Table tab 에서, Table Name 컬럼의 첫 번째 행을 클릭하고 **CUDO_SJH.ORDER_HEADER을** 선택합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2010.png)

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2011.png)

        2.  **INSERT**tab 에서, 먼저 **Insert** 행 버튼을 한번 누릅니다**.**

       다음 **Fill in all rows to the Table** 버튼을 클릭 합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2012.png)

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2013.png)

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2014.png)

           3. **Result** tab 에서, **Result Field:** **insertCount** / **Result Field Type**: **java.lang.String** 설정합니다.   

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2015.png)

          4. Package Navigator view 에서 Adapter Service 인 IF0013_ORA_I_01를 저장하고 우클릭→Run As→ Run Service를 눌러 실행합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2016.png)

         5.**OverrideCredentials** 및**$connectionName** 을 제외한 모든 입력 필드에 데이터를 삽입합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2017.png)

            6. **insertCount** 가 ‘1’ 로 반환 되는지 확인홥니다.   

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2018.png)

1. 1단계에서와 마찬가지로,     **IF0009.adpt** 폴더에     **IF0009_ORA_I_02**  라는 또 다른 Adapter Service를 생성합니다. **CUDO_Conn.ORA:CUDO_SJH** 를 사용하는 **JDBC Adapter type** 의 **Adapter Service 를 지정하고 InsertSQL** template 을 선택합니다.   

2. 생성된 JDBC Adapter Service  **IF0009_ORA_I_02** 를 다음과 같이 구성합니다**:**   
    1. Table tab에서**, CUDO_SJH.ORDER_DETAILS**를 선택합니다.
    2. INSERT tab에서, Fill in all rows 버튼을 클릭합니다. 
    3. Result tab에서, Result Field:insertCount / Result Field Type: java.lang.String 설정하세요.
    
3.  **IF0009_ORA_I_02** service를 저장하고 실행합니다.
    
    OverrideCredentias 및 $connectionName 제외한 모든 입력 필드에 데이터를 삽입합니다.
    
     InsertCount 가 ‘1’로 반환 되는지 확인합니다.
    
4.    **IF0009.adpt** 폴더에 **IF0013_ORA_S_01** 라는 새로운 Adapter Service 를 생성하세요.  **JDBC Adapter type** 의 **Adapter Service** 로  **CUDO_Conn.ORA:CUDO_SJH** 를 사용하고**, SelectSQL** template 를 선택하세요.   

1. 생성된JDBC Adapter Service **IF0013_ORA_S_01** 를 다음과 같이 구성합니다:
    
    a. **Tables** tab 에서, in the first row 선택, **Table Name** 으로 **CODO_Conn.ORDER_HEADER** 을 선택 합니다.   
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2019.png)
    
    b. SELECT tab에서 , select ALL. Insert Row 버튼을 먼저 클릭하고 , 다음 Fill in all rows to the Table 버튼을 클릭하세요.
    
    ![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2020.png)
    

c. Input/Output tab에서, 생성된 Document type을 검토하세요. results Document List 아래에 선택한 데이터 베이스 컬럼이 있어야 합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2021.png)

1. **IF0013_ORA_S_01** service를 저장하고 실행하세요. 이 Adapter Service는 input을 제공할 필요가 없습니다. Database table이 이  **IF0013_ORA_I_01**  service로 insert했던 데이터로 채워졌는지 확인합니다.

![Untitled](%5BWorkbook%2014%5D%20Create%20JDBC%20Adapter%20Services%200b64172d40ae455893028de2efff8fe6/Untitled%2022.png)

1.  **IF0009.adpt** 폴더에 **IF0009_ORA_S_02**  라는 마지막 Adapter Service 를 생성하세요. **JDBC Adapter** type 의 **Adapter Service** 로 **CUDO_Conn.ORA:CUDO_SJH를** **사용하고, SelectSQL** template 를 선택하세요. 
2. 생성된JDBC Adapter Service  **IF0009_ORA_S_02** 를 다음과 같이 구성합니다:
    1. Table tab에서 **CUDO_SJH.ORDER_DETAILS**선택하세요.
    2. Select tab 에서, select ALL. Insert Row 버튼을 한번 클릭 후 , Fill in all rows to the Table 버튼을 클릭하세요..
    3. **Input/Output** tab 에서, 생성된Document type 을 검토하세요. results Document List 아래에 선택한 데이터베이스 컬럼을 확인 할 수 있습니다.
3.  **IF0009_ORA_S_02**  service를 저장하고 실행하세요. 데이터베이스 **IF0013_ORA_I_02**  service로 insert했던  데이터로 채워졌는지 확인하세요.

---

**※ Check Your Understanding**

1. Adapter service templates 을 사용하기 전에 어떤 administrative activity (활동)을 수행해야 합니까 ?