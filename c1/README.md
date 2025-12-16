- CE1.1 Identificar els components físics d'un sistema informàtic fent servir esquemes funcionals.
- CE1.2 Descriure les funcions de la unitat central de procés utilitzant diagrames.
- CE1.3 Explicar les funcions i les característiques dels perifèrics localitzant-ne els mitjans de connexió amb el sistema informàtic i el tipus de consumible que utilitza.
- CE1.4 Descriure les funcions i les característiques de les unitats d'emmagatzematge i assenyalar els suports corresponents.
- CE1.5 Descriure els procediments d'arrencada i aturada de l'equip informàtic i dels seus perifèrics i identificar els problemes que poden sorgir en aquests procediments.



## 1.1 El sistema informàtic
- Definició: conjunt de maquinari, programari i personal per emmagatzemar i processar informació automàticament.
- Maquinari (físic): 
  - Intern: placa base, CPU, memòria principal, refrigeració, font d’alimentació, discs, targetes d’expansió.
  - Extern (perifèrics): monitor, teclat/ratolí, àudio, impressora/escàner, emmagatzematge extern, dispositius especialitzats (VR, lectors, gamepads).
- Programari:
  - Base/de sistema: SO, controladors, microprogramari (BIOS/UEFI) habitualment en ROM/EPROM/EEPROM.
  - Aplicació: horitzontal (genèric, ex. ofimàtica) i vertical (a mida per sector). Firmware integra lògica al maquinari.
- Programari base: drivers per E/S, firmware d’arrencada i gestió d’energia, SO com a gestor central de recursos.
- Classificació per mida/recursos: supercomputador, mainframe, minicomputador, microcomputador (PC/portàtil), sistemes integrats i mòbils (IoT, wearables).
- Exemples ràpids: supercomputador (HPC), mainframe (banca), PC (ofimàtica), smartphone (ús personal), microcontrolador en rentadora (control dedicat).
- Taula resum (mida/ús):

| Tipus | Recursos típics | Ús habitual |
| --- | --- | --- |
| Supercomputador | Milers de CPU/GPU, interconnexió d’alta velocitat | Simulació científica, IA gran escala |
| Mainframe | Alta E/S, redundància, gran RAM | Transaccions bancàries, facturació |
| Minicomputador | Potent però compacte | Servei a departaments/empreses |
| Microcomputador | 1–2 CPU, RAM moderada | PC, portàtil, estació personal |
| Integrat/Mòbil | SoC baix consum | IoT, mòbil, wearables |

- Exercicis proposats: 
  1) Enumera tres perifèrics d’entrada i tres de sortida. 
  2) Dóna un cas d’ús per a cada categoria (supercomputador, mainframe, PC, mòbil, embegut).
- Solucions breus: (1) Entrada: teclat, escàner, càmera. Sortida: monitor, impressora, altaveus. (2) Ex.: simulació clima, core bancari, ofimàtica, missatgeria mòbil, sensor ambiental.

## 1.2 Representació de la informació
- El maquinari treballa amb lògica binària (0/1). Bit = unitat mínima.
- Tipus de dades: numèriques, alfabètiques, alfanumèriques. Cal codificar-les per ser interpretables per circuits.
- Teorema fonamental de la numeració: $N = \sum_{i=0}^{k} d_i \cdot b^i$.
- Sistemes de numeració: 
  - Decimal (base 10), Binari (base 2), Octal (base 8), Hexadecimal (base 16 amb A–F).
  - Combinacions possibles: $\text{valors} = 2^{\text{bits}}$; 1 byte = 8 bits; 1 nibble = 4 bits.
  - Canvis de base: divisió successiva (decimal → altra base) i suma de potències (altra base → decimal).
- Exemple de conversió: 75(10) → binari: divisions per 2 donen residus 1 1 0 1 0 0 1 (invertint → 1001011(2)). A hexadecimal: 75 / 16 = 4, residu 11 (B) → 4B(16).
- Codis d’entrada/sortida: ASCII (7 bits, 128 caràcters), ASCII estès (8 bits, ISO-8859-x), EBCDIC (8 bits), Unicode (punts de codi; UTF-8/16/32) per suport multillenguatge.
- Representació interna: 
  - Coherència d’arquitectura (8/16/32/64 bits). Paraula = mida del bloc de dades del processador.
  - Nombres sense signe: rang $0 .. 2^n - 1$. Amb signe: bit de signe reservat.
  - Mètodes de signe: mòdul i signe, complement a 1, complement a 2 (habitual), excés $2^{n-1}$.
- Taula ràpida de codis i bases (0–15):

| Decimal | Binari | Octal | Hex |
| --- | --- | --- | --- |
| 0 | 0000 | 0 | 0 |
| 1 | 0001 | 1 | 1 |
| 2 | 0010 | 2 | 2 |
| 3 | 0011 | 3 | 3 |
| 4 | 0100 | 4 | 4 |
| 5 | 0101 | 5 | 5 |
| 6 | 0110 | 6 | 6 |
| 7 | 0111 | 7 | 7 |
| 8 | 1000 | 10 | 8 |
| 9 | 1001 | 11 | 9 |
| 10 | 1010 | 12 | A |
| 11 | 1011 | 13 | B |
| 12 | 1100 | 14 | C |
| 13 | 1101 | 15 | D |
| 14 | 1110 | 16 | E |
| 15 | 1111 | 17 | F |

- Exercicis ràpids: 
  1) Converteix 113(8) a decimal i binari. 
  2) Escriu el rang d’un enter amb signe en C2 amb paraula de 16 bits. 
  3) Calcula quants caràcters pot codificar un sistema de 10 bits.
- Solucions breus: 
  1) 113(8) = $1\cdot8^2+1\cdot8^1+3=64+8+3=75$(10) = 1001011(2). 
  2) C2, 16 bits: rang $-2^{15}$ a $2^{15}-1$ → -32768 a 32767. 
  3) $2^{10}=1024$ caràcters.
- Mesura de la informació:
  - Bit (b) = unitat mínima ($2$ estats). Byte (B) = 8 bits. 
  - Prefixos SI (decimal): k, M, G, T… ($10^3,10^6,10^9,10^{12}$). Prefixos IEC (binaris): Ki, Mi, Gi, Ti… ($2^{10},2^{20},2^{30},2^{40}$).
  - Taula ràpida:

| Nom | Símbol SI | Valor SI | Símbol IEC | Valor IEC |
| --- | --- | --- | --- | --- |
| kilobyte | kB | $10^3$ | KiB | $2^{10}$ |
| megabyte | MB | $10^6$ | MiB | $2^{20}$ |
| gigabyte | GB | $10^9$ | GiB | $2^{30}$ |
| terabyte | TB | $10^{12}$ | TiB | $2^{40}$ |

  - Exemple: disc de 250 GB comercials → bytes = $250 \times 10^9$. En GiB: $\dfrac{250\times10^9}{2^{30}} \approx 232\ \text{GiB}$ (d’aquí la diferència mostrada pel SO).
  - Exercicis: 
    1) Converteix 16 GiB a GB. 
    2) Quants bytes té 512 MiB? 
  - Solucions: 
    1) $16\,\text{GiB} \times \dfrac{2^{30}}{10^9} \approx 17{,}18\,\text{GB}$. 
    2) $512\,\text{MiB} = 512 \times 2^{20} \text{ bytes} \approx 536.870.912$ bytes.

## 1.3 El sistema operatiu
- Definició: programari base que ofereix interfície a usuaris/aplicacions i gestiona recursos de maquinari.
- Funcions clau: donar API/interfície (CLI/GUI), planificar recursos, protegir i monitorar el sistema.
- Elements: processos i espai d’adreces, sistema d’arxius, gestió E/S, protecció, shell i GUI.
- Estructures: monolític (nucli únic ràpid), capes (nivells de privilegi), micronucli (serveis fora del nucli), client-servidor (processos servei/client), virtuals (capa de virtualització), exonuclis (particions de recursos a màquines virtuals).
- Classificació: 
  - Usuaris: monousuari vs multiusuari. 
  - Tasques: monotasca vs multitasca (preemptiva o no). 
  - Processadors: mono vs multiprocessador. 
  - Propòsit: general vs especialitzat. 
  - Llicència: propietari vs lliure.
- Taula ràpida de classificació:

| Criteri | Opcions | Exemple |
| --- | --- | --- |
| Usuaris | Monousuari / Multiusuari | MS-DOS / GNU/Linux |
| Tasques | Monotasca / Multitasca | MS-DOS / Windows 11 |
| Processadors | Mono / Multi | Windows 9x / macOS |
| Propòsit | General / Especial | Windows, Linux / webOS TV |
| Llicència | Propietari / Lliure | Windows / Debian |

- Evolució (fites): màquina analítica (Babbage/Lovelace) → tubs de buit (ENIAC) → targetes perforades i processament per lots → transistors/mainframes (OS/360, multiprogramació, spooling) → minicomputadors (PDP, naixement UNIX) → microordinadors i PC (CP/M, MS-DOS, GUI Mac/Windows) → Linux (1991) i triada actual (Windows, macOS, GNU/Linux) → mòbil (Symbian, iOS, Android) i convergència dispositiu-escriptori.
- Exercicis: 
  1) Indica dos avantatges i dos inconvenients d’un nucli monolític versus micronucli. 
  2) Classifica: Android, Windows 11, mainframe z/OS, i un firmware d’una impressora.
- Solucions breus: 
  1) Monolític avantatge: rendiment alt, menys canvi de context; inconvenient: difícil d’aïllar errors, més gran. Micronucli avantatge: modularitat i fiabilitat; inconvenient: més missatgeria entre processos i potencial cost de rendiment. 
  2) Android: multiusuari, multitasca, multiprocessador, propòsit general, lliure (nucli). Windows 11: multiusuari, multitasca preemptiva, multiprocessador, propòsit general, propietari. z/OS: multiusuari, multitasca, multiprocessador, propòsit especial (transaccions), propietari. Firmware impressora: monousuari, monotasca, monoprocessador, especial, propietari.

## 1.4 Funcions del sistema operatiu
- Objectius: facilitar l’ús, monitorar i protegir, i gestionar recursos (CPU, memòria, E/S, emmagatzematge).

### 1.4.1 Gestió d’arxius
- Arxiu: conjunt lògic de dades; directori: agrupació jeràrquica de fitxers/directoris. Rutes absolutes vs relatives; entrades especials “.” (directori actual) i “..” (pare).
- Funcions: gestió de noms/rutes, permisos i atributs, accés simultani (bloqueig), assignació d’espai, maneig d’errors i consistència (diaris/logs, llista de blocs defectuosos).
- Estratègies d’assignació d’espai: contigua (ràpida, fragmenta), encadenada (menys fragmentació, accés seqüencial), indexada (índex separat; flexible).
- Exercicis: 
  1) Dissenya una jerarquia simple per a un projecte (arrel, src, docs, data). 
  2) Explica un cas on el bloqueig d’arxiu evita corrupció.
- Solucions breus: 
  1) Exemple: /projecte → /src (codi), /docs (manual), /data (fitxers entrada), /out (resultats). 
  2) Quan dues aplicacions editen el mateix full de càlcul, el bloqueig evita que se sobreescriguin dades inconsistents.

### 1.4.2 Gestió de la memòria
- Jerarquia: registres → memòria cau → RAM → emmagatzematge secundari (temps d’accés creixent, cost/bit decreixent).
- Funcions: assignar memòria a processos, alliberar/compactar, controlar concurrència, moure programes entre memòria principal i secundària.
- Tècniques: monitor resident/particions fixes, swapping (intercanvi amb disc), paginació (pàgines/marcs de mida fixa), segmentació (blocs lògics variables), combinacions segment-pàgina, enllaç dinàmic (DLL compartides), memòria virtual (carregar a demanda; fragments a disc).
- Exemple: en paginació amb pàgines de 4 KiB, un binari de 18 KiB necessita 5 pàgines; marcs lliures no cal que siguin contigus.
- Exercicis: 
  1) Calcula quantes pàgines de 8 KiB calen per a un procés de 50 KiB. 
  2) Diferencia swapping vs memòria virtual en una frase cadascun.
- Solucions breus: 
  1) $\lceil 50 / 8 \rceil = 7$ pàgines. 
  2) Swapping: mou el procés complet entre RAM i disc. Memòria virtual: carrega només les parts necessàries (pàgines/segments) a demanda.

### 1.4.3 Gestió de processos
- Procés = programa en execució + context (registres, dades, espai d’adreces). PCB guarda identificador, estat, ús de recursos, context.
- Estats (model de 5): Nou → Preparat → Execució → (Bloquejat ↔ Preparat) → Finalitzat.
- Planificació: 
  - No expulsores: FCFS, SJF, Prioritats (amb ajust dinàmic per evitar inanició). 
  - Expulsores: SRT (preemptiu de SJF), RR (quàntum temporal).
- Exemple: en RR amb quàntum de 50 ms i 3 processos, cada torn interromp l’actual per donar CPU al següent, assegurant resposta interactiva.
- Exercicis: 
  1) Dóna un avantatge de SJF i un problema potencial. 
  2) Què passa si el quàntum de RR és massa gran? I si és massa petit?
- Solucions breus: 
  1) Avantatge SJF: minimitza temps d’espera mitjà; problema: estimar durada i risc d’inanició de tasques llargues. 
  2) Quàntum massa gran: es comporta com FCFS i baixa interactivitat. Massa petit: massa canvis de context i sobrecost.

### 1.4.4 Gestió d’entrada/sortida
- Dispositius E/S: entrada (teclat, escàner), sortida (monitor, impressora), mixtos (discos, xarxa). Diferencien unitat de transferència (caràcter vs bloc), velocitat i protocol de bus.
- Controladors (drivers) com a interfície estandarditzada entre SO i dispositiu; operen habitualment al nucli.
- Modes de transferència: programada (CPU espera), per interrupcions (CPU notificat al final), DMA (dispositiu accedeix a RAM sense CPU).
- Spooling/buffers per desacoblar velocitats; magatzem simple, doble o circular segons concurrència de transferències.
- Exercicis: 
  1) Indica un cas on DMA millora el rendiment. 
  2) Per què les impressores utilitzen spooler?
- Solucions breus: 
  1) En transferir blocs grans de disc a RAM, DMA evita saturar la CPU amb interrupcions contínues. 
  2) Perquè l’aplicació allibera CPU ràpidament escrivint al buffer, i la impressora (lenta) buida la cua al seu ritme.
