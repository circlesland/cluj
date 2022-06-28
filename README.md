# Cluj - getting started

## Goal 1 - Core
- All target platforms, svelte-capacitor (ios, android), electron (Windows, Linux, macOS)
  - Dapp Frame + Loader Logic 
  - Event Delivery System
  - Function => Services + Actions in seperate libraies independent of UI's
  - Router => loader + compositor (alias support)
  - JSON only Manifest - First Dapp (Hello Earth) - Orechstrating only functions and UI composites
  - Load tailwind themes (dark/light)

## Goal 2
- Mock Banking Dapp with 1 Action - Send money trigering the send xstate flow
  - Build basic design system based on Composite Pattern
  - All screensizes, mobile first, exception overwrites
  - Layouts with overflow scroll etc until perfection, one root compositor for each z-index layer (window, popup, menu-slide)
  - Schemas for components, data and mappers inbetween

## Goal 3
- WireUp Banking Dapp
  - Connect DID / Profile and SAFE
  - Connect send money API
  - Data Input Validation
  - Language Switch + Translator
  - Display transaction metadata

## Goal 4
- Build next Dapp

## Resources
- Svelte Tutorial: https://svelte.dev/tutorial/basics
