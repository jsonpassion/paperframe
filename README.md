# AI Paper Review Thumbnail Generator

논문 리뷰 아티클/유튜브용 썸네일을 즉시 생성하는 로컬 웹 앱.  
외부 서버, 설치, 인터넷 연결 **불필요** — `index.html` 파일 하나로 동작합니다.

---

## 빠른 시작

```bash
# 그냥 브라우저에서 열기
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

또는 로컬 서버로 실행 (권장):

```bash
# Python 3
python3 -m http.server 8080
# 브라우저에서 → http://localhost:8080

# Node.js (npx)
npx serve .
# 브라우저에서 → http://localhost:3000
```

---

## 기능

| 기능 | 설명 |
|---|---|
| **픽셀 아트 13종** | MLP, Transformer, Robot, Brain, GPU, Vision Eye, GNN, DNA/Sequence, Tokens/LLM, Diffusion, RL Agent, CNN, VAE |
| **색상 테마 16종** | Classic Blue, Deep Teal, Royal Purple, Volcanic, Midnight Slate, Deep Forest, Amber Dusk, Deep Indigo, Cyberpunk, Arctic, Crimson, Tactical Olive, Rose Gold, Ocean Depth, Synthwave, Matcha |
| **BG 코드 타입 5종** | x86 Assembly, Python/PyTorch, Hex Dump, CUDA/C++, Math Notation |
| **레이아웃** | 윈도우 위치 (좌/우/중앙), 픽셀 사이즈, BG 농도 |
| **Export** | PNG 1200×630 (OG Image / YouTube 썸네일 규격) |
| **Randomize** | 배경 코드 패턴 랜덤 재생성 |
| **Config JSON** | 설정을 JSON으로 복사 → 재현 가능 |

---

## 출력 해상도

- **1200 × 630 px** — Open Graph Image (블로그, SNS) 표준 규격
- YouTube 썸네일, Velog 대표 이미지, GitHub README에도 적합

---

## 커스터마이징 팁

### 새 픽셀 아트 추가

`index.html` 하단 스크립트에서 `ARTS` 배열에 추가:

```javascript
function artMyTopic(ctx, x, y, w, h, t) {
  // t.bg, t.bg2, t.win, t.text, t.accent, t.dark 사용
  ctx.fillStyle = t.accent;
  ctx.fillRect(x, y, w, h);
  // ...
}

// ARTS 배열에 추가
const ARTS = [
  // ...기존 항목들...
  { id: 'mytopic', name: 'My Topic', fn: artMyTopic },
];
```

### 새 색상 테마 추가

```javascript
const THEMES = [
  // ...기존 테마들...
  {
    id: 'custom', name: 'Custom Theme',
    bg: '#1a1a2e',   // 배경 메인
    bg2: '#16213e',  // 배경 어두운
    win: '#0f3460',  // 윈도우/카드
    text: '#ffffff', // 텍스트
    accent: '#e94560', // 강조색
    dark: '#0a0a15', // 가장 어두운
  },
];
```

### 설정 재현 (Config JSON 활용)

"⎘ Copy Config JSON" 버튼으로 복사한 JSON을 `index.html` 상단 `<script>`에 붙여넣어 기본값으로 설정 가능:

```javascript
const ST = { theme: 2, art: 3, bgSeed: 483920 };
```

---

## 파일 구조

```
thumbnail-gen/
├── index.html    ← 모든 코드 포함 (단일 파일)
└── README.md
```

외부 의존성 없음. CDN, npm 패키지 전혀 사용하지 않습니다.

---

## 라이선스

MIT — 자유롭게 수정/배포 가능합니다.
