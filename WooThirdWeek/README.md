## 우테코 프리코스 미션 3주차 - 로또(Lotto)

---

로또 게임 기능을 구현한다. 
사용자로부터 로또 구입 금액을 입력받은 후, 당첨 번호와 보너스 번호를 입력받는다.
사용자가 구매한 로또 당첨 번호를 비교하여 당첨 내역 및 수익률을 출력하고 게임을 종료한다.


### 입력 값
- 입력 값은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 활용한다.

1. **로또 구입 금액**
   - 구입 금액은 1,000원 단위로 입력 받는다.
   - 1,000원 단위로 나누어 떨어지지 않는 경우 예외 처리한다.
   - 예외 처리 시 `IllegalArgumentException`을 발생한다.
 

2. **당첨 번호**
   - 로또 범위의 숫자 범위는 1~45까지이다.
   - 중복되지 않는 6개의 숫자를 입력 받는다.
   - 번호는 쉼표(,)를 기준으로 구분한다.
   - 입력 값에 숫자 범위 외의 숫자 혹은 문자가 존재하는 경우, 6개의 숫자를 입력하지 않은 경우, 중복 값이 존재하는 경우 `IllegalArgumentException`를 발생하여 예외 처리한다.


3. **보너스 번호**
   - 보너스 번호의 숫자 범위는 당첨 번호와 동일하다.
   - 당첨 번호와 중복되지 않는 숫자를 입력 받는다.
   - 숫자 범위 외의 숫자 혹은 문자가 존재하는 경우, 1개의 숫자를 입력하지 않은 경우, 당첨 번호와 중복되는 값이 존재하는 경우 `IllegalArgumentException`를 발생하여 예외 처리한다.
     
 

    
### 출력 값 
1. **발행한 로또 수량 및 번호**
   - 발행한 로또 수량을 출력한다. (ex. 8개를 구매했습니다.)
   - 발행한 로또 번호를 오름차순으로 출력한다. (ex. [1, 21, 23, 41, 42, 43])


2. **당첨 내역**
    - 당첨 내역을 출력한다.
        - 3개 일치 (5,000원) - 1개
        - 4개 일치 (50,000원) - 0개
        - 5개 일치 (1,500,000원) - 0개
        - 5개 일치, 보너스 불 일치 (30,000,000원) - 0개
        - 6개 일치 (2,000,000,000원) - 0개
    

3. **수익률**
    - 수익률은 소수점 둘째 자리에서 반올림한다.
      - 총 수익률은 62.5%입니다.


4. **예외처리**
   - 로또구매 금액
     - 1,000으로 나누어 떨어지지 않는 경우: [ERROR] The unit of the purchase amount is not 1,000" 메시지를 출력한다.
   - 당첨 번호
     - 숫자 범위 외의 숫자 혹은 문자가 존재하는 경우: "[ERROR] An out-of-range number or character exists in the input value." 메시지를 출력한다.
     - 6개의 숫자를 입력하지 않은 경우: "[ERROR] The number of input values does not match 6." 메시지를 출력한다.
     - 중복 값이 존재하는 경우: "[ERROR] Duplicate number exists in input value." 메시지를 출력한다.
   - 보너스 번호
     - 숫자 범위 외의 숫자 혹은 문자가 존재하는 경우: "[ERROR] An out-of-range number or character exists in the input value." 메시지를 출력한다.
     - 1개의 숫자를 입력하지 않은 경우: "[ERROR] The number of input values does not match 1." 메시지를 출력한다.
     - 당첨 번호와 중복된 숫자를 입력한 경우: "[ERROR] The input value contains a number that overlaps the winning number." 메시지를 출력한다.