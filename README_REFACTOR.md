# HIVEOIL 코드 분리본

원본 `index.html`의 동작을 유지하면서 유지보수용으로 파일을 분리했습니다.

## 구조

```
index.html                 # 공통 레이아웃, 패널 로더
assets/css/styles.css      # 기존 인라인 CSS 분리
assets/js/bootstrap.js     # 빌드 버전/전역 에러/초기 마이그레이션 코드
assets/js/app.js           # 기존 전체 JavaScript 로직
pages/*.html               # 기존 panel 단위 화면 분리
manifest.json, sw.js, icon # 기존 PWA 파일 유지
```

## 실행 주의

`pages/*.html`을 `fetch()`로 불러오도록 분리했기 때문에 파일을 더블클릭(`file://`)으로 열면 브라우저 보안 정책상 화면 로드가 막힐 수 있습니다. GitHub Pages에 올리거나 로컬 서버에서 확인하세요.

로컬 확인 예시:

```bash
python -m http.server 8000
```

그 후 `http://localhost:8000` 접속.

## 수정 포인트

- 화면 HTML 수정: `pages/` 폴더
- 디자인 수정: `assets/css/styles.css`
- 버튼/DB/Supabase 로직 수정: `assets/js/app.js`
