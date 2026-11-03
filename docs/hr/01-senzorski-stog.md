# Senzorski stog — Galion Marine AI

## Cilj
Dati posadi Teglenice pouzdanu **situacijsku sliku** u kanalima Brač–Šolta–Hvar–Vis i pri **pristajanju** u lukama s mješovitim prometom (trajekti, nautičari, kupači u sezoni).

## LiDAR
- Kratki doseg oko pramca/krme i bočnih bokova pri manevaru u luci
- Detekcija mole, bitvi, drugih plovila i plutajućih objekata
- Zona-skeneri na palubi oko kontejnerskih zona (sigurnost ljudi/strojeva)

## Vizija (kamere)
- 360° pokrivenost: dnevne + infracrvene kamere
- Klasifikacija: mala plovila, plivači, plutače, plutajući otpad
- Snimanje za ROC i istrage događaja (zadržavanje prema politici vlasnika)

## Akustika
- Hidrofoni / akustički senzori kao **treći modalitet** kad LiDAR i kamere slabije rade (magla, odsjaj, noć)
- Upozorenja na bliske kontakte i anomalije oko trupa
- Nije zamjena za sonar klase; koncept za fuziju s vizijom/LiDAR-om

## Brodsko računalo
- Edge jedinica (CPU/GPU prema opterećenju modela) s UPS-om
- Lokalna mapa + snimanje telemetrije; veza prema ROC-u kad je mreža dostupna
- Cyber: usklađenost s klasnim zahtjevima (IACS UR E26/E27 — [provjeriti s CRS])

## Vanjske reference (tržište, ne citati cijena)
Komercijalni paketi tipa radar+AIS+kamere+opcioni LiDAR za pristajanje postoje (npr. Kongsberg / Sea Machines / Orca AI klasa). Galion Marine AI dokumentira **otvorenu arhitekturu fuzije** za Teglenicu, ne jednog dobavljača.
