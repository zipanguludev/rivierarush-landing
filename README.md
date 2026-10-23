# rivierarush-landing

Sito del gioco **Riviera Rush**, servito via GitHub Pages:
<https://zipanguludev.github.io/rivierarush-landing/>

Stesso schema degli altri sottositi (`numberpuzzle-landing`, `counter-landing`,
`witsagora-landing`, `cartnap-landing`): un repository per app, linkato dalla
vetrina `zipanguludev.github.io`.

## Contenuti

- `index.html` — il sito in inglese (lingua predefinita, `x-default`) e
  `it/index.html` la stessa pagina in italiano. Le due pagine hanno la stessa
  struttura: apertura con il video «Day 1 → Day 9», numeri, come si gioca, eventi,
  i cinque lidi, recensioni del gioco, trailer, domande, invito a scaricare.
  **Quando si cambia una pagina si cambia anche l'altra**, compresi i dati
  strutturati (`application/ld+json`) e i `hreflang`.
- `privacy-policy.html` — informativa sulla privacy in inglese. È l'URL che va
  nelle due console (Play Console → *Contenuti dell'app*, App Store Connect →
  *App Information*) e nel pulsante dentro il gioco.
- `privacy-policy.it.html` — la stessa informativa in italiano, linkata dalla
  versione inglese e viceversa.
- `assets/site.css`, `assets/site.js` — stile e script comuni alle due pagine.
  Nessuno script di terze parti, nessun cookie, nessuna statistica.
- `assets/fonts/` — Fredoka SemiBold servito dal sito (non da Google Fonts),
  con la sua licenza OFL accanto. È lo stesso file del gioco.
- `assets/` — icona dell'app (`icon-1024.png` è il master, viene da
  `Art/Icon/icon_store_1024.png` nel repo del gioco; `icon-512.png` è
  `icon_play_512.png`), favicon e touch icon derivate da quella;
  `og-en.jpg` / `og-it.jpg` sono le anteprime per i social (1200×630).
- `assets/img/` — gli screenshot della scheda di Google Play
  (`docs/store/play/<lingua>/phone_0N.png` del gioco, ridotti a 540×960) e la
  mappa dell'Italia presa dalle riprese del trailer.
- `assets/video/` — il loop «Day 1 → Day 9» dell'apertura e il trailer, in
  inglese e italiano, con le loro copertine. Vengono da `Recordings/promo/out/`
  sul Mac (`beforeafter_916_<lingua>.mp4`; il trailer dal 2026-10-23 è quello
  della 1.1, `1.1/RivieraRush_1.1_GooglePlay_<LINGUA>_9x16.mp4`, con la
  copertina presa dalla scheda finale a 31 s), ricompressi con ffmpeg (H.264;
  il loop 540×960 senza audio, il trailer 720×1280, CRF 26). Il trailer si
  scarica solo quando lo si avvia. Nei dati strutturati `embedUrl` e
  `uploadDate` sono quelli del video su YouTube (inglese `0GiJJc5XI9s`,
  italiano `iTGYYT-sv6I`): cambiando trailer vanno cambiati insieme.
- `.nojekyll` — Pages serve i file così come sono, senza build Jekyll.

Niente build: si modificano gli `.html` e si fa push su `main`.

**App Store** (dal 2026-10-23, quando il gioco è uscito su iPhone): badge
ufficiale di Apple per primo nella fila (`assets/app-store-badge-en.svg` e
`-it.svg`, gli stessi dei video del gioco, alti quanto quello di Google Play),
link `apps.apple.com/us|it/app/riviera-rush/id6816526737`, App Store in
`operatingSystem`, `gamePlatform` e `sameAs`, domande e descrizioni senza «coming
soon», `<meta name="apple-itunes-app" content="app-id=6816526737">` e, in fondo,
le righe dei marchi di Apple.

**Ricerca Google**: la proprietà di Search Console è `https://zipanguludev.github.io/`
(nel repository della vetrina). La sitemap di tutto il dominio è lì, in
`sitemap.xml`: quando si aggiunge una pagina a questo sito va aggiunta anche lì.

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

Dal 2026-09-26 descrive anche **Firebase** (blocco C del piano di rilascio, nel repo del
gioco): statistiche di Google Analytics for Firebase (punto 3.5, base giuridica il
consenso nel SEE, nel Regno Unito e in Svizzera, raccolto con lo stesso modulo di Google:
nel gioco restano spente finché non ci sono le finalità 1 e 8, e non usano mai
l'identificativo pubblicitario), segnalazione degli arresti anomali di Crashlytics
(punto 3.6) e impostazioni a distanza di Remote Config (punto 3.7), entrambe su legittimo
interesse; Google come responsabile del trattamento (punto 5); conservazione 2 mesi per le
statistiche e 90 giorni per i rapporti (punto 6). I 2 mesi sono l'impostazione predefinita
di Analytics: se nella console si passa a 14 mesi, va cambiato il punto 6. Se un giorno si
toglie un servizio Firebase dal gioco, vanno tolti il suo punto e le righe corrispondenti
ai punti 4, 5 e 6. Il testo di partenza è `docs/privacy-firebase.md` nel repo del gioco.

Dal 2026-09-30 il contatto del titolare, nelle due lingue e nella pagina del sito, è
**rivierarush.game@gmail.com**: l'indirizzo creato apposta per il pubblico, lo stesso della
scheda di Google Play. L'indirizzo dell'account delle console non va scritto su queste pagine.

Quando arrivano gli acquisti (blocco D) **l’informativa va aggiornata e ripubblicata
prima che quella build raggiunga i giocatori**, non dopo.

**`app-ads.txt` non sta qui.** È in comune per tutte le app, alla radice del
repository della vetrina (`zipanguludev.github.io/app-ads.txt`, editore
`pub-6135393007497814`, lo stesso id che sta in `docs/ids-store.md` del gioco).
AdMob lo cerca alla radice del dominio dichiarato come sito dello sviluppatore:
finché il sito dichiarato nelle schede degli store sta su
`zipanguludev.github.io`, la verifica trova già il file giusto e non c'è niente
da fare.
