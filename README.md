# micro

A microblogging nostr client — **composed entirely from independent
nostr-client components**. No build step, no bundler, no framework. This whole
client is one HTML file that imports web components from their own repos.

**Live:** https://nostr-client.github.io/micro/

```html
<script type="module">
  import 'https://nostr-client.github.io/login/login.js'
  import 'https://nostr-client.github.io/composer/composer.js'
  import 'https://nostr-client.github.io/feed/feed.js'
  import 'https://nostr-client.github.io/profile-editor/profile-editor.js'
</script>

<nostr-login></nostr-login>
<nostr-composer></nostr-composer>
<nostr-feed limit="30"></nostr-feed>
<nostr-profile-editor></nostr-profile-editor>
```

Plus ~40 lines of glue for tabs and a "Following" feed (the user's kind-3
contact list piped into `<nostr-feed authors="…">`).

## Why this exists

It's the proof of the [nostr-client](https://github.com/nostr-client) thesis:
if each part does one thing and speaks the shared contract (hex pubkeys,
NIP-07-shaped `window.nostrSigner`, `nostr:*` window events, one shared relay
pool), then *a client is just a page that arranges parts*.

Fork this repo, delete what you don't want, add parts you do — no toolchain to
set up. Swap any component for your own implementation by changing one URL.

## License

AGPL-3.0-or-later
