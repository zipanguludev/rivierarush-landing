# rivierarush-landing

Sito del gioco **Riviera Rush**, servito via GitHub Pages:
<https://zipanguludev.github.io/rivierarush-landing/>

Stesso schema degli altri sottositi (`numberpuzzle-landing`, `counter-landing`,
`witsagora-landing`, `cartnap-landing`): un repository per app, linkato dalla
vetrina `zipanguludev.github.io`.

## Contenuti

- `index.html` — landing del gioco: icona, presentazione, griglia delle
  caratteristiche, invito ai tester. **Non ci sono ancora i badge degli store**
  perché il gioco è in test chiuso: vanno aggiunti quando esce in test aperto.
- `privacy-policy.html` — informativa sulla privacy in inglese. È l'URL che va
  nelle due console (Play Console → *Contenuti dell'app*, App Store Connect →
  *App Information*) e nel pulsante dentro il gioco.
- `privacy-policy.it.html` — la stessa informativa in italiano, linkata dalla
  versione inglese e viceversa.
- `assets/` — icona dell'app (`icon-1024.png` è il master, viene da
  `Art/Icon/icon_store_1024.png` nel repo del gioco), favicon e touch icon
  derivate da quella.
- `.nojekyll` — Pages serve i file così come sono, senza build Jekyll.

Niente build: si modificano gli `.html` e si fa push su `main`.

## Regole da non dimenticare

**Gli indirizzi delle pagine legali finiscono nelle schede degli store pubblicate
e dentro l'app: non si rinominano e non si spostano più.** Se un giorno il gioco
avrà un dominio suo, si punta il dominio a questo repository e gli URL vecchi
continuano a funzionare.

**L’informativa è un documento sul trattamento dei dati, non una presentazione del
gioco.** Dal 2026-09-23 è scritta sul modello dell’art. 13 del GDPR: titolare, dati
e finalità, base giuridica, destinatari, conservazione, diritti. Descrive AdMob e il
consenso di Google, e dice come revocarlo (menu del gioco, «Impostazioni privacy»).
Dal 2026-09-24 descrive anche la **diagnostica del motore Unity** (punto 3.4: crash,
blocchi e prestazioni inviati a Unity Technologies, base giuridica il legittimo
interesse), accesa nel progetto del gioco e dichiarata in *Sicurezza dei dati* di
Play Console. Se un giorno la si spegne, vanno tolti il punto 3.4 e le righe su
Unity ai punti 4, 5 e 6, e le due voci «solo Unity» del modulo di Play.
Di proposito **non** entra nei dettagli interni (frequenza degli annunci, premi,
funzionamento senza rete): non servono allo scopo e darebbero indicazioni per
aggirare la pubblicità. Dice invece, perché è vero, che senza consenso possono
comunque essere mostrati annunci con trattamento limitato dei dati.

Quando arrivano statistiche, segnalazione degli errori o acquisti (blocchi C e D del
piano di rilascio, nel repo del gioco) **l’informativa va aggiornata e ripubblicata
prima che quella build raggiunga i giocatori**, non dopo.

**`app-ads.txt` non sta qui.** È in comune per tutte le app, alla radice del
repository della vetrina (`zipanguludev.github.io/app-ads.txt`, editore
`pub-6135393007497814`, lo stesso id che sta in `docs/ids-store.md` del gioco).
AdMob lo cerca alla radice del dominio dichiarato come sito dello sviluppatore:
finché il sito dichiarato nelle schede degli store sta su
`zipanguludev.github.io`, la verifica trova già il file giusto e non c'è niente
da fare.
