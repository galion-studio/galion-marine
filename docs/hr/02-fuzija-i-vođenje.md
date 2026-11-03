# Fuzija senzora i logika vođenja (skica)

## Fuzija
1. Sinkronizacija vremenskih oznaka LiDAR / kamera / akustika
2. Detekcija i praćenje objekata po modalitetu
3. Zajednički prostor objekata (track fusion) + AIS ako je dostupan
4. Procjena rizika (udaljenost, CPA/TCPA, klasa objekta)

## Razine (v1 → kasnije)
| Razina | Ponašanje | Status koncepta |
|---|---|---|
| **A — Advisory** | Upozorenja i predloženi manevri; zapovjednik odlučuje | Cilj v1 |
| **B — Nadzirana** | Auto-track na odobrenoj liniji; ROC + most | Pilot (zahtijeva odobrenja) |
| **C — Bez posade** | Nije komercijalna osnova u HR danas | Tek uz nacionalni okvir / MASS |

## COLREG
Savjeti moraju biti usklađeni s pravilima izbjegavanja sudara; v1 **ne** izvršava manevre bez zapovjednika.

## Pristajanje
LiDAR + vizija vode auto-docking **s potvrdom** posade; akustika pomaže pri slaboj vidljivosti.
