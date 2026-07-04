# 🌍 Osservatorio SGGC

Dashboard di monitoraggio in tempo reale che incrocia due fonti di dati geofisici pubblici — l'indice geomagnetico planetario **Kp** (NOAA SWPC) e l'attività sismica globale **M≥4.5** (USGS) — per verificare, con metodi statistici rigorosi, se esista una correlazione tra attività geomagnetica e terremoti.

🔗 **Demo live:** [sggc-vik.github.io/sggc-app](https://sggc-vik.github.io/sggc-app/)

## Perché questo progetto

L'ipotesi di una correlazione tra tempeste geomagnetiche e terremoti circola da tempo in ambienti non scientifici. Questo progetto nasce per testarla concretamente, con dati reali e un metodo statistico verificabile, invece di basarsi su impressioni o aneddoti.

## Risultato dello studio storico (2000–2026)

**0 correlazioni significative su 186 test statistici**, dopo correzione per test multipli.

Questo risultato (mostrato anche nella dashboard) è coerente con la letteratura scientifica consolidata: non esiste, a oggi, evidenza statistica di una relazione causale tra attività geomagnetica e sismicità.

## Metodologia

- **Correlazione di rango di Spearman** tra indice Kp giornaliero e numero di terremoti M≥4.5
- **Permutation test** (N = 2000) per la significatività
- **Correzione FDR (Benjamini-Hochberg)**, soglia q < 0.05, per il controllo su test multipli
- Analisi ripetuta su diverse finestre di **lag temporale** (da -72h a +72h) per verificare anche eventuali correlazioni ritardate

## Cosa fa la dashboard

- Recupera dati **in tempo reale** da USGS (terremoti) e NOAA SWPC (indice Kp)
- Calcola live la correlazione Spearman, p-value e q-value (FDR) sugli ultimi 30 giorni
- Segnala anomalie statistiche (valori oltre il 75°/90°/95°/99° percentile storico)
- Permette di esplorare i dati con filtri (magnitudo minima, Kp minimo, lag temporale)
- Esporta i dati filtrati in CSV, JSON o l'immagine del grafico in PNG

> **Nota:** il contatore "0/186" nell'interfaccia si riferisce allo studio storico 2000–2026 ed è un valore fisso di riferimento, distinto dall'analisi statistica in tempo reale (correlazione, p-value, FDR) calcolata sui dati delle ultime settimane.

## Fonti dati

- [USGS Earthquake Hazards Program](https://earthquake.usgs.gov/) — feed GeoJSON terremoti M≥4.5
- [NOAA Space Weather Prediction Center](https://www.swpc.noaa.gov/) — indice planetario Kp

## Stack tecnico

HTML/CSS/JavaScript vanilla, [Chart.js](https://www.chartjs.org/) per la visualizzazione, nessuna dipendenza backend — hostato su GitHub Pages.

## Stato del progetto

In sviluppo attivo. È in lavorazione una versione con analisi statistiche più approfondite.

## Licenza

Tutti i diritti riservati

---

Realizzato per curiosità personale e per offrire uno strumento gratuito e trasparente a chi si interessa di geofisica e statistica applicata.
