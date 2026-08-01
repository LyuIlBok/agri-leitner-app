# 단어학습앱 (AgriLeitner / leitner_app.html) 요약 정보

Gemini CLI가 만든 다수의 AI 협업 도구 파일을 정리하면서, 실제 앱과 관련된 정보만 보존해 둔 문서입니다.

## 앱 개요
- 파일: `index.html` (단일 HTML 파일, React 18 + Tailwind CSS + Babel, CDN으로 빌드 없이 구동)
- 주제: 라이트너 학습법 기반 농업/공학 전문용어(식물보호기사 등) 단어장 SaaS

## 백엔드
- Supabase 프로젝트 URL: `https://cfimyvvecsoqeicsjezo.supabase.co`
- Anon Key: 코드 내 하드코딩되어 있음 (공개되어도 안전한 anon key, RLS로 보호)
- DB 테이블:
  - `public.agri_profiles`: 요금제(Free/Pro), AI 생성 카운트 관리
  - `public.agri_cards`: 사용자별 플래시카드 저장
- Google OAuth 연동 (로그인) — Client ID/Secret은 이 저장소에는 없음. 과거 Gemini CLI 로컬 메모리(`.gemini/tmp/project/memory/MEMORY.md`, 이 폴더 밖에 위치)에 저장되어 있었다는 기록이 있으니, 실제 값이 어디에 있는지 확인 후 필요시 재발급(rotate) 권장.

## 로컬 실행
- `npx http-server -p 5000` 실행 → `http://localhost:5000/index.html` (구글 로그인은 file:// 프로토콜을 막기 때문에 로컬 서버 경유 필요)

## 참고 (저장소 분리 완료)
이 폴더는 **독립 저장소** `github.com/LyuIlBok/agri-leitner-app.git`로 분리 완료됐습니다(커밋 `chore: split word app into its own repository`). 쇼핑몰(`github.com/LyuIlBok/modern-korean-mall`, 폴더 `Desktop\word_app`)과는 **완전히 별개의 repo**입니다.

단, **Supabase 프로젝트(cfimyvvecsoqeicsjezo)는 몰과 공유**하며 회원(auth)이 통합돼 있습니다 — 이건 의도된 설계라 분리 대상이 아닙니다. `agri_profiles`/`agri_cards` 테이블은 단어앱 전용(`agri_` 접두사)입니다. 공유 DB 스키마 변경은 몰 리드(Cowork-Claude)와 `Desktop\word_app\AI_STATUS.md`를 통해 조율합니다.
