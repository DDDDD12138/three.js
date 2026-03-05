# Three.js 中文手册翻译查漏补缺 TODO

## 执行原则
- 目标：`manual/zh` 与 `manual/en` 在结构、代码示例、链接、图片引用上保持同步（允许正文中文翻译差异和代码注释翻译差异）
- 顺序：严格按 `P0 → P1 → P2 → P3` 执行

## 优先级说明
- P0: 内容完全缺失、代码错误、异常链接 — 直接影响读者理解或代码可用性
- P1: 内容过时，需同步英文最新版 — 代码能看但与当前 API 不符
- P2: 缺少部分内容（代码块、图片、示例、章节）
- P3: 小问题（链接本地化、标题层级、样式不一致）

---

## P0 — 内容缺失 / 代码错误 / 异常链接

### ~~game.html~~ — ✅ 已完成翻译
- [x] ~~当前仅有占位符（42 行），英文原文 1931 行~~
- [x] ~~缺少全部 62 个代码块~~
- [x] ~~缺少全部 6 个 iframe 交互示例~~
- [x] ~~缺少全部图片引用~~
- [x] ~~缺少全部站内链接~~
- [x] ~~缺少全部外链和 docs 链接~~
- [x] ~~需要完整翻译~~ → 已完成（含正文、代码注释、CSS 注释）

### post-processing.html — API 过时 + 代码错误 + 异常链接
- [ ] **异常链接**：第 206 行存在 `notion://www.notion.so/threejs-rendertargets.html`，应改为 `rendertargets.html`
- [ ] **全角标点 bug**：第 185 行 `texture2D（tDiffuse，vUv）` → `texture2D(tDiffuse, vUv)`（全角括号和逗号会导致 GLSL 代码无法运行）
- [ ] **BloomPass API 过时**：ZH 使用 `copyUniforms['opacity']`，EN 已更新为 `combineUniforms['strength']`
- [ ] **缺少 `OutputPass` 章节**：EN 第 94-107 行有独立段落和代码块，ZH 完全缺失
- [ ] 缺少 1 个代码块（EN 16 个，ZH 15 个）

---

## P1 — 内容过时，需同步更新

### fundamentals.html — es6 模块章节过时
- [ ] EN 已更新为 import maps 方式（r147+），包含 `<script type="importmap">` 用法
- [ ] ZH 仍为旧版（r106），使用文件夹结构 + 相对路径方式，内容已不适用
- [ ] 需要**重写** `#es6` 底部栏整个章节，对齐 EN 的 import maps 内容
- [ ] ZH 缺少 1 个代码块（EN 23 个，ZH 22 个）
- [ ] ZH 缺少站内链接 `geometry.html`（需确认 EN 中是否仍存在该目标）

### prerequisites.html — 缺少章节和代码示例
- [ ] 缺少 `es6 modules` 独立章节（EN 第 41 行的 `<h2>`，含 `<script type="module">` 示例代码块）
- [ ] 缺少数组解构示例：`const y = position[1]` 和 `const [, y, z] = position`（2 个代码块）
- [ ] 缺少对象简写完整代码示例（`const dims = {width: 300, height: 150}`，1 个代码块）
- [ ] 缺少箭头函数对比写法 `const foo = (args) => {}`（1 个代码块）
- [ ] 缺少 `copiedPositionArray` 展开运算符示例（1 个代码块）
- [ ] 缺少编码风格/命名规范代码示例（EN 末尾 `const v = new vector()` 部分，1 个代码块）
- [ ] 缺少站内链接 `fundamentals.html`
- [ ] 共缺少 8 个代码块（EN 29 个，ZH 21 个）

---

## P2 — 部分内容缺失

### offscreencanvas.html — 缺少中间步骤代码（4 个代码块）
- [ ] EN 有 `ElementProxyReceiver` 逐步演化过程，ZH 跳过了中间步骤直接给出最终代码：
  - `focus()` noop 方法
  - `preventDefault` / `stopPropagation` noop 处理
  - `clientWidth` / `clientHeight` getter
  - `getBoundingClientRect()` 方法
- [ ] 教学效果不如 EN，建议补充中间步骤
- [ ] 共缺少 4 个代码块（EN 43 个，ZH 39 个）

### responsive.html — 缺少整个章节
- [ ] 缺少 "HD-DPI: Limiting maximum drawing buffer size" 整个章节（EN 第 261 行的 `<h2>`）
- [ ] 该章节包含 `resizeRendererToDisplaySize(renderer, maxPixelCount)` 的代码块
- [ ] EN 有 2 个 h2 标题，ZH 只有 1 个
- [ ] 缺少 1 个代码块（EN 9 个，ZH 8 个）

### shadows.html — 缺少图片和注释段落
- [ ] 缺少 `low-res-shadow-map-spotlight.png` 图片引用
- [ ] 缺少 SpotLight shadow-radius 模糊效果的注释段落（EN 中为 HTML 注释，ZH 完全没有对应内容）
- [ ] EN 有 7 个 iframe，ZH 有 6 个

### multiple-scenes.html — 缺少图片 + 标题层级异常
- [ ] 缺少 `multi-view-fixed.gif` 图片引用（展示修复后滚动效果）
- [ ] EN 有 6 个媒体引用，ZH 有 5 个
- [ ] ZH 有 7 个 h2/h3 标题，EN 只有 4 个 — ZH 多出了"基本方法""另一个方法""更新的方法"等额外标题
- [ ] "使用HTML Dataset"在 ZH 中是 `<h3>` 但 EN 中是 `<h2>`，层级不一致

### setup.html — 缺少代码块
- [ ] 缺少 1 个代码块（EN 4 个，ZH 3 个）
- [ ] 缺少的是 `cd path/to/folder/where/you/unzipped/files` + `servez` 命令示例

---

## P3 — 小问题

### 3.1 站内链接差异（3 个文件）
- [ ] `creating-a-scene.html`：ZH 多出 `installation.html` 链接，EN 无此链接，需确认是否应保留
- [ ] `load-obj.html`：ZH 缺少 `load-gltf.html` 站内链接
- [ ] `align-html-elements-to-3d.html`：ZH 缺少 geo-picking GitHub 链接 (`https://github.com/mrdoob/three.js/blob/master/manual/resources/tools/geo-picking/`)

### 3.2 Docs 链接本地化（11 个文件）
以下文件的 `/docs/#api/` 链接需检查，确保 ZH 版使用 `/docs/#api/zh/` 而非 `/docs/#api/en/`：
- [ ] `backgrounds.html` — 已确认 6 处使用了 `/api/en/`，需改为 `/api/zh/`
- [ ] `cameras.html`
- [ ] `debugging-glsl.html` — ZH 完全缺少 docs 链接（EN 有 3 个），需补充
- [ ] `lights.html` — ZH 链接数（20）多于 EN（15），需排查冗余
- [ ] `load-obj.html`
- [ ] `materials.html`
- [ ] `optimize-lots-of-objects.html`
- [ ] `post-processing.html`
- [ ] `primitives.html`
- [ ] `shadows.html`
- [x] `game.html` — 翻译时已保留 EN 原始 docs 链接

### 3.3 标题层级差异（2 个文件）
- [ ] `multiple-scenes.html`：已在 P2 中列出
- [ ] `prerequisites.html`：ZH 缺少 EN 的第一个 `<h2>` (es6 modules)，已在 P1 中列出

### 3.4 代码块样式不一致
- [ ] `fundamentals.html` ZH 的 es6 章节代码块缺少 `showlinemods notranslate lang-html translate="no"` 等 class（随 P1 重写一并修复）
- [ ] `prerequisites.html` 部分代码块 class 格式与 EN 不一致（如用 `notranslate notranslate` 替代 `lang-js`）

---

## 不需要修复的项（排除项）

以下差异属于**正常翻译行为**，不需要同步：
- 代码块内注释的中文翻译（如 `// left` → `// 左侧`，`// compute a canvas relative rectangle` → `// 计算canvas的尺寸`）
- 中文表述比英文更简洁导致的行数差异（大部分文件 ZH 行数少于 EN 属正常）
- 尾部逗号风格差异（如 `dir: [ -1, 0, 0, ]` vs `dir: [ -1, 0, 0 ]`）

---

## 统计

| 状态 | 文件数 | 文件 |
|------|--------|------|
| P0 — 完全缺失/代码错误 | 2（game ✅） | ~~game~~, post-processing |
| P1 — 内容过时 | 2 | fundamentals, prerequisites |
| P2 — 部分缺失 | 5 | offscreencanvas, responsive, shadows, multiple-scenes, setup |
| P3 — 小问题 | 14 | creating-a-scene, load-obj, align-html-elements-to-3d, backgrounds, cameras, debugging-glsl, lights, materials, optimize-lots-of-objects, primitives, shadows(链接), multiple-scenes(标题), fundamentals(样式), prerequisites(样式) |
| 无问题 | 40+ | 其余文件 |

---

## 已一致的页面（20 个，无需处理）
- `creating-text.html`
- `custom-buffergeometry.html`
- `debugging-javascript.html`
- `faq.html`
- `fog.html`
- `how-to-create-vr-content.html`
- `how-to-dispose-of-objects.html`
- `installation.html`
- `libraries-and-plugins.html`
- `loading-3d-models.html`
- `material-table.html`
- `matrix-transformations.html`
- `physics.html`
- `rendertargets.html`
- `shadertoy.html`
- `tips.html`
- `transparency.html`
- `uniform-types.html`
- `useful-links.html`
- `webgpurenderer.html`

---

## 完成定义（DoD）
- [ ] P0 全部勾选完成
- [ ] P1 全部勾选完成
- [ ] P2 全部勾选完成
- [ ] P3 全部勾选完成
