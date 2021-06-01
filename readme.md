# String Calculator

## 기술스펙
### 0. 파일명과 구조
- 루트 폴더 아래에 stringCalculator.js를 생성한다.
- stringCalculator.js 는 add 메소드를 갖는 객체를 export 한다. `module.exports = { add }`
- 사용할때는 `const { add } = require('./stringCalculator');` 로 import 한다.

### 1. add 함수는 다음의 시그니처를 갖고 나열된 기능을 수행한다.
———————————————
int add(string numbers)
———————————————

- add 함수는 콤마로 구분된 두 숫자를 받고 그것들의 합을 반환한다.
  ex> “” or “1” or “1,2” as inputs.
- 빈 문자열인 경우 0을 반환한다.
- 구분된 숫자의 갯수 제한은 없다.(두개 이상의 숫자도 합할 수 있다.)

### 2. 콤마와 함께 뉴라인도 구분자로 사용할 수 있도록 한다.

- 다음 입력이 가능하다. : `"1\n2,3"` (리턴은 6)
- 다음 입력은 불가하다. : `"1,\n"` (테스트할 필요는 없음)

### 3. 추가로 커스텀 구분자를 지원한다.

- 다음과 같은 입력으로 다양한 구분자를 처리하도록 한다. :

```javascript
"//[delimiter]\n[numbers…]"
ex> "//[;]\n1;2"
=> 3
```

- 다양한 구분자 문법은 옵셔널이며 위의 요구사항들은 여전히 만족해야 한다.

### 4. 음수를 입력하면 "음수는 지원하지 않습니다.(-1,-2)" 라는 예외를 발생시킨다.

- 에러 메시지의 괄호안에는 모든 음수를 콤마로 구분한 문자열을 포함한다.

---

### 5. 1000보다 큰 숫자는 무시한다. (2 + 1001 = 2)


### 6. 여러 커스텀 구분자를 지원한다.

```javascript
"//[delim1][delim2]\n"
ex> "//[*][%]\n1*2%3*4"
=> 10
```