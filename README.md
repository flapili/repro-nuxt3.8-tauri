# repro-nuxt3.8-tauri

repro with nuxt3.8 and tauri (alpha) error 500 on android:

setup :

- 1: git clone
- 2: install deps (pnpm i / npm y / yarn / bun / whatever you want)
- 3: rust*
- 4: android studio*

* : see tauri doc (https://beta.tauri.app/guides/prerequisites/)

repro :

- start nuxt : `pnpm run dev -p 1420 --host`
- start tauri : `pnpm run tauri dev` => ok
- start android tauri : `pnpm run tauri android dev` => not ok

```
nuxt.js?v=d306a4ef:97 [nuxt] error caught during app initialization TypeError: Cannot read properties of undefined (reading 'entries')
    at _sortRoutesMap (index.mjs?v=d306a4ef:218:16)
    at _matchRoutes (index.mjs?v=d306a4ef:200:30)
    at Object.matchAll (index.mjs?v=d306a4ef:158:25)
    at getRouteRules (manifest.js?v=d306a4ef:27:30)
    at async manifest-route-rule.js?v=d306a4ef:8:89
    at async router.js?v=d306a4ef:126:26
```

- using nuxt 3.7.4 instead of 3.8.2 => OK