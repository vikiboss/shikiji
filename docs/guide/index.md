---
outline: deep
---

# Introduction

<br>

<span text-xl text-green>
<b><span text-yellow6>Shiki</span><span text-teal6>ji</span></b> <ruby text-yellow6>式<rt>shiki</rt></ruby><ruby text-teal6>辞<rt>ji</rt></ruby>
</span> is a beautiful and powerful syntax highlighter based on TextMate grammar and themes, the same engine as VS Code's syntax highlighting. Provides a very accurate and fast syntax highlighting for almost any mainstream programming language.

No custom RegEx to maintain, no custom CSS to maintain, no custom HTML to maintain. And as your favorite languages and themes in VS Code evolve - your syntax highlighting will evolve too.

Shikiji is a ESM-rewrite of [Shiki](https://github.com/shikijs/shiki) with quite many improvements. We aim to [merge this project back to Shiki as a milestone update](https://github.com/shikijs/shiki/issues/510).

About the name, <ruby text-lg text-yellow6>式<rt>shiki</rt></ruby><ruby text-lg text-teal6>辞<rt>ji</rt></ruby> is a Japanese word meaing ["Ceremonial Speech"](https://jisho.org/word/%E5%BC%8F%E8%BE%9E). <ruby text-yellow6 text-lg>式<rt>shiki</rt></ruby> is inherited from [shiki](https://github.com/shikijs/shiki) means ["Style"](https://jisho.org/word/%E5%BC%8F) and <ruby text-teal6 text-lg>辞<rt>ji</rt></ruby> means ["Word"](https://jisho.org/word/%E8%BE%9E).

Oh btw, the code blocks in this document is highlighted by Shikiji, as you'd expect \:)

## Features

- All grammars/themes/wasm served as pure-ESM, no more [CDN](https://github.com/shikijs/shiki#specify-a-custom-root-directory), no more [assets](https://github.com/shikijs/shiki#specify-how-to-load-webassembly).
- Portable. Does not rely on Node.js APIs or the filesystem, works in any modern JavaScript runtime.
- ESM-only ([CDN Usage](/guide/install#cdn-usage), [CJS Usage](/guide/install#cjs-usage))
- [Bundles languages/themes composedly](/guide/install#fine-grained-bundle)
- [Light/Dark themes support](/guide/dual-themes)
- [AST-based transformers addons](/guide/transformers)
- [`hast` support](/guide/transformers#codetohast)
- [TypeScript TwoSlash](/packages/twoslash)
- [Shiki-compatible build](/guide/compat)

## Playground

Here is a little playground for you to try out how Shikiji highlights your code. Unlike other code blocks that ran on the build time, this playground is rendered on the client side in the browser. Themes and languages are loaded on demand.

<ShikijiMiniPlayground />
## Bundle Size

You can inspect the bundle size in detail on [pkg-size.dev/shikiji](https://pkg-size.dev/shikiji).

As of `v0.9.2`, measured at 15th, December 2023:

| Bundle         | Size (minified) | Size (gzip) | Notes                                             |
| -------------- | --------------: | ----------: | ------------------------------------------------- |
| `shikiji`      |          6.2 MB |      1.2 MB | includes all themes and languages as async chunks |
| `shikiji/core` |           99 KB |       31 KB | without themes or languages, compose on your own  |
| `shikiji/wasm` |          623 KB |      231 KB | wasm binary inlined as base64 string              |