# SimSim Simulation

En resurshanterings- och befolkningssimulering byggd i Python.

## Översikt
SimSim simulerar ett ekonomiskt ekosystem där arbetare bor i baracker, konsumerar mat och produkter, och arbetar i olika byggnader (fabriker, gårdar, matställen, hem) för att upprätthålla kolonins tillväxt och stabilitet.

## Funktioner
- **Objektorienterad Design**: Separata klasser för Arbetare, Resurser och Byggnader.
- **Resurslivscykel**: Produktion och konsumtion av mat och produkter.
- **Arbetarnas Vitalitet**: Arbetare kan skadas eller läkas baserat på deras miljö och konsumtion.
- **Datapersistens**: Automatisk loggning av varje simuleringssteg till en SQLite-databas (`SIMSIMDATABASE.db`).
- **Dataanalys**: 
  - Exporterar simuleringshistorik till Excel (`simulation_data.xlsx`).
  - Genererar en graf över resurstrender över tid med Matplotlib.
- **Hantering av Stagnation**: Automatiserade ingripanden för att lägga till resurser eller ändra balansen om simuleringen kör fast.

## Krav
- Python 3.x
- `pandas`
- `matplotlib`
- `openpyxl`
- `sqlite3` (inbyggd)

## Installation
```bash
pip install pandas matplotlib openpyxl
```

## Användning
Kör simuleringsskriptet:
```bash
python simsim.py
```
Simuleringen körs i upp till 900 steg eller tills arbetare/produkter tar slut. När den är klar visas en graf och data sparas till Excel.

## Byggnadstyper
- **Factory (Fabrik)**: Producerar produkter, kostar arbetarens vitalitet.
- **Farm (Gård)**: Producerar mat.
- **Foodcourt (Matställe)**: Bearbetar mat för att läka arbetare.
- **Home (Hem)**: Använder produkter och arbetare för att skapa nya arbetare (befolkningstillväxt).
