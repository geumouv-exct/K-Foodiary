# K-Foodendar / K-Foodiary

Mac에서 바로 실행 가능한 정적 웹 앱입니다.

## 실행 방법

1. `K-food` 폴더를 압축 해제합니다.
2. `index.html`을 더블클릭하면 브라우저에서 실행됩니다.
3. 실제 Google 로그인을 사용하려면 `config.js`에 Google OAuth Client ID를 넣고 GitHub Pages, Netlify, Vercel 같은 HTTPS 배포 환경에서 실행하세요.

## Google 로그인 설정

`config.js` 파일에서 아래 값을 입력합니다.

```js
window.KFOOD_CONFIG = {
  GOOGLE_CLIENT_ID: "YOUR_GOOGLE_CLIENT_ID",
  GOOGLE_MAPS_API_KEY: ""
};
```

Google Cloud Console에서 OAuth 2.0 Client ID를 만들 때 앱을 배포할 주소를 Authorized JavaScript origins에 등록해야 합니다.
로컬 Mac 미리보기에서는 Client ID가 비어 있을 때 `Local preview login`으로 기능을 테스트할 수 있습니다.

## 이번 수정사항3 반영 내용

- 로그인하지 않으면 Calendar, Add, Book, Stamps 기능을 사용할 수 없도록 잠금 화면 추가
- 왼쪽 상단 메뉴에서 로그인/로그아웃 가능
- Google Identity Services 기반 Google 로그인 연동 코드 추가
- 로그인 후 왼쪽 상단 메뉴에서 사용자 이름, 이메일, 프로필 사진 확인 가능
- Stamps / Challenge 완료 시 K-food 아이콘을 획득하고 프로필 아이콘으로 설정 가능
- 프로필 사진 클릭 시 획득한 아이콘 선택 화면 표시
- Book 카드에서 사진과 K-food 이름이 겹치지 않도록 이름 영역 간격 조정

## 파일 구성

- `index.html` : 앱 진입 파일
- `styles.css` : 전체 UI 스타일
- `app.js` : 캘린더, 추가, 도감, 스탬프, 로그인 기능
- `config.js` : Google 로그인 / Google Maps 키 설정
- `assets/reference/` : UI 레퍼런스 이미지
