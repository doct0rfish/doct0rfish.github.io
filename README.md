# 태국 방콕 · 파타야 여행 사이트

2026년 10월 14일~21일 여행 계획을 담은 정적 웹사이트입니다.

## 반영된 내용
- 날짜별 여행 일정과 Thai Airways 왕복 항공편
- 맛집 후보 23곳: 대표 메뉴, 설명, 지역 필터, 지도·길찾기
- 맛집 사진 제외 및 더 커피 클럽·팁싸마이 제외
- 준비물 체크리스트와 브라우저 내 체크 상태 저장
- 마사지 일정·문구 전체 삭제, 메뉴 이름을 ‘식사 일정’으로 변경

## 파일 구성
- dist/index.html: 페이지 구조, 메뉴, 항공편, 숙소, 준비물
- dist/app.js: 날짜별 일정과 화면 전환, 방문 체크
- dist/restaurants-data.js: 맛집 23곳의 데이터
- dist/restaurants.js: 맛집 카드, 지역 필터, 지도·길찾기
- dist/packing.js: 준비물 체크 상태 저장
- dist/style.css: 데스크톱·모바일 스타일
- dist/*.jpg: 기존 이미지 자산 (맛집 카드에는 사진을 표시하지 않습니다)
- .openai/hosting.json: 기존 Sites 프로젝트 연결 및 dist 배포 설정
- .gitignore: 임시 작업 파일과 ZIP 제외

## 기존 Git 저장소에 업데이트
1. ZIP을 풉니다.
2. 기존 저장소 루트에 파일을 복사해 같은 경로의 파일을 덮어씁니다.
3. 아래 명령으로 변경 내용을 확인한 뒤 커밋하고 푸시합니다.

    git diff
    git add dist .openai/hosting.json .gitignore README.md
    git commit -m "Update Thailand trip website"
    git push

이 패키지에는 .git 폴더나 Git 인증 정보가 없습니다.
.openai 폴더는 숨김 폴더로 보일 수 있으니 복사할 때 포함해 주세요.

## 로컬 미리보기
별도 설치나 빌드 없이 정적 파일로 실행됩니다. Python이 설치되어 있다면:

    python -m http.server 8080 --directory dist

브라우저에서 http://localhost:8080 을 엽니다.

## 배포
정적 호스팅의 공개 디렉터리를 dist로 설정하세요.
.openai/hosting.json은 현재 여행 사이트에 연결된 설정입니다.
다른 서비스에 배포할 때는 해당 서비스의 배포 설정을 사용하세요.

방문·준비물 체크는 사용 중인 브라우저의 localStorage에 저장됩니다.
기기별 체크 상태는 이 소스 패키지에 포함되지 않습니다.