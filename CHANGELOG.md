# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 2.0.0 - 2026-08-26

### Breaking

- Removed `PocketShare` — Pocket was shut down by Mozilla in July 2025.
- Removed `WorkplaceShare` — Meta Workplace was discontinued in 2026.
- The CommonJS build moved from `dist/index.js` to `dist/index.cjs`, and a proper `exports` map was added to `package.json`. This fixes the class of bugs where `dist/index.js` was treated as an ES module and crashed CommonJS consumers.

### Added

- `XShare` — the canonical X (formerly Twitter) button. Renders the X logo and opens `https://x.com/intent/post`. Props: `url`, `title`, `via`, `hashtags`, `related`.
- `BlueskyShare` — opens `https://bsky.app/intent/compose`. Props: `url`, `title`, `separator`.
- `ThreadsShare` — opens `https://www.threads.net/intent/post`. Props: `url`, `title`.
- `VKShare` export. The README always documented `import { VKShare }`, but only the misspelled `VKShareShare` export existed; `VKShareShare` remains as a deprecated alias.
- All standard button HTML props (`className`, `style`, `data-*`, `aria-*`, event handlers, etc.) are now forwarded to the underlying `<button>` — the buttons can finally be styled with CSS classes (#5). `disabled` now truly disables the button and applies `disabledStyle`; `iconStyle` and `iconFillColor` now work.
- TypeScript prop/param types are now exported from the package root.
- `'use client'` banner in the bundle — the components work when imported directly into Next.js App Router server components.
- React 19 support: the peer dependency range is now `^17 || ^18 || ^19`, and `defaultProps` was removed internally. Fixes buttons silently not opening under React 19 (#8, #4).

### Changed

- `TwitterShare` is now a deprecated alias of `XShare` — it renders the X icon and opens `x.com/intent/post`.
- Share endpoints refreshed: WhatsApp always uses `api.whatsapp.com/send`; Telegram uses `t.me/share/url`; LinkedIn uses `www.linkedin.com/sharing/share-offsite/`; Hatena, Instapaper and Weibo upgraded to https.
- Popup windows opened with `blankTarget` now use `noopener,noreferrer` (security).
- Toolchain modernized: rollup + `@rollup/plugin-typescript`, TypeScript 5.9, ESLint 9 flat config, sourcemaps shipped, no more minified-only output.

### Fixed

- Buttons render `type="button"`, so they no longer accidentally submit surrounding forms.
- The keyboard focus outline is no longer stripped — keyboard users get a visible focus indicator again (#6).
- Hatena link params are now properly URL-encoded.
- Tumblr `tags` prop is now correctly typed as `string[]`.
- Email button: clicking navigates to the `mailto:` link, and a custom `onClick` no longer breaks it.

## 1.1.0 - 2023-12-04

- Last v1 release (React 18).
