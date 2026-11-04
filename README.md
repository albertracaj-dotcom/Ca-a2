# Caça2

Aplicació web progressiva (PWA) en català per organitzar l'activitat cinegètica i preparar els exàmens de llicències d'armes D i E.

## Mòduls disponibles

- **Inici:** resum de jornades, observacions i equipament.
- **Mapa:** mapa base OpenStreetMap, localització GPS sota demanda, punts personals guardats, enregistrament de tracks i exportació GPX.
- **Temporada:** cercador per espècie amb una base inicial de 19 espècies i períodes 2026–2027, més enllaços a normativa, espècies, llicències i permisos oficials de la Generalitat. Les restriccions locals i dies puntuals s'han de verificar.
- **Diari de caça:** registre de jornades, modalitat, zona, espècies i notes.
- **Fauna:** registre d'observacions, ubicació i nombre d'exemplars.
- **Meteorologia:** consulta de condicions actuals i previsió de tres dies per població mitjançant Open-Meteo.
- **Equipament:** inventari de material, documentació i dates de revisió.
- **Seguretat:** accés telefònic al 112 i visualització de la ubicació.
- **Exàmens:** simulacres de 423 preguntes en 7 temes, simulacres de 20 preguntes amb 20 minuts, llindar d'apte de 16/20, pràctica per temes, banc de preguntes i revisió d'errors.
- **Configuració:** exportació i importació de còpies de seguretat.

## Publicació amb GitHub Pages

El repositori inclou el workflow `.github/workflows/pages.yml`. Per activar la publicació:

1. Obre **Settings → Pages** al repositori.
2. A **Build and deployment**, selecciona **GitHub Actions**.
3. Desa els canvis. A partir d'aquí, cada actualització a `main` desplega l'aplicació automàticament.

Adreça prevista: https://albertracaj-dotcom.github.io/Ca-a2/

## Instal·lació al mòbil

Obre l'adreça publicada amb Chrome/Edge i utilitza **Instal·la l'aplicació** o **Afegeix a la pantalla d'inici**.

## Dades i privacitat

Les jornades, observacions, equipament, punts GPS i progrés dels exàmens es desen al navegador del dispositiu amb `localStorage`. No hi ha compte d'usuari ni sincronització al núvol. Exporta periòdicament una còpia des de Configuració; la còpia inclou també l'historial i el progrés dels exàmens.

La ubicació només es demana quan l'usuari prem expressament el botó corresponent. No es registra ni s'envia automàticament.

## Funcionament sense connexió

El service worker desa la carcassa de l'aplicació, les dades de temporada i el banc d'exàmens per permetre obrir-los després de la primera càrrega amb connexió. Les dades personals romanen al dispositiu.

El mapa base i les consultes meteorològiques necessiten Internet. Les imatges de mapa no es descarreguen per a ús offline en aquesta versió. El registre GPS requereix que la pantalla de mapa romangui oberta; no es garanteix el seguiment en segon pla.

## Fonts i advertiments

- Temporada, normativa, espècies, llicències i permisos: [Departament d'Agricultura de la Generalitat](https://agricultura.gencat.cat/ca/ambits/medi-natural/casa/).
- Meteorologia: [Open-Meteo](https://open-meteo.com/).
- Cartografia base: [© OpenStreetMap contributors](https://www.openstreetmap.org/copyright).
- El mòdul de preguntes utilitza el banc incorporat al projecte públic [CathalMcDonegal/Apunta-i-Dispara](https://github.com/CathalMcDonegal/Apunta-i-Dispara), concretament el fitxer `official-bank.json`. Es manté la referència a la font del banc original.
- Caça2 és una eina privada d'organització i estudi; no és una aplicació oficial de la Generalitat ni de la Guardia Civil.
- El mapa no conté límits oficials de vedats, zones de seguretat ni delimitacions legals. No s'ha d'utilitzar per decidir si es pot caçar en un lloc concret.
- Els períodes, autoritzacions i restriccions poden canviar. La consulta de les fonts oficials vigents és imprescindible.

## Tecnologia

HTML, CSS i JavaScript sense backend; Leaflet/OpenStreetMap per al mapa; Open-Meteo per a la previsió; PWA amb service worker i emmagatzematge local.
