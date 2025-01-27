# Spring_mvc2
스프링 MVC2강의 기록 저장소

# 검증
컨트롤러의 중요한 역할중 하나는 HTTP 요청이 정상인지 검증하는 것이다.

- 클라이언트 검증은 조작할 수 있어서 보안에 취약하다.
- 서버만으로 검증하면, 즉각적인 고객 사용성이 부족해진다.
- 둘을 적절히 섞어서 사용하되, 최종적으로 서버 검증은 필수다.
- API 방식을 사용하면 API 스펙을 잘 정의해서 검증 오류를 API응답 결과에 잘 남겨줘야 한다.
<hr>
<ul>
  <li>String형으로 List를 만들어서 model.addAttribute에 저장해서 다음 페이지로 이동할때 넘겨준다.</li>
  <li>BindingResult파라미터를 사용할 때는 @ModelAttribute로 등록된 파라미터 뒤에 와야한다.</li>
    <ul>
      <li>BindingResult에 검증 오류를 적용하는 3가지 방법</li>
      <ul>
        <li>@ModelAttribute의 객체에 타입 오류 등으로 바인딩이 실패하면 스프링이 FieldError생성해서 BindingResult에 넣어줌.</li>  
        <li>개발자가 직접 넣기</li>
        <li>Validator사용</li>
      </ul>
    </ul>
  <li>타입 요류로 바인딩이 실패하면 스프링은 FieldError를 생성하면서 사용자가 입력한 값을 넣어둔다. -> 그리고 해당 오류를 BindingResult에 담아서 컨트롤러 호출</li>
  <li>MessageCodesResolver</li>
  <ul>
    <li>검증 오류 코드로 메시지 코드들을 생성</li>
    <li>MessageCodesResolver인터페이스이고 DefaultMessageCodesResoolver는 기본 구현체다.</li>
    <li>ObjectError, FieldError와 함께 사용한다</li>
  </ul>
</ul>
       
