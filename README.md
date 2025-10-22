# Projekt

V tomto repozitáři chybí složka `node_modules` (to je záměrné — závislosti se instalují lokálně po stažení projektu). Níže jsou přesné příkazy pro uživatele na Windows (PowerShell), aby se mu nainstalovaly potřebné moduly a spustila aplikace.

## Požadavky
- Node.js (doporučeno LTS — např. 16.x nebo 18.x)
- npm (je součástí instalace Node.js)

Zkontrolujte verzi:

```powershell
node -v
npm -v
```

## Instalace závislostí
V kořenovém adresáři projektu spusťte jeden z následujících příkazů.

```powershell
npm install
```

## Spuštění aplikace

Spuštění hlavního Express serveru:

```powershell
npm run start
```

Spuštění WebSocket listeneru (běží samostatně):

```powershell
npm run startWebLis
```

Doporučení: Web server (`npm run start`) a WebSocket listener (`npm run startWebLis`) spouštějte v samostatných terminálech (nebo záložkách terminálu), protože jsou to dva nezávislé procesy.

Po spuštění by mělo být dostupné:
- HTTP: http://localhost:6969 (nastaveno v `index.js`)
- WebSocket: port 42069 (nastaveno v `webListener.js`)

## Poznámka o testovacích klientech a live chatu
- Soubory `index.js` a `index1.js` v tomto repozitáři slouží jako imitace dvou různých klientů. To umožňuje spustit oba (v samostatných terminálech) a testovat, jak si klienti mezi sebou posílají zprávy.
- Pro funkční "live" chat je nutné spustit WebSocket listener (`webListener.js`) pomocí:

```powershell
npm run startWebLis
```

	Web listener přijímá WebSocket připojení na portu 42069 a přeposílá zprávy klientům. Pokud listener neběží, chat bude omezený na statické / HTTP operace bez reálného live chatu.


