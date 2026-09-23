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

**L'informativa dice il vero su *questa* versione**, che non raccoglie niente:
nessuna pubblicità, nessuna statistica, nessuna segnalazione degli errori,
nessuna richiesta di rete. Al blocco B del piano di rilascio entrano AdMob,
Firebase Analytics e Crashlytics: **l'informativa va riscritta e ripubblicata
prima che quella build raggiunga i giocatori**, non dopo. Nel repo del gioco,
`docs/piano-rilascio.md` lo segna come G3.

**`app-ads.txt` non sta qui.** È in comune per tutte le app, alla radice del
repository della vetrina (`zipanguludev.github.io/app-ads.txt`, editore
`pub-6135393007497814`, lo stesso id che sta in `docs/ids-store.md` del gioco).
AdMob lo cerca alla radice del dominio dichiarato come sito dello sviluppatore:
finché il sito dichiarato nelle schede degli store sta su
`zipanguludev.github.io`, la verifica trova già il file giusto e non c'è niente
da fare.
