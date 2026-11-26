# progliodario.github.io

Sito radice di `https://progliodario.github.io/`. Contiene solo questi file:

| File                          | A cosa serve                                                                                     |
| ----------------------------- | ------------------------------------------------------------------------------------------------ |
| `.well-known/assetlinks.json` | Digital Asset Links: dice a Chrome che l'app Android di [Playlist Player][pp] appartiene a questo sito, così l'app si apre **senza barra dell'indirizzo** |
| `index.html`                  | Reindirizza la radice a `/playlist-player/`                                                      |
| `.nojekyll`                   | Senza, GitHub Pages ignorerebbe la cartella `.well-known` (inizia con un punto)                  |

## Quando va modificato

- **Nuova chiave di firma dell'APK**: sostituisci l'impronta in `sha256_cert_fingerprints` con
  quella stampata dal workflow _Android APK_ di [playlist-player][pp] (sezione "Signing
  certificate", riga `SHA-256 digest`, in maiuscolo con i due punti ogni due caratteri).
- **Nuovo `applicationId`** in `app.config.json` di playlist-player: aggiorna `package_name`.
- **Un'altra app Android** sullo stesso dominio: aggiungi un altro oggetto all'array.

Verifica: <https://digitalassetlinks.googleapis.com/v1/statements:list?source.web.site=https://progliodario.github.io&relation=delegate_permission/common.handle_all_urls>

Dettagli: [docs/sviluppo/android.md][android] in playlist-player.

[pp]: https://github.com/progliodario/playlist-player
[android]: https://github.com/progliodario/playlist-player/blob/main/docs/sviluppo/android.md
