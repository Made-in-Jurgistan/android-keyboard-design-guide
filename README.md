<div align="center">

# <img src="https://api.iconify.design/lucide:keyboard.svg?color=%23b25a1a" width="28" height="28" alt="" /> Android Keyboard Design Guide

### The Comprehensive Resource for Production-Grade Android IME Development

**27 Sections · API 30–36 · Kotlin · Jetpack Compose · Material You 3.0**

[![Version](https://img.shields.io/badge/version-2026.2.0-b25a1a?style=flat-square)](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/)
[![License](https://img.shields.io/badge/license-CC%20BY--SA%204.0-b25a1a?style=flat-square)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Accessibility](https://img.shields.io/badge/WCAG-2.2%20AA-b25a1a?style=flat-square)](https://www.w3.org/TR/WCAG22/)
[![Print Ready](https://img.shields.io/badge/print-A4%20ready-b25a1a?style=flat-square)](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/)

</div>

---

> **From first principles to expert-level implementations** — the complete guide to building
> Android Input Method Editors (IMEs) with `InputMethodService`, Jetpack Compose, Material You 3.0,
> dynamic color, gesture typing, voice input, clipboard integration, and production deployment.

---

## <img src="https://api.iconify.design/lucide:book-open.svg?color=%23b25a1a" width="20" height="20" alt="" /> Table of Contents

| # | Section | Group | Focus |
|---|---------|-------|-------|
| 01 | Introduction | Getting Started | Architecture overview, API level landscape |
| 02 | API Level Overview | Getting Started | API 30–36 features, market share, compatibility |
| 03 | Architecture Patterns | Getting Started | MVVM/MVI for IME, state management, unidirectional flow |
| 04 | Project Setup | Getting Started | Gradle config, manifest, `method.xml`, build variants |
| 05 | InputMethodService | Core Implementation | Lifecycle, `onCreateInputView`, `onStartInput`, window management |
| 06 | Layout System | Core Implementation | XML keyboards, `KeyboardView`, rows, keys, codes |
| 07 | Compose UI for Keyboards | Core Implementation | Compose for IME, `BasicTextField`, state hoisting |
| 08 | Keyboard Views | Core Implementation | Custom `View` rendering, canvas drawing, hardware accel |
| 09 | InputConnection | Core Implementation | Text injection, `commitText`, `deleteSurroundingText`, batch edits |
| 10 | Material You 3.0 | Material You Design | M3 components, color roles, typography scales |
| 11 | Dynamic Color | Material You Design | HCT color space, `DynamicColors` API, tonal palettes |
| 12 | Theming System | Material You Design | Light/dark themes, user preferences, runtime switching |
| 13 | Motion & Animations | Material You Design | Spring physics, keyframes, `AnimatedVisibility`, haptic sync |
| 14 | Dark Mode Best Practices | UI/UX Excellence | 2026 standards, contrast ratios, OLED optimization |
| 15 | Adaptive Layouts | UI/UX Excellence | Foldables, split-screen, `WindowManager`, `FoldingFeature` |
| 16 | Haptic Feedback | UI/UX Excellence | `Vibrator` API, predefined effects, custom waveforms |
| 17 | Sound Effects | UI/UX Excellence | `SoundPool`, audio focus, low-latency playback |
| 18 | Gesture Typing | Advanced Features | Swipe path recognition, dictionary lookup, debounce |
| 19 | Autocorrect & Text Prediction | Advanced Features | N-gram models, user dictionary, confidence scoring |
| 20 | Voice Input | Advanced Features | `SpeechRecognizer`, on-device recognition (API 33+) |
| 21 | Clipboard Management | Advanced Features | `ClipboardManager`, history, rich content (API 25+) |
| 22 | Performance Optimization | Production Quality | Recomposition, `Baseline Profile`, memory, jank |
| 23 | Accessibility | Production Quality | WCAG 2.2 AA, `AccessibilityNodeInfo`, focus management |
| 24 | Testing Strategies | Production Quality | Unit, instrumentation, `Robolectric`, Firebase Test Lab |
| 25 | Deployment | Production Quality | Play Store, `app-bundle`, signing, proguard, distribution |
| 26 | Code Examples | References | Complete Kotlin snippets for every pattern |
| 27 | Resources | References | Curated links, related guides, staying current |

---

## <img src="https://api.iconify.design/lucide:key-round.svg?color=%23b25a1a" width="20" height="20" alt="" /> Key Technologies

| Category | Technologies |
|----------|-------------|
| **Core Framework** | `InputMethodService`, `InputConnection`, `EditorInfo`, `KeyboardView` |
| **UI** | Jetpack Compose, Material You 3.0, `DynamicColors`, custom `View` rendering |
| **Language** | Kotlin, Coroutines, Flow |
| **Architecture** | MVVM/MVI, StateFlow, unidirectional data flow |
| **Animation** | Spring physics, `AnimatedVisibility`, `Animatable`, haptic synchronization |
| **Input** | Gesture typing, autocorrect, voice input (`SpeechRecognizer`), clipboard, stylus |
| **Dynamic Color** | HCT color space, tonal palettes, `DynamicColors` API (API 31+) |
| **Performance** | `Baseline Profile`, Compose Compiler Metrics, `Perfetto`, LeakCanary |
| **Testing** | JUnit, `Robolectric`, Espresso, Firebase Test Lab |
| **API Range** | API 30 (minSdk) through API 36 (latest) |

---

## <img src="https://api.iconify.design/lucide:sparkles.svg?color=%23b25a1a" width="20" height="20" alt="" /> Guide Features

- **<img src="https://api.iconify.design/lucide:ruler.svg?color=%23b25a1a" width="16" height="16" alt="" /> Print-Ready** — A4 duplex margins, page-break controls, print-safe color resets
- **<img src="https://api.iconify.design/lucide:accessibility.svg?color=%23b25a1a" width="16" height="16" alt="" /> WCAG 2.2 AA** — Keyboard navigation, skip links, `:focus-visible` outlines, reduced-motion support, forced-colors support
- **<img src="https://api.iconify.design/lucide:search.svg?color=%23b25a1a" width="16" height="16" alt="" /> SEO Optimized** — Open Graph, JSON-LD `TechArticle` structured data, canonical URL
- **<img src="https://api.iconify.design/lucide:palette.svg?color=%23b25a1a" width="16" height="16" alt="" /> Editorial Design** — Lora (display) · DM Sans (body) · JetBrains Mono (code); warm paper palette with burnt sienna accent (`#b25a1a`)
- **<img src="https://api.iconify.design/lucide:smartphone.svg?color=%23b25a1a" width="16" height="16" alt="" /> Responsive** — CSS-only sidebar navigation, mobile hamburger menu, scroll progress indicator
- **<img src="https://api.iconify.design/lucide:zap.svg?color=%23b25a1a" width="16" height="16" alt="" /> Performance** — `content-visibility: auto`, `@property` typed custom properties, layered CSS architecture
- **<img src="https://api.iconify.design/lucide:rainbow.svg?color=%23b25a1a" width="16" height="16" alt="" /> Wide Gamut** — `color-gamut: p3` media query with OKLCH accent colors

---

## <img src="https://api.iconify.design/lucide:rocket.svg?color=%23b25a1a" width="20" height="20" alt="" /> Getting Started

### Read Online

Visit the hosted guide: **[Made-in-Jurgistan.github.io/android-keyboard-design-guide](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/)**

### Read Locally

```bash
git clone https://github.com/Made-in-Jurgistan/Made-in-Jurgistan.github.io.git
cd Made-in-Jurgistan.github.io/android-keyboard-design-guide
open Android_Keyboard_Design_Guide.html
# or serve locally:
python -m http.server 8000
# navigate to http://localhost:8000
```

### Print to PDF

Open the HTML file in Chrome/Edge → `Ctrl+P` → set paper size to A4 → enable background graphics → print to PDF.

---

## <img src="https://api.iconify.design/lucide:build.svg?color=%23b25a1a" width="20" height="20" alt="" /> IME Architecture at a Glance

```text
  ┌─────────────────────────────────────────────────────────────────────┐
  │                         Android System                              │
  │  ┌─────────────┐    ┌──────────────────────────────────────────────┐  │
  │  │  Client App │───▶│      InputMethodService                      │  │
  │  │ (EditorInfo)│    │  ┌──────────┐  ┌───────────┐                │  │
  │  └─────────────┘    │  │ UI Layer │  │  Logic    │                │  │
  │                     │  │ Compose  │  │  State    │                │  │
  │                     │  │ XML View │  │  Flow     │                │  │
  │                     │  └──────────┘  └───────────┘                │  │
  │                     │       │              │                      │  │
  │                     │       ▼              ▼                      │  │
  │                     │  ┌────────────────────────────────────────┐  │  │
  │                     │  │          InputConnection               │  │  │
  │                     │  │  commitText · deleteSurroundingText    │  │  │
  │                     │  └────────────────────────────────────────┘  │  │
  │                     └──────────────────────────────────────────────┘  │
  └─────────────────────────────────────────────────────────────────────┘
```

---

## <img src="https://api.iconify.design/lucide:library.svg?color=%23b25a1a" width="20" height="20" alt="" /> Related Guides

| Guide | Focus |
|-------|-------|
| **Android Keyboard: 3D & Personalization** | 3D rendering, PBR materials, custom themes, game engine bridges |
| **Mobile STT Engineering Guide** | On-device speech-to-text: audio capture, VAD, model inference, post-processing |
| **Debugging Field Manual** | Cross-platform debugging, AI-augmented workflows, 30 sections |

---

## <img src="https://api.iconify.design/lucide:file-text.svg?color=%23b25a1a" width="20" height="20" alt="" /> Metadata

| Field | Value |
|-------|-------|
| **Author** | Made in Jurgistan |
| **Version** | 2026.2.0 |
| **Published** | 2026-01-15 |
| **Updated** | 2026-01-15 |
| **License** | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) |
| **Accessibility** | WCAG 2.2 AA |
| **Canonical URL** | `https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/` |
| **Theme Color** | `#b25a1a` (Burnt Sienna) |
| **Fonts** | Lora · DM Sans · JetBrains Mono |

---

## <img src="https://api.iconify.design/lucide:git-pull-request.svg?color=%23b25a1a" width="20" height="20" alt="" /> Contributing

Report issues or suggest improvements: [github.com/Made-in-Jurgistan/android-keyboard-design-guide-2026/issues](https://github.com/Made-in-Jurgistan/android-keyboard-design-guide-2026/issues)

---

## <img src="https://api.iconify.design/lucide:scale.svg?color=%23b25a1a" width="20" height="20" alt="" /> License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) — Free to share and adapt with attribution. See [`LICENSE-Keyboard.md`](LICENSE-Keyboard.md) for details.

---

## <img src="https://api.iconify.design/lucide:quote.svg?color=%237c3aed" width="20" height="20" alt="" /> How to Cite

If you reference this guide in academic work, documentation, or project READMEs, please use one of the formats below. Both are consistent with the output generated by GitHub's "Cite this repository" button and the [`cffconvert`](https://github.com/citation-file-format/cffconvert) tool from the repository's `CITATION.cff` file.

### APA (7th Edition)

```text
Made in Jurgistan. (2026). Android Keyboard Design Guide (Version 2026.2.0) [Computer software]. https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/
```

### BibTeX

```bibtex
@software{Made_in_Jurgistan_Android_Keyboard_2026,
  author = {Made in Jurgistan},
  month = {1},
  title = {{Android Keyboard Design Guide}},
  url = {https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/},
  version = {2026.2.0},
  year = {2026}
}
```

> **Note:** A `CITATION.cff` file at the repository root also enables GitHub's built-in "Cite this repository" button (right sidebar on the repo page), which auto-generates APA and BibTeX citations from the same metadata.

---

<div align="center">

**Made in Jurgistan** — Complete Edition · 2026

</div>
