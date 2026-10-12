# Lucian UX/UI Prompt

![Lucian UX/UI Prompt: 200 interactive UI elements](.github/cover.png)

200 interactive UI elements you can try live, then take into your project as an AI prompt or as working code. Every element supports light and dark themes, pointer, touch and keyboard input, and reduced motion. No dependencies.

**Live gallery: [lucianlabs.dev/uxui-prompt](https://lucianlabs.dev/uxui-prompt/)**

[한국어 안내](#한국어)

## How to use

1. Open the gallery and try an element. Each one plays a short demo when it scrolls into view, and you can take over at any time.
2. Press **Copy prompt**. The prompt contains the element's full working code plus porting instructions.
3. Paste it into your AI coding tool (Claude Code, Cursor, Codex, …), fill in `[Insertion point]` (and `[Replacement target]` if you are replacing something), and send.

The agent first checks your framework, styling and theming setup, then ports the element into a component, maps the `--ux-*` color tokens to your theme variables, and reports what it changed and what it could not check.

If you'd rather port it yourself, **Copy code** gives you the raw HTML, CSS and JS, and **Download code** saves a standalone HTML file with a theme toggle.

To link to a specific element, add its number: `https://lucianlabs.dev/uxui-prompt/#001`.

## Run locally

All you need is Node.js. There are no packages to install.

```sh
git clone https://github.com/Seokwoooo/lucian-uxui-prompt.git
cd lucian-uxui-prompt
node src/build.mjs
open prompt-uxui-lab/index.html
```

The build checks every element and writes the whole gallery into one self-contained HTML file.

## Element format

Each element is a single file, `src/elements/NNN-slug.html`:

```html
<!-- @meta {"title":"…","category":"버튼","summary":"…","hint":"…","shape":"square","tags":["button"]} -->
<!-- @demo [["wait",400],["tap",".u001-btn"],["wait",1200]] -->
<!-- @en {"title":"…","summary":"…","hint":"…","map":[["계속하기","Continue"]]} -->
<style>.u001{…} .u001-btn{…}</style>
<div class="ux u001">…</div>
<script>(() => { const root = document.currentScript.previousElementSibling; … })();</script>
```

- `@meta`: title, category and summary. Korean is the source language.
- `@demo`: steps for the autoplay demo (`wait`, `tap`, `hover`, `glide`, `drag`, `type`, …).
- `@en`: English title and summary, plus a string map that localizes the element's code.
- Every CSS selector is scoped to `.uNNN`, and the script finds its root through `document.currentScript`, so elements never leak into each other.
- Colors come only from the `--ux-*` tokens in [`src/tokens.css`](src/tokens.css), which define both light and dark values.

`node src/build.mjs` rejects any file that breaks these rules.

## License

[MIT](LICENSE) © 2026 Seokwoooo. You can use the elements in personal and commercial projects. Code copied from the gallery starts with a one-line comment that credits the source and names the license. Please keep it in your file.

---

## 한국어

바로 눌러 볼 수 있는 UI 요소 200개를 모았습니다. 마음에 드는 요소는 AI 프롬프트나 실제 코드로 가져가세요. 모든 요소가 라이트·다크 테마, 마우스·터치·키보드 조작, 동작 줄이기 설정을 지원하고, 외부 라이브러리는 쓰지 않습니다.

**갤러리: [lucianlabs.dev/uxui-prompt](https://lucianlabs.dev/uxui-prompt/)**

### 사용법

1. 갤러리에서 요소를 직접 눌러 보세요. 화면에 보이면 스스로 시연하고, 언제든 직접 조작할 수 있습니다.
2. **프롬프트 복사**를 누르세요. 요소의 실행 코드 전체와 적용 지침이 함께 들어 있습니다.
3. Claude Code, Cursor, Codex 같은 AI 코딩 도구에 붙여넣고 `[삽입 위치]`(바꿀 요소가 있으면 `[교체 대상]`도)를 채워 보내면 됩니다.

AI는 프로젝트의 프레임워크와 스타일, 테마 방식을 먼저 확인한 뒤 요소를 컴포넌트로 옮깁니다. `--ux-*` 색 토큰은 프로젝트의 테마 변수에 연결하고, 바꾼 파일과 확인하지 못한 항목을 알려 줍니다.

직접 옮기고 싶다면 **코드 복사**로 HTML·CSS·JS 원본을 받거나, **코드 파일 받기**로 테마 전환 버튼이 있는 단독 HTML 파일을 저장하세요. 특정 요소는 `https://lucianlabs.dev/uxui-prompt/#001`처럼 번호로 바로 연결할 수 있습니다.

### 로컬에서 실행

Node.js만 있으면 됩니다. 설치할 패키지는 없습니다.

```sh
git clone https://github.com/Seokwoooo/lucian-uxui-prompt.git
cd lucian-uxui-prompt
node src/build.mjs
open prompt-uxui-lab/index.html
```

빌드는 요소 파일 형식을 모두 검사한 뒤 갤러리 전체를 HTML 파일 하나로 만듭니다. 파일 형식은 위의 [Element format](#element-format)을 참고하세요.

### 라이선스

[MIT](LICENSE) © 2026 Seokwoooo. 개인·상업 프로젝트에 자유롭게 쓸 수 있습니다. 갤러리에서 복사한 코드 맨 위에는 출처와 라이선스를 적은 주석 한 줄이 붙어 있으니, 파일에 남겨 주세요.
