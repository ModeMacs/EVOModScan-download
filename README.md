# EVOModScan

Strumento **Modbus RTU / TCP** di **Evologic** per test, messa in servizio, diagnostica e registrazione dati,
utilizzabile sia come **Master** sia come **Slave**.

## ⬇ Download

**[Scarica l'ultima versione di EVOModScan.exe](https://github.com/ModeMacs/EVOModScan-download/releases/latest/download/EVOModScan.exe)**

**[Guida alla prova in loopback (PDF)](https://github.com/ModeMacs/EVOModScan-download/releases/latest/download/EVOModScan_Prova_loopback.pdf)**: come provare Master, Slave e Logger su un solo PC senza hardware, con il file di configurazione
[Prova_loopback.evoscan.json](https://github.com/ModeMacs/EVOModScan-download/releases/latest/download/Prova_loopback.evoscan.json) che usa.

Elenco di tutte le versioni: [Releases](https://github.com/ModeMacs/EVOModScan-download/releases)

È un **unico eseguibile portable**: niente installazione, basta copiarlo e avviarlo su qualsiasi
PC Windows 10/11 a 64 bit (il runtime .NET è già incluso). Le impostazioni vengono salvate nel
file `EVOModScan.settings.json` accanto all'eseguibile.

> Al primo avvio Windows SmartScreen potrebbe mostrare "PC protetto da Windows" perché
> l'eseguibile non è firmato digitalmente: clicca **Ulteriori informazioni → Esegui comunque**.

## Funzioni principali

- **Master**: lettura singola, monitor ciclico e scrittura di coil, discrete input, input register
  e holding register (FC01–06, FC15, FC16), su Modbus TCP o RTU (porta seriale).
- **Slave**: simulatore di dispositivo Modbus TCP o RTU con memoria completa; i valori scritti dal
  master compaiono subito in tabella e si possono modificare al volo.
- **Tipi di dato**: BOOL, INT16/UINT16, INT32/UINT32, INT64/UINT64, FLOAT32 (REAL),
  FLOAT64 (LREAL), STRING ASCII; ordine byte AB CD / CD AB / BA DC / DC BA; visualizzazione
  decimale, esadecimale, binaria o ASCII.
- **Logger** (dalla 1.1.0): tag con nome simbolico, unità, commento, scala/offset e deadband sui
  registri Modbus, registrati su uno storico locale (`EVOModScan.history.db` accanto all'exe), con
  grafico di trend ed export CSV pronto per Excel. Le configurazioni dei tag si salvano e si
  ricaricano con un nome (`*.evolog.json`). Dalla 1.2.0 si sceglie la **sorgente**: *Master* registra
  un dispositivo slave interrogato sul bus, *Slave* registra ciò che un master esterno (PLC, SCADA)
  scrive in EVOModScan.
- **Diagnostica**: tutti i frame TX/RX in esadecimale, errori e eccezioni Modbus con descrizione,
  log copiabile e salvabile.
- **Configurazioni** salvabili e ricaricabili (`*.evoscan.json`), una per impianto.

---
© Evologic — questo repository contiene solo i file eseguibili distribuiti.
