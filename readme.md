<div align="center">

<img src="icon.png" width="140" alt="FCA icon — a fractal hexagon of components nested at every scale" />

# Fractal Component Architecture (FCA)

Fractal components nested at every scale, composing the software architecture. This repository documents a way of thinking about software architecture, and a way of translating that thinking directly into a project's file layout — in any language.

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg)](LICENSE)

</div>

---

## What is FCA?

The central claim is simple: **a software system is a tree of components**, and that tree should be visible, literally, in the directory structure. The directories *are* the architecture. Reading `ls -R` should be equivalent to reading a component diagram. The name comes from the property that sets it apart from generic component-based design: the **same small rule set** (what a component is, how it relates to its children, when it becomes a folder, when a folder gets its own code) applies identically **at every depth**, from the whole program down to the smallest leaf. Zoom into any node and the same shape repeats.

```text
Program
├── Actions
│   └── CreateRegistration
└── Api
    └── Routes
        └── Registration
```

> **Software is a hierarchical construct composed of components, where the filesystem provides a tangible representation of its architecture, and the source code provides the implementation of that structure.**

Structure is decided first; implementation fills the shape the tree already declares. A component's external boundary stays fixed while its internal composition grows — a leaf becoming a branch never renames or moves anything visible from outside.

## Start here

1. **Read the main document:** [fractal-component-architecture/readme.md](fractal-component-architecture/readme.md) — the vision and the language-agnostic rules (tree, leaves vs. branches, naming, composition root and dependency injection, abstract dependencies, actions, data carriers, errors, long-running components, adapters, configuration, and a checklist).
2. **Then pick your language** below to see how each idea materializes in concrete file layout and idioms.

### Main document at a glance

| Section | Topic |
| --- | --- |
| 1–2 | Purpose, philosophy, the project as a tree of components |
| 3–6 | Leaf and branch shapes, entry points, behavioral units, naming |
| 7–8 | Composition root, explicit dependency injection, abstract dependencies |
| 9–14 | Actions, data carriers, errors, long-running components, adapters, configuration |
| 15 | Language-agnostic checklist |
| 16 | Materializing FCA by language |
| 17 | Final principles |

## Language guides

| Language | Guide |
| --- | --- |
| C | [languages/c](fractal-component-architecture/languages/c/file.md) |
| C++ | [languages/cpp](fractal-component-architecture/languages/cpp/file.md) |
| C# | [languages/csharp](fractal-component-architecture/languages/csharp/file.md) |
| Go | [languages/go](fractal-component-architecture/languages/go/file.md) |
| Java | [languages/java](fractal-component-architecture/languages/java/file.md) |
| JavaScript / TypeScript | [languages/javascript-typescript](fractal-component-architecture/languages/javascript-typescript/file.md) |
| Python | [languages/python](fractal-component-architecture/languages/python/file.md) |
| Ruby | [languages/ruby](fractal-component-architecture/languages/ruby/file.md) |
| Rust | [languages/rust](fractal-component-architecture/languages/rust/file.md) |

Each guide assumes you have read the main document first.

## Repository layout

```text
.
├── documentation/   # The main, language-agnostic document
├── languages/       # One guide per language
├── icon/            # Project icon
└── license/         # CC BY 4.0
```

## The trade-off, stated honestly

FCA costs more nesting, more folders, and more clicks to reach a given file. In exchange, every component gets a boundary that never needs renegotiating as the system grows. The main document returns to this trade-off in concrete, checkable terms (§15 and §17).

## License

Licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). You may share and adapt the material, including commercially, as long as you give appropriate credit, for example:

> Fractal Component Architecture (FCA), by Augusto Viceli, CC BY 4.0

© 2026 Augusto Viceli
