# 문자열 덧셈 계산기

## 구현 기능 리스트
- [ ] 문자열 입력 기능
- [ ] 빈문자열 입력 시 에러메세지 출력 함수 작성
- [ ] 커스텀 구분자 검사 함수 작성
- [ ] 커스텀 구분자가 존재한다면 커스텀 구분자로 문자열 분리하는 함수 작성
- [ ] 커스텀 구분자가 존재하지 않는다면 디폴트 구분자로 분리하는 함수 작성
- [ ] 문자열 분리 후 잘못된 입력인 경우 에러처리 ex) 0~9 제외 모든 문자 존재 시 에러메세지 출력
- [ ] 분리된 문자열 덧셈 후 출력
- [ ] 예외상황 에러 함수 작성 ex) [ //*\n//-\n1,2,3 ], [ 1 ], [ *\n1,2,3 ]


### 기본동작

- , 와 : 을 구분자로 하여 숫자를 분리하고 해당 숫자를 덧셈하는 기능 구현
- ex) "1,2:3" -> 6

### 빈문자열 처리

- 입력이 **빈문자열** ""인 경우 결과 값을 0으로 처리하는 기능 구현
- ex) "" -> 0

### 커스텀 구분자 처리

- "//" 와 "\n" 사이에 위치한 **커스텀 구분자**가 포함 된 경우 해당 구분자로 숫자를 분리할 수 있도록 처리하는 기능 구현
- ex) "//;\n1;2;3" -> 6

### 예외 처리

- 사용자가 잘못된 값을 입력했을 경우 **Error**를 발생 시킨 후 종료되도록 처리하는 기능 구현
- ex) "1:k:3" -> [ERROR]
- ex) "1,-2:3" -> [ERROR]

## 기능 요구 사항

입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.

- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
  - 예: "" => 0, "1,2" => 3, "1,2,3" => 6, "1,2:3" => 6
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자를 커스텀 구분자로 사용한다.
  - 예를 들어 "//;\n1;2;3"과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 사용자가 잘못된 값을 입력할 경우 "[ERROR]"로 시작하는 메시지와 함께 Error를 발생시킨 후 애플리케이션은 종료되어야 한다.

## 입출력 요구 사항

**입력**

- 구분자와 양수로 구성된 문자열

**출력**

- 덧셈 결과

```
결과 : 6
```

**실행 결과 예시**

```
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

## 프로그래밍 요구 사항

- Node.js 20.17.0 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 App.js의 run()이다.
- package.json 파일은 변경할 수 없으며, 제공된 라이브러리와 스타일 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 process.exit()를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.
- 자바스크립트 코드 컨벤션을 지키면서 프로그래밍한다.
- 기본적으로 JavaScript Style Guide를 원칙으로 한다.

## 생각해볼 점

 - 커스텀 구분자와 디폴트 구분자가 동시에 존재하면 잘못된 입력인가? 아니면 디폴트 구분자로도 문자열 분리를 실행해야 하나?
 - -> 일단은 커스텀 구분자로만 분리 후 디폴트 구분자 존재 시 에러처리
 - 구분자로 분리 후 문자열 에러 검사를 할 지 아니면 분리 전 에러 검사를 할 지