# AI Presentation Builder — Figma 편집 가이드

> 이 파일은 AI Presentation Builder 발표자료를 Figma에서 수정하기 위한 인스트럭션 파일입니다.
> PPT를 Figma로 가져온 뒤 아래 가이드를 따라 편집하세요.

---

## 📐 슬라이드 기본 설정

| 항목 | 값 |
|------|-----|
| 슬라이드 크기 | 1280 × 720 px (16:9) |
| 총 슬라이드 수 | 7장 |
| 레이아웃 그리드 | 좌우 마진 48px / 컬럼 간격 24px |

---

## 🎨 컬러 시스템

Figma에서 **로컬 스타일(Local Styles)** 로 등록하여 사용하세요.

### 배경색

| 이름 | Hex | 용도 |
|------|-----|------|
| `bg/dark` | `#0F172A` | 타이틀·클로징 슬라이드 배경 |
| `bg/dark-secondary` | `#1E293B` | 헤더 바, 카드 배경(다크) |
| `bg/light` | `#F8FAFC` | 콘텐츠 슬라이드 배경 |
| `bg/card` | `#FFFFFF` | 라이트 슬라이드 카드 |

### 브랜드 컬러

| 이름 | Hex | 용도 |
|------|-----|------|
| `brand/primary` | `#6366F1` | 주요 강조, 버튼, 넘버링 |
| `brand/accent` | `#A78BFA` | 서브 강조, 副제목 |
| `brand/green` | `#10B981` | OUTPUT, 긍정적 지표 |
| `brand/amber` | `#F59E0B` | 현재 상황 카드 상단 |
| `brand/rose` | `#F43F5E` | 문제 항목 좌측 액센트 |

### 텍스트

| 이름 | Hex | 용도 |
|------|-----|------|
| `text/primary` | `#1E293B` | 본문 (라이트 배경) |
| `text/muted` | `#64748B` | 서브텍스트, 설명 |
| `text/white` | `#FFFFFF` | 다크 배경 위 텍스트 |

### 보조

| 이름 | Hex | 용도 |
|------|-----|------|
| `util/border` | `#E2E8F0` | 카드 테두리 |
| `util/highlight` | `#EEF2FF` | 인디고 배경 하이라이트 박스 |
| `util/card-dark` | `#334155` | 다크 슬라이드 내 구분선 |

---

## 🔤 타이포그래피 시스템

Figma **Text Styles** 로 등록하세요.

| 스타일 이름 | 폰트 | 크기 | 굵기 | 색상 |
|------------|------|------|------|------|
| `H1/slide-title` | Calibri | 60 px | Bold | `text/white` |
| `H2/section-num` | Calibri | 36 px | Bold | `brand/primary` |
| `H2/section-title` | Calibri | 28 px | Bold | `text/white` |
| `H3/card-title` | Calibri | 16 px | Bold | 상황에 따라 |
| `Body/default` | Calibri | 14 px | Regular | `text/primary` |
| `Body/muted` | Calibri | 13 px | Regular | `text/muted` |
| `Label/tag` | Calibri | 11 px | Bold | `text/white` |
| `Stat/large` | Calibri | 64 px | Bold | 색상별 브랜드 |

---

## 🗂 슬라이드별 편집 가이드

---

### Slide 1 — 타이틀

**레이어 구조**
```
[Slide 1 - Title]
  ├── bg-dark (Rectangle, fill: bg/dark)
  ├── left-accent-bar (Rectangle, w:16px, fill: brand/primary)
  ├── deco-circle-outer (Ellipse, fill: brand/primary 15%)
  ├── deco-circle-inner (Ellipse, fill: brand/accent 10%)
  ├── tag-bg (Rectangle, fill: brand/primary)
  ├── tag-text (Text: "AI SOLUTION")
  ├── title (Text: "AI Presentation Builder")
  ├── subtitle (Text: 부제목)
  └── footer-bar
        ├── bar-bg (Rectangle, fill: brand/primary 40%)
        └── footer-text (Text)
```

**수정 포인트**
- **서비스명 변경** → `title` 레이어 텍스트 직접 수정
- **태그 문구 변경** → `tag-text` 수정 후 `tag-bg` 너비를 텍스트에 맞게 조정
- **부제목 변경** → `subtitle` 레이어 수정
- **장식 원** → 크기·투명도 조정으로 무게감 제어 가능

---

### Slide 2 — 문제 정의

**레이어 구조**
```
[Slide 2 - Problem]
  ├── bg-light (Rectangle, fill: bg/light)
  ├── header-bar (Rectangle, fill: bg/dark)
  │     ├── num-text "01"
  │     └── section-title "문제 정의"
  ├── subtitle-text
  ├── card-situation (현재 상황 카드)
  │     ├── card-bg (Rectangle, fill: bg/card)
  │     ├── card-top-bar (Rectangle, h:4px, fill: brand/amber)
  │     ├── card-title "현재 상황"
  │     └── card-bullets (Text, bullet items)
  ├── issue-cards (문제 항목 4개, 반복 구조)
  │     └── [issue-card × 4]
  │           ├── card-bg (Rectangle, fill: bg/card)
  │           ├── left-accent (Rectangle, w:4px, fill: brand/rose)
  │           └── item-text
  └── conclusion-bar
        ├── bar-bg (Rectangle, fill: brand/primary)
        └── conclusion-text
```

**수정 포인트**
- **문제 항목 추가/삭제** → `issue-cards` 그룹 내 카드 복사·삭제 후 Y 좌표 재정렬 (간격: 44px)
- **현재 상황 내용** → `card-bullets` 텍스트 수정
- **결론 문구** → `conclusion-text` 수정

---

### Slide 3 — 해결 방향

**레이어 구조**
```
[Slide 3 - Solution Direction]
  ├── bg-light
  ├── header-bar
  ├── highlight-box (fill: util/highlight, stroke: #C7D2FE)
  │     └── highlight-text
  └── step-cards (프로세스 4단계)
        └── [step-card × 4]
              ├── card-bg
              ├── card-top-bar (h:4px, fill: brand/primary)
              ├── circle-bg (Ellipse, fill: util/highlight)
              ├── step-number (Text)
              ├── step-title (Text)
              └── step-desc (Text)
```

**수정 포인트**
- **단계 수 변경** → 카드 복사·삭제 후 X 좌표 재분배 (슬라이드 너비 1184px ÷ n)
- **단계 제목/설명 수정** → 각 카드의 `step-title`, `step-desc` 텍스트 수정
- **하이라이트 박스 문구** → `highlight-text` 수정

---

### Slide 4 — 서비스 개념 (플로우)

**레이어 구조**
```
[Slide 4 - Service Concept]
  ├── bg-dark
  ├── header-bar (fill: bg/dark-secondary)
  ├── flow-group
  │     ├── input-box
  │     │     ├── box-bg (stroke: brand/primary)
  │     │     ├── box-header (fill: brand/primary)
  │     │     ├── box-label "INPUT"
  │     │     ├── input-subtitle
  │     │     └── placeholder-lines (Rectangle × 6)
  │     ├── arrow-1 (Text "→")
  │     ├── ai-box
  │     │     ├── box-bg (stroke: brand/accent)
  │     │     ├── box-header (fill: brand/accent)
  │     │     ├── box-label "AI 분석"
  │     │     └── ai-items (Rectangle × 3)
  │     ├── arrow-2 (Text "→")
  │     └── output-box
  │           ├── box-bg (stroke: brand/green)
  │           ├── box-header (fill: brand/green)
  │           ├── box-label "OUTPUT"
  │           └── output-items (Rectangle × 2)
  └── bottom-note
```

**수정 포인트**
- **AI 분석 항목 추가** → `ai-items` 내 카드 복사, Y 좌표 조정 (간격: 52px)
- **OUTPUT 항목 추가** → `output-items` 내 카드 복사, Y 좌표 조정
- **박스 색상 변경** → 각 `box-bg`의 stroke 색상 및 `box-header`의 fill 색상 동시 변경

---

### Slide 5 — 주요 기능

**레이어 구조**
```
[Slide 5 - Key Features]
  ├── bg-light
  ├── header-bar
  └── feature-columns (3열 구조)
        └── [feature-col × 3]
              ├── col-bg (Rectangle, fill: bg/card)
              ├── col-header (fill: brand색 각각)
              ├── col-title (Text)
              └── feature-items
                    └── [feature-item × n]
                          ├── dot (Ellipse, fill: 브랜드색)
                          └── item-text (Text)
```

**수정 포인트**
- **기능 항목 추가** → `feature-items` 내 그룹 복사, Y 좌표 조정 (간격: 44px)
- **열 제목 변경** → `col-title` 텍스트 수정 + `col-header` 색상 변경
- **열 추가** → 컬럼 복사 후 전체 너비를 슬라이드에 맞게 재분배

---

### Slide 6 — 기대 효과

**레이어 구조**
```
[Slide 6 - Expected Effects]
  ├── bg-dark
  ├── header-bar
  └── effect-columns (3열 구조)
        └── [effect-col × 3]
              ├── col-bg (fill: bg/dark-secondary)
              ├── top-accent (h:4px, fill: 브랜드색)
              ├── stat-text (대형 수치, Text)
              ├── stat-label (Text)
              ├── divider (Rectangle, fill: util/card-dark)
              ├── effect-title (Text, Bold)
              └── effect-desc (Text, muted)
```

**수정 포인트**
- **수치 변경** → `stat-text` 텍스트 수정 (폰트 크기 64px 유지 권장)
- **레이블 변경** → `stat-label` 텍스트 수정
- **열 색상 변경** → `top-accent`의 fill 색상 변경 (브랜드 색 참조)

---

### Slide 7 — 클로징

**레이어 구조**
```
[Slide 7 - Closing]
  ├── bg-dark
  ├── deco-circle-left (Ellipse, fill: brand/primary 12%)
  ├── deco-circle-right (Ellipse, fill: brand/accent 10%)
  ├── main-copy (Text: 주요 카피라이트)
  ├── sub-copy (Text: 서브 문구)
  └── footer-bar
        ├── bar-bg (fill: brand/primary)
        └── footer-text
```

**수정 포인트**
- **메인 카피 변경** → `main-copy` 텍스트 수정
- **서브 카피 변경** → `sub-copy` 텍스트 수정

---

## 🧩 컴포넌트 권장 구조

Figma에서 아래 컴포넌트를 만들어두면 반복 작업이 줄어듭니다.

| 컴포넌트 이름 | 설명 | 사용 슬라이드 |
|--------------|------|--------------|
| `SlideHeader` | 번호 + 제목 헤더 바 | 2, 3, 4, 5, 6 |
| `IssueCard` | 좌측 액센트 + 텍스트 카드 | 2 |
| `StepCard` | 번호 원 + 제목 + 설명 카드 | 3 |
| `FlowBox` | INPUT/AI/OUTPUT 박스 | 4 |
| `FeatureColumn` | 기능 열 (헤더 + 아이템 목록) | 5 |
| `EffectColumn` | 대형 수치 + 설명 열 | 6 |

---

## ✅ 편집 체크리스트

편집 완료 후 다음을 확인하세요.

- [ ] 모든 텍스트가 슬라이드 경계 안에 있는가
- [ ] 카드 내 텍스트가 카드 박스를 넘지 않는가
- [ ] 브랜드 색상이 Color Styles에 등록되어 일관적으로 사용되고 있는가
- [ ] 헤더 바의 번호(`01`~`05`)가 순서에 맞게 수정되었는가
- [ ] 다크 슬라이드(1, 4, 6, 7)에서 텍스트 색상이 충분히 밝은가
- [ ] 라이트 슬라이드(2, 3, 5)에서 텍스트가 `text/primary` 또는 `text/muted`를 사용하고 있는가
- [ ] 수정 후 Export 시 1280×720px PDF 또는 PNG로 추출하였는가

---

## 📤 Figma Import 방법

1. PowerPoint 파일을 [Figma Importer 플러그인](https://www.figma.com/community/plugin/823537477024460284) 또는 **Figma → File → Import** 로 가져오기
2. 가져온 파일에서 각 슬라이드를 Frame으로 변환
3. 위 레이어 구조에 맞게 그룹 및 이름 재정리
4. 컬러·텍스트 스타일 등록 후 각 요소에 적용
5. 컴포넌트화하여 반복 요소 관리

> **팁**: Figma에서 직접 재현할 경우 슬라이드 Frame 크기를 `1280 × 720` 으로 설정하세요.
