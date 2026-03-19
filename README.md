# seefleet CMS — Kom igång

Så här deployas sajten till Netlify med CMS på 10 minuter.

---

## Mappstruktur

```
seefleet-cms/
├── index.html          ← Landningssidan
├── netlify.toml        ← Netlify-konfiguration
├── images/             ← Lägg feature-screenshots här
│   ├── feature-valuations.png
│   ├── feature-email.png
│   ├── feature-fleet.png
│   ├── feature-ais.png
│   └── feature-team.png
└── admin/
    ├── index.html      ← CMS-gränssnittet (öppnas på /admin)
    └── config.yml      ← Definierar alla redigerbara fält
```

---

## Steg 1 — Lägg upp koden på GitHub

1. Gå till github.com → New repository → kalla det `seefleet-landing`
2. Ladda upp hela den här mappen (drag & drop i GitHub-gränssnittet)
3. Klart

---

## Steg 2 — Koppla till Netlify

1. Gå till netlify.com → Log in / Sign up (gratis)
2. Klicka **"Add new site"** → **"Import an existing project"**
3. Välj **GitHub** → välj ditt repo `seefleet-landing`
4. Build settings: lämna allt tomt (ingen build-process behövs)
5. Klicka **Deploy site**

Sajten är nu live på en slumpmässig Netlify-URL (t.ex. `amazing-ship-123.netlify.app`).

---

## Steg 3 — Aktivera CMS-inloggning (Netlify Identity)

1. I Netlify → gå till **Site settings** → **Identity**
2. Klicka **"Enable Identity"**
3. Scrolla ner till **"Git Gateway"** → klicka **"Enable Git Gateway"**
4. Gå till **Identity** → **Invite users** → bjud in din e-post

Du får ett mail → klicka länken → sätt ett lösenord.

---

## Steg 4 — Logga in på CMS

Gå till: `din-netlify-url.netlify.app/admin`

Logga in med din e-post och lösenord.

Nu kan du redigera:
- ✅ All text på sidan (rubriker, knappar, beskrivningar)
- ✅ Statistiksiffrorna
- ✅ Feature-bilder (ladda upp screenshots)
- ✅ Färger (accent, navy, bakgrund)

---

## Steg 5 — Eget domännamn (valfritt)

I Netlify → **Domain settings** → **Add custom domain** → skriv in `seefleet.com` eller en subdomän.

---

## Lägga till feature-screenshots

Lägg PNG/JPG-filer i mappen `images/` med dessa exakta namn:
- `feature-valuations.png`
- `feature-email.png`
- `feature-fleet.png`
- `feature-ais.png`
- `feature-team.png`

Bilderna visas automatiskt i rätt feature-sektion.
Eller ladda upp dem direkt via CMS under **Media**.

---

## Teknisk info för Rails-teamet

Landningssidan är en **statisk HTML-fil** hostad på Netlify.
Den lever separat från Rails-appen på secure.seefleet.com.
Alla knappar/länkar pekar på secure.seefleet.com som vanligt.

Inget Rails-arbete behövs för att driftsätta den här sidan.
