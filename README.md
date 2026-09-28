# AppSettings ⇄ Azure Environment Variables

Pagina statica (un solo `index.html`, nessuna dipendenza) per convertire:

- **JSON → Env**: `appsettings.json` / `local.settings.json` (sezione `Values`) nelle variabili d'ambiente di una Azure Function, nel formato *Advanced edit* del portale Azure (`[{ "name", "value", "slotSetting" }]`) oppure `KEY=VALUE`. Le chiavi annidate vengono appiattite con `__` (o `:`), gli array con l'indice (`AllowedHosts__0`).
- **Env → JSON**: il contrario. Accetta l'array del portale, un oggetto piatto o righe `KEY=VALUE`.

Tutto avviene nel browser: nessun dato viene inviato altrove.

## Pubblicazione su GitHub Pages

1. Crea un repository e fai push di `index.html`.
2. *Settings → Pages → Build and deployment*: Source **Deploy from a branch**, branch `main`, cartella `/ (root)`.
3. Il sito sarà su `https://<utente>.github.io/<repo>/`.
