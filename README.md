<img width="150px" align="center" src="https://user-images.githubusercontent.com/122191856/230551371-0f89c64e-4ad9-4b8d-af3e-5543603cb931.png">

# [See other] 고전 영화 상영관 예매 서비스


> 본 프로젝트는 2023년 3월 위코드에서 진행항 2차 프로젝트입니다
<br><br><br>

# 📅 개발 기간 및 인원

- 개발 기간: 2023.03.27 ~ 2023.04.07 (2주)
- 개발 인원:
  - FrontEnd : 김수미(Product Manager), 이솜이(Project Manager), 오지수
  - BackEnd : 김승태, 강혁주
    <br><br><br>

# ❶ 배경

## 왜 처음 "CGV"를 참고하여 기획했나요?

<br>

- 사용자의 편의를 고려하여 유연한 영화 옵션 선택 기능
- 스크린리더를 고려한 시멘틱 마크업
- 사용자 친화적인 UI
  <br>

국내 영화관 중 굳건히 1위를 유지하는 CGV의 웹사이트를 보며, 소수의 사용자까지 고려한 고민의 흔적을 느낄 수 있었어요!<br>
폭 넓은 사용자가 모두 불편함 없이 이용 할 수 있는 서비스를 만드는 것에 가장 부합하다고 생각하여 참고하게 되었어요.
<br>

해당 사이트를 참고하여 만든 두번째 프로젝트, 영화 예매 서비스 See Other입니다:)

---

<br>

# ❷ 서비스 소개

## See Other, 어떤 서비스인가요?

- 지금은 상영하지 않는 고전 영화를 보다 쾌적한 환경에서, 몰입감 있게 볼 수 있는 영화관 예매 서비스예요.
- 30대 ~ 60대까지 고전영화가 보고싶은 모든 사용자에세 최적화된 예매 서비스예요.
- 사용자 친화적인 UI와 UX를 기반한 영화 예매 플랫폼이에요.
  <br><br>

## See Other, 어떤 기능이 있나요?

- 소셜 로그인, 회원가입
- 영화 리스트, 필터링, 캐러셀
- 영화 상세, 후기 작성, 페이지네이션
- 영화 예매, 좌석선택, 예매 내역 확인
- 스토어
  <br><br>

## 소셜 로그인, 회원가입
![05  로그인](https://user-images.githubusercontent.com/122191856/230551589-c0944ef4-ec07-46e1-b9ef-45cd17554fbe.GIF)
- 카카오 로그인을 통해 보다 쉽게 회원가입 및 로그인을 할 수 있어요.
- React 기반으로 로컬스토리지에 token을 저장하여 존재여부 확인 로그인/로그아웃기능을 사용할 수있도록 했어요.
- 사용자 닉네임과 연령대를 로컬스토리지에 저장하여 전역에서 사용할수 있도록 구현했어요.
  <br><br>

## 영화 리스트, 필터링
### 무비차트
![03  무비차트](https://user-images.githubusercontent.com/122191856/230551964-f31d3089-650e-4d07-b45a-3491f48a43ad.GIF)
### 메인
![01  메인](https://user-images.githubusercontent.com/122191856/230552032-f69ad038-66ae-434f-b067-14a6b65c5a26.GIF)

- 현재 상영 중인 영화와 상영 예정인 영화를 각각 확인 할 수 있어요.
- 각 탭에서 평점순, 예매율 순으로 정렬하여 확인 할 수 있어요.
- 현재 상영중인 영화의 예고편을 캐러셀로 확인 할 수 있어요.
- React의 useState에 불리언값을 저장하여 사용자가 광고 배너를 닫을 수 있는 기능 구현했어요.
- position:sticky를 사용하여 스크롤 내렸을때도 고정되도록 구현했어요.
- React를 이용하여 재사용 가능한 모달 컴포넌트 구현하고 Props 사용하여 부모컴포넌트로부터 전달받아<br>사용할수있도록 구현하여 유연하게 활용하고 다양한 상황에 맞게 컨텐츠와 버튼을 동적으로 변경가능도록 작업했어요.

<br><br>

## 영화 상세, 후기 작성
### 영화 상세, 리뷰
![나의 동영상 13](https://user-images.githubusercontent.com/122191856/230552088-0c84fd79-ab54-4c6a-8bf3-a7692de2d3f4.GIF)
### 페이지네이션
![나의 동영상 12](https://user-images.githubusercontent.com/122191856/230552162-86cea2f0-e33c-494d-8db4-54a938e5dae2.GIF)

- 백엔드에서 전달받은 movieId값과 무비 차트의 useState에 저장해놓은 movieId값을 비교하여,<br>상세 내용을 Modal로 띄워 주소 이동 없이 이용 할 수 있어요.
- 상세페이지에서 필요한 정보가있는 API를 화면에 렌더링했어요.
- useState에 리뷰를 저장하여, submit이벤트가 발생했을때 백엔드에게 movieId, 유저 토큰, 댓글내용 값을 넘겨주어<br>등록/수정/삭제/평균을 리뷰를 함께 등록 할 수 있어요.
- 로컬스토리지 토큰 유무를 확인하여 로그인(예매)한 사용자가 후기를 남길수 있도록 구현했어요.
- React 라이브러리인 react-paginate을 활용하여 등록된 후기를 3개씩 페이징하여 노출하고, 페이징이 10개가 넘을 경우<br>더보기 버튼 및 이전/다음 기능을 구현 등록된 후기를 모두 확인 할 수 있어요.
  <br><br>

## 영화 예매
![나의 동영상 20](https://user-images.githubusercontent.com/122191856/230552310-380d7bf0-d264-4876-bf94-1155f86cf44d.GIF)

- 예매자의 연령이 상영중인 영화의 상영등급에 부합되지 않는 경우 예매가 불가능하도록 했어요.
- 로그인 없이 예매 페이지로 이동 시, 로그인 페이지로 즉시 이동할 수 있는 Modal을 띄웠어요.
- 사용자의 동작에 따라 선택 가능한 옵션을 필터링하고, 선택된 옵션을 퀵메뉴에서 바로 확인 할 수 있도록 했어요.
- 색약/색맹인 사용자도 쉽게 좌석의 가격을 볼 수 있도록 좌석의 모양을 다르게 했어요.
- 사용자가 선택한 좌석의 총 가격을 합산하여 퀵메뉴에서 바로 결제가 가능하도록 구현했어요.
  <br><br>

## 예매 내역 확인

- 로그인한 사용자의 예매 내역 정보가있는 API를 화면에 렌더링하여, 예매 내역을 간소화 하여 바로 확인 할 수 있도록 편의성을 고려하였어요.
- Main 페이지에서 마이티켓 클릭시 영화 예매 내용을 API를 불러와 Modal로 띄워 확인할 수 있도록 했어요.

  <br><br>

## 스토어
![나의 동영상 15](https://user-images.githubusercontent.com/122191856/230552382-b829b017-bdc1-43ec-95d1-8d5a9810390c.GIF)

- 매출의 11%를 담당하는 스토어 페이지를 시멘틱한 마크업 및 접근성을 고려하여 마크업하여,<br>구매 가능한 제품을 확인 할 수 있도록 했어요.
  <br><br>

---

<br><br>

# ❸ 핵심기술

## See Other에서는 어떤 기술을 사용하였을까요?

> React와 Styled-component를 사용했어요!
> <br>

- className의 중복이나 오타로 인한 버그를 줄여주었어요.
- 스타일 컴포넌트를 활용하여 컴포넌트별로 독립적인 스타일을 정의하고, 필요한 CSS만 수정해서 사용할 수 있는 방식으로 구현했어요.

<br>

> 그 외에 다양한 라이브러리를 사용했어요!
> <br>

- slick, calender, pagnation을 사용하여 작업시간을 단축시킬 수 있었어요.

> 이미지 스프라이트 기법을 사용했어요!
> <br>

- 이미지 스프라이트 기법을 이용하여, 페이지 로딩속도를 향상시켰어요.<br><br>

---

<br><br>

# ❹ 회고

## See Other 프로젝트를 진행하면서 배운점이 있나요?

> React 라이브러리인 react-paginate을 활용해서 페이징 기능을 구현하는 방법을 배웠어요!
> <br>

- React를 사용한 프로젝트에서 페이징 기능을 구현하는 방법을 습득하였고, 라이브러리를 활용하여 효율적으로 개발하는 방법을 경험했어요.<br><br>

> 스타일 컴포넌트를 활용하여 컴포넌트별로 독립적인 스타일을 정의하고 CSS를 수정하는 방법을 배웠어요!
> <br>

- 컴포넌트의 스타일을 더욱 관리하기 쉽게 구현할 수 있었고, 코드의 가독성과 유지보수성을 향상시킬 수 있었어요.<br><br>

> 발표 및 기획의 전반적인 프로덕트를 담당하면서 프로젝트를 이끌어가는 경험을 했어요!
> <br>

- 팀 내에서의 건강한 토론과 협력을 통해 프로젝트를 원활하게 진행했어요.
- 팀원들의 의견을 적극적으로 수렴하여 좋은 결과물을 도출하는 방법을 익혔어요.
- 새로운 아이디어를 제시하고 실행에 옮기는것을 경험했어요.
<br><br>

## See Other 프로젝트를 진행하면서 부족한점이 있었있나요?

> 상세페이지에서 필요한 정보를 화면에 렌더링하는 부분에서 불필요한 렌더링이 발생하거나, 발생하지 않는 경우가 있었어요!
> <br>

- 상세페이지의 useState와 useEffect를 처음부터 하나씩 살펴보면서 차근차근 수정했어요.<br><br>

## See Other 프로젝트를 진행하면서 개선하고 싶은점이 있었있나요?
> 코드 리펙토링을 하고싶어요!
> <br>

- 코드의 가독성과 재사용성을 개선하고, 불필요한 코드 중복을 제거하여 유지보수를 편리하게 하고싶어요. <br><br>

## See Other 프로젝트를 진행하면서 느낀점이 있었있나요?
> 무엇보다도 개발하는 과정에서의 문제 해결 능력이 중요하다는 것을 깨달았어요!
> <br>

- 다양한 오류와 문제에 부딪혀 해결책을 찾고, 도전적인 상황에서도 포기하지 않고<br>해결하려는 노력을 통해 성장할 수 있는 기회를 얻었어요.





