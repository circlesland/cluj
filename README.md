# Cluj - getting started

**Concrete goals for now:**
1) Add a test mode for the auth which returns a predefined key when a special URL parameter is supplied  
  1.1) Use a "magic-string"->"private key" mapping table so that we can simulate multiple accounts   
  1.2) No user interaction should be necessary in the test-mode   
2) Signer   
  2.1) Include the ethers.js library   
  2.2) Use the key from the auth with a new ethers wallet (https://docs.ethers.io/v4/api-wallet.html)   
  2.3) Create a small dialog that signs some arbitrary data and displays the result   
    2.3.1) If you're feeling fancy: Sign a transacion ;)   
3) Take a look at the gnosis safe dapps  
3.1) Check out how to integrate a Hello World app into the safe (manifest and js-lib)   
3.2) Reverse-engineer the hosting part of the gnosis safe app (see following quotes from the chat with Daniel from the gnosis safe team)
```
From the Circlesland <-> Gnosis Safe telegram chat:
As we commented in the Zoom call here you have some resources to start checking  This is Safe Apps docs, here all resources are listed, either is more oriented to Safe Apps developers than to the specific case we want to check about. https://docs.gnosis-safe.io/build/sdks/safe-apps  For your specific case the most interesting resources would be
- Safe Apps SDK https://github.com/safe-global/safe-apps-sdk
 This is the SDK that Safe Apps need to integrate so we are able to connect with them. Test application should use any of the connectors provided under “packages” folder

- In the Web side, that is not the part that is usually seen important files where Safe App communication takes place are this two
    - Communicator https://github.com/safe-global/safe-react/blob/dev/src/routes/safe/components/Apps/communicator.ts  Here we check that messages coming from the iframe make sense and that we are able to handle them
    - AppFrame https://github.com/safe-global/safe-react/blob/dev/src/routes/safe/components/Apps/components/AppFrame.tsx The actual iframe component, here we add the logic to detect the listeners

This web parts weren’t think to be reused anywhere, but you can use them as POC inspiration. We sometimes do changes in the SDK that involve changes in web to keep compatibility, so it may be a bit difficult to keep up to date. We may discuss internally if some kind of lib would make sense but still in the end some actions to what Safe Apps send you should be created on your side
```
3.1. Checkout if this is a good starting point for safe-app integration: https://github.com/rmeissner/dsafe  
3.9) Use our own circles.land app in the safe-frame (skip the signup and go directly to the dashboard - make at least banking completely work)  

4. Check out Ceramic and the DID concept and write a PoC that uses a DID document as profile   
4.1 Starting point: https://github.com/ceramicnetwork/CIP/blob/main/CIPs/CIP-101/CIP-101.md



__Notes:__
* Add a page for the case the deep-link doesn't work

Overall preliminary timeline:
### Goal 1 - Core
- All target platforms, svelte-capacitor (ios, android), electron (Windows, Linux, macOS)
  - Dapp Frame + Loader Logic 
  - Event Delivery System
  - Function => Services + Actions in seperate libraies independent of UI's
  - Router => loader + compositor (alias support)
  - JSON only Manifest - First Dapp (Hello Earth) - Orechstrating only functions and UI composites
  - Load tailwind themes (dark/light)

### Goal 2
- Mock Banking Dapp with 1 Action - Send money trigering the send xstate flow
  - Build basic design system based on Composite Pattern
  - All screensizes, mobile first, exception overwrites
  - Layouts with overflow scroll etc until perfection, one root compositor for each z-index layer (window, popup, menu-slide)
  - Schemas for components, data and mappers inbetween

### Goal 3
- WireUp Banking Dapp
  - Connect DID / Profile and SAFE
  - Connect send money API
  - Data Input Validation
  - Language Switch + Translator
  - Display transaction metadata

### Goal 4
- Build next Dapp

### Resources
- Svelte Tutorial: https://svelte.dev/tutorial/basics
- For mobile: Capactior & Svelte: https://capacitorjs.com/solution/svelte
- For desktop: https://www.electronjs.org/
- Bundler: https://vitejs.dev/
- Tailwind: https://tailwindcss.com/
- Typescript: 
