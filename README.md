# Bestuhl Addressbook

베스툴 임직원 주요연락처 웹앱 (PWA) — https://qogus00.github.io/bestuhl-addressbook/

- 연락처는 `data.enc.json`에 **암호화(AES-256-GCM, PBKDF2)** 되어 있으며, 접속 비밀번호를 입력해야 열립니다.
- 엑셀 원본은 이 저장소에 올리지 않습니다.

## 앱 설치
크롬(안드로이드/PC)으로 접속 → 화면의 **📲 앱 설치** 버튼 또는 주소창의 설치 아이콘.
아이폰은 Safari → 공유 → 홈 화면에 추가.

## 연락처 갱신 (관리자)
1. PC 크롬에서 `https://qogus00.github.io/bestuhl-addressbook/?admin` 접속 (한 번 열면 그 PC에 관리자 모드가 기억됨, `?admin=off`로 해제)
2. **⬆ DB 업로드** → 새 주요연락처 엑셀(.xlsx) 선택 (화면에 끌어다 놓아도 됨) → 변경 내용 확인 → **다음**
3. 접속 비밀번호 확인 후 **게시**
   - 깃허브 토큰을 넣으면 바로 게시됩니다 (최초 1회 입력, 그 PC에 저장).
     토큰 만들기: GitHub → Settings → Developer settings → Fine-grained tokens → 저장소 `bestuhl-addressbook`만 선택, Permissions → Contents: Read and write
   - 토큰 없이: `data.enc.json`이 내려받아지면, 열리는 업로드 화면에 끌어다 놓고 Commit changes
4. 1~2분 뒤 모든 사용자에게 반영됩니다.

비밀번호를 바꾸려면 3번에서 새 비밀번호로 게시하면 됩니다 (모든 기기에서 새로 입력 필요).

## 파일
| 파일 | 내용 |
|---|---|
| index.html | 앱 화면 · 엑셀 해석 · 암호화/복호화 |
| data.enc.json | 암호화된 연락처 DB |
| manifest.webmanifest, sw.js, icon-*.png | 앱 설치(PWA)·오프라인 지원 |
