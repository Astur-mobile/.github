<div align="center">
  <img src="./astur_logo_white.png" alt="Astur logo" width="180" />
  <p><strong>Device-native mobile automation for Android and iOS with Playwright ergonomics and no Appium server.</strong></p>
  <p>Native apps. Mobile web. WebView flows. One automation surface.</p>
</div>

## Why Astur

Astur is built for engineers who want direct mobile automation without the Appium stack and its surrounding setup cost. It keeps Playwright Test as the runner, uses platform-native control paths, and exposes one clear API for native mobile interactions, device control, and WebView handoff.

## What It Delivers

| Area | Astur approach |
| --- | --- |
| Runner | Playwright Test projects, fixtures, retries, reporters, traces |
| Android | ADB, UI tree parsing, gestures, app lifecycle, device controls |
| iOS | `simctl` lifecycle, screenshots, recording, XCUITest agent boundary |
| Contexts | Native automation plus WebView DOM switching |
| Artifacts | Native screenshots and recordings attached to Playwright results |
| Setup | No Appium server, no WebDriver bridge, npm-first workflow |

## Design Principles

- Platform-first control instead of a generic server layer
- Playwright-style test authoring and project orchestration
- Honest platform boundaries, especially on iOS
- Open architecture for native agents where the OS requires them
- Clear defaults with escape hatches only where they matter

## Quick Start

```bash
npx create-astur my-mobile-tests
cd my-mobile-tests
npx astur doctor
npx astur test
```

## Platform Snapshot

| Target | Status |
| --- | --- |
| Android emulator | Supported |
| Android real device | Supported |
| iOS simulator lifecycle | Supported |
| iOS native element automation | Routed through XCUITest agent boundary |
| iOS real device execution | Planned |
| BrowserStack execution | Scaffolded, not implemented in current alpha |

## npm Packages

| Package | Purpose |
| --- | --- |
| `@astur/test` | Playwright Test integration and the primary automation API |
| `astur-mobile` | CLI package that exposes the `astur` command |
| `create-astur` | Project scaffold for bootstrapping a new Astur test repository |

## Positioning

Astur does not try to hide the mobile platform. It exposes the parts that should feel like Playwright and keeps the parts that must remain platform-aware explicit. That tradeoff is the point: less ceremony, tighter control, and fewer layers between the test and the device.
