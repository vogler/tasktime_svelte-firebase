# track-time_svelte-firebase

This is a test project building some todo/time-tracking app using:
- [Svelte](https://svelte.dev) as compiler for reactive UI components
- [Firebase](https://firebase.google.com/) for Auth and Firestore

Try it at https://fire-abc6b.web.app/

Conclusion: not too happy with Svelte, Firebase is ok.

Cons Svelte:
- no Typescript yet (or hard to setup)
- editor support (no Intellisense for JS in .svelte files)
- limited composability, file for every component
- element list problem:
  - immutable forces to handle all edits in list component instead of element component
  - mutable allows to move functions into element component but makes all elements react to change in any element

Pro Firebase:
- easy authentication
- Firestore:
  - real-time (can subscribe to updates)
  - offline support (even sync between tabs)
Cons Firebase:
- vendor lock-in
- can't test offline (`firebase serve` launches some server, but no local database)
- limits; what happens for >1 write/s, just queued/throttled?

More notes in [devlog.md](./devlog.md).

## develop

```bash
npm install
npm run dev
```

Open in browser; has live-reload.
