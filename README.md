# geo01

인구 변천을 살펴보는 두 가지 정적 웹 시뮬레이션입니다. 별도 패키지 설치나
빌드 없이 HTML 파일을 웹 서버에서 제공할 수 있습니다.

## 파일 구조

```text
geo01/
├── index.html                    # 시작 페이지: 두 시뮬레이션 선택
├── .nojekyll                     # GitHub Pages에서 Jekyll 처리 생략
├── population-sim/
│   └── index.html                # 조건과 그래프를 함께 보는 화면
├── population-simulation/
│   └── index.html                # 단계별 진행과 변화 기록 화면
└── README.md
```

시작 페이지는 상대 경로로 연결되어 GitHub Pages의 `/geo01/` 하위에서도
동작합니다. 시뮬레이션의 수치는 개념 이해를 위한 가상 모형이며 실제 통계가 아닙니다.

## GitHub Pages 배포

저장소의 **Settings → Pages → Build and deployment**에서 다음과 같이 설정합니다.

1. **Source**: `Deploy from a branch`
2. **Branch**: `main`, 폴더: `/ (root)`
3. **Save**를 누른 후 Pages 배포가 완료될 때까지 기다립니다.

배포 후 기본 주소는 <https://kkhj0727-blip.github.io/geo01/>입니다.
이후 `main`에 푸시하면 GitHub Pages가 변경 내용을 배포합니다.
저장소 설정 권한이 필요하며, 배포 결과는 저장소의 Actions 또는 Pages에서 확인합니다.

## 로컬 실행

기존 체크아웃에서 다음 명령을 실행합니다.

```sh
cd /workspace/geo01
python3 -m http.server 8000 --bind 127.0.0.1
```

브라우저에서 `http://127.0.0.1:8000/`을 열어 시작 페이지와 두 시뮬레이션을 확인합니다.
서버는 `Ctrl+C`로 종료합니다. 각 클라우드 작업은 격리된 환경이므로 별도 요청이
없으면 Git worktree를 만들 필요가 없습니다.

## 환경 점검 기록

2026년 10월 31일 클라우드 환경에서 GitHub 저장소 읽기 접근과 다음 도구의
사용 가능 여부를 확인했습니다. 버전 고정 요구사항은 아닙니다.

- Git 2.52.0
- Python 3.12.14
- Node.js 24.19.0, npm 11.9.0
