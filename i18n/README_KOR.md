# Celeste

<img src="https://github.com/LeeYe-jin/Celeste/blob/develop/docs/static/img/Celeste_banner.png?raw=true" alt="Celeste Banner" width="100%" />

Celeste는 AI 기반의 동기부여 어시스턴트로, 디지털 웰니스와 습관 형성을 촉진하기 위해 매력적인 트윗과 반응을 제공합니다. Celeste를 통해 청중에게 실용적인 조언, 팁, 그리고 격려의 메시지를 전달하세요.

---

## 🚀 주요 기능

- **일일 트윗**: 동기부여 메시지를 자동으로 게시하며 스타일을 사용자 정의 가능.
- **상호작용**: 사용자 멘션에 응답하고 특정 계정과 상호작용.
- **개인화된 성격**: Celeste의 어조, 주제 및 스타일을 쉽게 조정 가능.
- **이모지 지원**: 이모지를 통해 메시지에 따뜻함과 개성을 추가.
- **타겟 응답**: 특정 사용자 계정이나 해시태그에 반응.

---

## 📂 프로젝트 구조

```
Celeste/
├── characters/
│   └── Celeste.character.json   # 주요 캐릭터 설정 파일
├── src/
│   ├── clients/                 # API 클라이언트 (예: 트위터 통합)
│   ├── config/                  # 일반 설정 파일
│   ├── database/                # 데이터 저장소
│   ├── index.ts                 # 애플리케이션 진입점
├── .env                         # 환경 변수 (API 키 등)
├── README.md                    # 프로젝트 문서
└── package.json                 # 종속성 관리
```

---

## 🛠️ 설정 방법

아래 단계를 따라 Celeste를 설정하세요:

### 1. 저장소 클론

```bash
git clone <repository_url>
cd eliza-starter-1
```

### 2. 종속성 설치

`pnpm`이 설치되어 있는지 확인한 후 실행:

```bash
pnpm install
```

### 3. 환경 변수 설정

프로젝트 루트 디렉토리에 `.env` 파일을 생성하고 아래 내용을 추가:

```plaintext
TWITTER_EMAIL=<트위터 이메일>
TWITTER_USERNAME=<트위터 사용자명>
TWITTER_PASSWORD=<트위터 비밀번호>
OPENAI_API_KEY=<OpenAI API 키>
```

### 4. 캐릭터 설정

`characters/` 폴더에 있는 `Celeste.character.json` 파일을 수정하여 Celeste의 성격, 주제 및 스타일을 사용자 정의하세요. 예시:

```json
{
  "name": "Celeste",
  "clients": ["twitter"],
  "modelProvider": "openai",
  "config": {
    "actionProcessing": true
  },
  "topics": ["디지털 웰니스", "마음챙김", "시간 관리"]
}
```

### 5. 애플리케이션 실행

다음 명령어로 Celeste를 실행하세요:

```bash
pnpm start --characters="/path/to/Celeste.character.json"
```

---

## ✍️ 커스터마이징

### 새로운 트윗 추가

새로운 트윗을 추가하려면 `Celeste.character.json`의 `postExamples` 섹션을 편집:

```json
"postExamples": [
  "🌟 오늘 하루를 감사로 시작하고 긍정적인 에너지를 만들어보세요!",
  "📚 잠시 쉬면서 영감을 주는 책을 읽어보세요!",
  "🧘‍♂️ 당신의 웰빙이 중요합니다. 숨을 깊이 들이쉬고 다시 시작하세요."
]
```

### 이모지 활용

Celeste의 개성을 강화하기 위해 트윗에 이모지를 추가하세요. 예:

```json
"postExamples": [
  "힘들 때는 작은 것부터 시작하세요. 단순함은 강력한 힘입니다! 🌟",
  "디지털 기기를 내려놓고 마음을 새롭게 해보세요. 🌿"
]
```

### 타겟 사용자 상호작용

`.env` 파일에 타겟 사용자를 추가:

```plaintext
TARGET_USERS=user1,user2,user3
```

---

## 🐛 문제 해결

### 이모지가 제대로 표시되지 않음

1. **인코딩 확인**: 문자 인코딩이 Unicode를 지원하는지 확인.
2. **트위터 API 로그 확인**: 메시지가 잘려서 전송되지 않았는지 확인.

### 애플리케이션이 시작되지 않음

- **에러**: `Unsupported engine: wanted {"node":">=22"}`
  - 해결: Node.js 버전을 22 이상으로 업데이트.

```bash
nvm install 22
nvm use 22
```

### 멘션에 응답하지 않음

1. `Celeste.character.json`에서 `actionProcessing`이 활성화되어 있는지 확인.
2. `.env`에서 API 키와 권한을 확인.

---

## 🌟 향후 개선 사항

- 멀티 플랫폼 지원 추가 (예: Slack, Discord).
- 트렌드 주제에 대한 동적 응답 구현.
- 실시간 상호작용을 위한 대화형 AI 개선.

---

## 👩‍💻 기여자

- [당신의 이름](https://github.com/yourusername)
- 기여를 환영합니다! Pull Request를 제출하거나 이슈를 만들어주세요.

---

## 📜 라이센스

이 프로젝트는 MIT 라이센스를 따릅니다. 자세한 내용은 LICENSE 파일을 확인하세요.

