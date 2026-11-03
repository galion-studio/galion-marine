# Galion Marine AI

[![Status](https://img.shields.io/badge/status-concept%20%2F%20skica-blue)](#status)
[![Senzori](https://img.shields.io/badge/senzori-LiDAR%20%2B%20vizija%20%2B%20akustika-teal)](#senzorski-stog)
[![Licence](https://img.shields.io/badge/licence-MIT-green)](LICENSE)

**Hrvatski (primarni)** · [English below](#english-summary)

Sustav **automatskog vođenja** za plovila tipa **Teglenica TSO-36**: fuzija **LiDAR-a**, **vizije (kamere)** i **zvuka (akustika)** na brodskom računalu — asistencija i nadzirana autonomija na linijama otok ↔ kopno Splitsko-dalmatinske županije.

**Autor i voditelj projekta:** Maciej Grajczyk · Galion Studio ([galion.studio](https://galion.studio) · [galion.app](https://galion.app))

> **Ovaj repozitorij nije** brodogradnja Teglenice, nije energana i nije plutajući podatkovni centar. Brodovi, luke i zatvoreni spremnici žive u [galion-studio/Teglenica-TSO-36](https://github.com/galion-studio/Teglenica-TSO-36). Ovdje je **AI mozak vođenja** koji će se ugraditi u ta plovila.

---

## Status

Koncept / **skica arhitekture**. Nema još ugrađenog hardvera, klasne notacije za autonomiju, ni odobrenja lučke kapetanije. Cilj v1: **posada na mostu** + sustav podrške odlukama (advisory), kasnije nadzirana autonomija uz ROC (Remote Operations Centre).

---

## Svrha (za koga)

| Strana | Što dobiva |
|---|---|
| **Vlada / SDŽ / općine** | Jasniji, sigurniji otpadni lanac otok→kopno uz manje rizika u uskim kanalima |
| **Brodari i brodogradilišta (Split/Trogir)** | Spec senzorskog i računalnog paketa „autonomy-ready, crewed“ |
| **Posada** | Upozorenja na sudar, pomoć pri pristajanju, bolja situacijska svjesnost noću i u magli |
| **Open-source zajednica** | MIT dokumentacija, skice fuzije, put prema otvorenom softveru |

---

## Senzorski stog

| Modalitet | Uloga na Teglenici |
|---|---|
| **LiDAR** | 3D blizina pri pristajanju, luke, pejsani objekti, zona-skeneri na palubi |
| **Vizija** | 360° dnevne + IR kamere; detekcija malih plovila, plivača, plutača, otpada |
| **Akustika** | Hidrofoni / akustički senzori: bliski objekti u magli, upozorenja, nadopuna LiDAR-a/vizije |
| **Fuzija** | Zajednički prostor objekata + AIS/radar (ako postoji na brodu) → savjeti za kurs i manevre |

Detalji: [docs/hr/01-senzorski-stog.md](docs/hr/01-senzorski-stog.md) · [docs/en/01-sensor-stack.md](docs/en/01-sensor-stack.md)

---

## Arhitektura (skica)

```
  LiDAR ─┐
  Kamere ─┼─► fuzija percepcije ─► lokalna mapa ─► savjeti COLREG ─► HMI mosta
  Akustika┘         │                                │
                    └──── brodsko računalo (edge) ───┴──► opcionalno ROC na kopnu
```

Više: [architecture/OVERVIEW.md](architecture/OVERVIEW.md) · [docs/hr/02-fuzija-i-vođenje.md](docs/hr/02-fuzija-i-vođenje.md)

---

## Integracija s Teglenicom

- Nositelj plovila i logistike: **[Teglenica-TSO-36](https://github.com/galion-studio/Teglenica-TSO-36)**
- Galion Marine AI: paket senzora + edge računalo + softver vođenja (ovaj repo)
- Regulativa (HR): start kao oprema na brodu s posadom; smanjena posada / MASS tek kroz službeni pilot

[docs/hr/03-integracija-teglenica.md](docs/hr/03-integracija-teglenica.md)

---

## Dokumenti

| Put | Sadržaj |
|---|---|
| [docs/hr/](docs/hr/) | Hrvatski tehnički tekstovi (primarni) |
| [docs/en/](docs/en/) | English mirrors |
| [architecture/](architecture/) | Dijagrami i slojna skica |
| [sketches/](sketches/) | Bilješke iz prethodnih sesija / praznine |

---

## English summary

**Galion Marine AI** is a concept for an onboard **automatic guidance** stack for **Teglenica TSO-36** waste barges: **LiDAR + vision + acoustic** sensor fusion on an edge computer for assisted / supervised navigation and harbour ops on Dalmatian island–mainland legs. Shipbuilding and waste logistics stay in [Teglenica-TSO-36](https://github.com/galion-studio/Teglenica-TSO-36). This repo is MIT concept docs — not class-approved autonomy.

---

## Licence

[MIT](LICENSE) © 2026 Maciej Grajczyk / Galion Studio
