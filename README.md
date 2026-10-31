# Kupi Pametno

Magazin afiliat pentru Serbia - ghid de cumpăraturi inteligente, în sârbă (latinică, ekavică).

**Live:** kupipametno.freehtml.dev (Cloudflare Pages, auto-deploy din `main`)

## Ce e

Un singur fișier HTML (`index.html`), zero dependente externe, zero CDN, zero cookie-uri de tracking:

- **Asistent de alegere** - 6 întrebări cu scor → top 3 recomandări cu procent de potrivire și motive
- **Catalog** - 24 produse (casă / birou / călătorii / securitate) + 2 abonamente software, cu filtre, căutare, sortare
- **FAQ** - transparență totală: ce sunt linkurile de partener, cum se aleg produsele, confidențialitate
- Light/dark (persistat local, prefix `kp-`), complet responsive

## Cum se actualizează

1. Editează `index.html`
2. QA: extrage `<script>` → `node --check`; Playwright: catalog 24 carduri, finder complet, temă, mobil 390px, zero erori consolă
3. Commit + push pe `main` → Cloudflare Pages se publică automat în 1-2 minute

## Linkuri affiliate

`const AFF` din script conține parametrii de partener pentru fiecare sursă (AliExpress, Gigatron, Amazon, web). Cât e gol, toate linkurile ies curate (fără parametri). După aprobările din programe, se completează valorile - `buyUrl()` le atașează automat la toate linkurile.

Surse linkuri (verificate 23.10.2026):
- Gigatron: `gigatron.rs/pretraga?q=TERMEN` (NU `?query=` - dă 404)
- AliExpress: `aliexpress.com/w/wholesale-TERMEN.html`
- Amazon: `amazon.de/s?k=TERMEN`

## Reguli de conținut

- „-" niciodată "—" în textele vizibile
- Prețurile sunt întotdeauna marcate "orijentaciono" (orientative)
- Fără reduceri false, fără specificații inventate - fiecare produs are și contra
- Disclosure vizibil: strip în hero + badge pe fiecare card + secțiune dedicată + FAQ

## Licență

Proprietate privată, toate drepturile rezervate. Vezi `LICENSE`.

Repo-ul e public din 31.10.2026, la decizia proprietarului, pentru transparență - nu ca
open source. Vizualizarea și fork-ul pe GitHub sînt permise doar cît cere Termenii GitHub;
nu dau dreptul de a folosi, publica sau implementa conținutul.
