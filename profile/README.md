<div align="center">
  <img src="./astur_logo_white.png" alt="Astur logo" width="180" />

  ### Device-native mobile automation for Android and iOS — Playwright ergonomics, no Appium server.

  <p>
    <a href="https://astur-mobile.github.io">Docs</a> ·
    <a href="https://astur-mobile.github.io/getting-started/">Getting Started</a> ·
    <a href="https://astur-mobile.github.io/why-astur/">Why Astur</a> ·
    <a href="https://github.com/sponsors/Astur-mobile">Sponsor</a>
  </p>
</div>

---

Astur is a new generation of mobile test automation. Instead of wrapping a
remote Appium/WebDriver server, it drives **native platform agents** it builds
and manages itself — a Kotlin UIAutomator agent on Android and a Swift XCUITest
agent on iOS — behind a familiar Playwright-style API. Faster, simpler to set up,
and far harder to wedge in CI.

```bash
npm install -D @astur/test astur-mobile
```

```ts
import { test, expect } from '@astur/test';

test('login', async ({ device }) => {
  await device.getByLabel('Email').fill('qa@example.com');
  await device.getByRole('button', { name: 'Login' }).tap();
  await expect(device.getByText('Welcome')).toBeVisible();
});
```

## Why it's different

- **No Appium server, no separate runner.** Native agents are built and launched
  for you on every session.
- **One selector engine, end to end.** The locators your tests use are the same
  ones the Inspector ranks from the live tree — what you author is what runs.
- **Playwright ergonomics on mobile.** Fixtures, projects, `expect`, locators,
  and WebView automation through the Playwright/CDP bridge.
- **Native gestures.** Taps, double-taps, long-press, swipe, drag, and
  cross-platform `scrollIntoView`, executed on-device.
- **A self-healing lifecycle.** Auto-boots emulators, auto-builds and auto-signs
  the iOS agent, reaps orphaned sessions on startup, prunes stale build caches,
  and tears down cleanly on Ctrl-C or terminal close.
- **Visual Inspector & codegen** built on the same runtime, exporting
  ready-to-run `@astur/test` specs.

## Quick start

```bash
npm create astur@latest my-mobile-tests
cd my-mobile-tests
npx astur-mobile doctor
npx astur-mobile test
```

## Packages

| Package | Purpose |
| --- | --- |
| `astur-mobile` | CLI: `doctor`, `devices`, `init`, `codegen`, `inspect`, `test` |
| `@astur/test` | Playwright-style test API (fixtures, `expect`, locators) |
| `create-astur` | Project scaffolder (`npm create astur`) |
| `@astur/core` · `@astur/android` · `@astur/ios` · `@astur/protocol` | Runtime + platform drivers |

## License & brand

Astur is open source under the **Apache License 2.0**. The **Astur** name and
logo are trademarks — you can fork and build on the code, but forks must use
their own name. See each repository's `TRADEMARK.md`.

❤️ If Astur saves your team time, please consider [sponsoring](https://github.com/sponsors/Astur-mobile).
