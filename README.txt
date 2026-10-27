PROOF — Client Select & Delivery

실행
1. index.html을 브라우저에서 열거나 정적 호스팅(Vercel/GitHub Pages)에 올립니다.
2. 현재 데이터는 localStorage에 저장됩니다.
3. 고객 화면은 프로젝트의 "고객 화면" 버튼 또는 #client/{projectId} 경로로 접속합니다.

현재 구현
- 작가 대시보드
- 프로젝트 생성/삭제/상태 관리
- 사진 다중 업로드(로컬 Data URL)
- 고객용 PIN 접근
- 셀렉 장수 제한/선택/취소/완료
- 선택 파일명 복사/CSV 저장
- 보정본 연결 및 버전 숫자 증가
- 납품 완료 및 납품 목록 저장
- 활동 로그
- 스튜디오명/워터마크/기본 설정
- 모바일 대응

Supabase 연결 시 교체 지점
- localStorage -> database tables
- Data URL 사진 -> Storage signed URL
- client PIN 비교 -> server-side validation / edge function
- activity -> activity_logs table
- 작가 로그인 -> Supabase Auth
- 고객 링크 -> random share token + PIN
- ZIP 다운로드 -> server/edge generated archive

권장 테이블
projects
photos
selections
clients
activity_logs
settings
