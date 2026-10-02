# AppSettings ⇄ Azure Environment Variables

Pagina statica (un solo `index.html`, nessuna dipendenza) per convertire:

- **JSON → Env**: `appsettings.json` / `local.settings.json` (sezione `Values`) nelle variabili d'ambiente di una Azure Function, nel formato *Advanced edit* del portale Azure (`[{ "name", "value", "slotSetting" }]`) oppure `KEY=VALUE`. Le chiavi annidate vengono appiattite con `__` (o `:`), gli array con l'indice (`AllowedHosts__0`).
- **Env → JSON**: il contrario. Accetta l'array del portale, un oggetto piatto o righe `KEY=VALUE`.
- **Merge** (tab dedicato): unisce una *Base* (es. le variabili attuali su Azure) con degli *Aggiornamenti*. I valori diversi vengono sovrascritti, le chiavi nuove aggiunte, quelle esistenti mantenute (incluso `slotSetting`). Entrambi i pannelli accettano qualsiasi formato supportato; il confronto delle chiavi ignora maiuscole/minuscole e tratta `:` come `__`. Un pannello elenca le chiavi modificate e aggiunte, ognuna con un check (attivo di default): deselezionandolo la modifica non viene applicata e il risultato si aggiorna subito.

Tutti gli output hanno le chiavi in ordine alfabetico.

Tutto avviene nel browser: nessun dato viene inviato altrove.
