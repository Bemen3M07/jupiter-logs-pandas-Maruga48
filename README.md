[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ULiw8LbN)
# PP4

2- Que creieu que és millor mostrar els logs per exemple a la terminal durant
l'execució del programa o bolcar-los en un fitxer de text? Afegiu al readme.md
del repositori aquesta pregunta amb la seva reposta

Avantatges:

Supervisió en temps real: És ideal per a aplicacions en desenvolupament o en proves, ja que permet veure immediatament què està passant.
Facilitat d'accés: No cal buscar fitxers, i els missatges són visibles directament mentre el programa s'executa.
Simples d'implementar: Amb un StreamHandler a sys.stdout es poden veure fàcilment els logs sense configuracions complicades.
Limitacions:

Poc útil per a programes en producció, ja que els missatges es poden perdre si la terminal es tanca.
Dificultat per analitzar grans quantitats de dades o històrics.
Logs en un fitxer de text
Avantatges:

Historial complet: Els fitxers de logs permeten mantenir un registre detallat de tot el que ha succeït, útil per fer auditories o depuracions a llarg termini.
Facilitat d'anàlisi: Es poden aplicar eines com grep, awk o scripts personalitzats per analitzar els logs.
Persistència: Els logs no es perden si el sistema es reinicia o la terminal es tanca.
Limitacions:

No són tan immediats per supervisar en temps real.
Poden ocupar molt espai al disc si no es gestionen correctament amb eines com rotació de logs (log rotation).
Conclusió
L'ideal és fer servir una combinació de tots dos enfocaments:

Mostrar els logs més rellevants (com missatges de nivell INFO o superior) a la terminal durant l'execució, per facilitar el seguiment en temps real.
Bolcar tots els logs (incloent-hi DEBUG) en fitxers de text per garantir que hi ha un registre complet per a anàlisi futura.


3- Omple la següent taula amb expmple, avantantges, i desavantatges de les
següents maneres de fer logs: (inclou-la al readme.md)

### Taula de maneres de fer logs

| **Mètode**                             | **Exemple**                                                                                        | **Avantatges**                                                                                     | **Desavantatges**                                                                                   |
|----------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| **Mostrar logs a la terminal**         | ```python                                                                                          | - Fàcil de veure els logs en temps real durant el desenvolupament i la depuració.                  | - Els logs es perden quan es tanca la terminal o es reinicia el sistema.                             |
|                                        | logging.debug('Missatge de depuració')                                                             | - Útil per a depurar errors immediatament mentre el programa s'executa.                            | - No es conserva cap registre històric.                                                              |
|                                        | logging.info('Missatge informatiu')                                                                | - El codi és senzill i ràpid de configurar.                                                        | - No és adequat per a sistemes en producció.                                                         |
| **Bolcar logs en un fitxer de text**   | ```python                                                                                          | - Els logs es conserven fins que els eliminem, permetent anàlisis posteriors.                      | - No és tan útil per a la depuració en temps real.                                                   |
|                                        | logging.basicConfig(filename='app.log', level=logging.DEBUG)                                       | - Permet la gestió de logs a llarg termini, ideal per a auditories i seguiment.                    | - Pot ocupar molt d'espai si no es gestionen adequadament (rotació de logs).                        |
|                                        | logging.info('Missatge escrit en fitxer')                                                          | - Es poden analitzar més fàcilment utilitzant eines com *grep*, *awk* o scripts personalitzats.     | - Pot ser necessari configurar la rotació o compressió per evitar que els fitxers creixin massa.    |
| **Logs a la base de dades**            | ```python                                                                                          | - Permet guardar els logs de manera centralitzada i facilitar la cerca i consulta d'informació.    | - Pot ser més lent que escriure els logs a un fitxer de text, depenent de la base de dades utilitzada. |
|                                        | logging.basicConfig(filename='logs.db', level=logging.DEBUG)                                       | - Facilita l'anàlisi de grans volums de dades.                                                     | - Requereix més configuració i pot afegir complexitat al sistema.                                   |
|                                        | logging.info('Log escrit a la base de dades')                                                      | - Permet associar logs amb altres dades estructurades dins de la base de dades.                     | - No sempre és necessari i pot ser excessiu per a aplicacions petites o senzilles.                 |
| **Logs a la consola i fitxer simultàniament** | ```python                                                                                          | - Proporciona la visibilitat en temps real (pantalla) i també conserva els logs per a anàlisis posteriors (fitxer). | - Pot ser redundat en alguns casos si els logs es mostren tant a la pantalla com al fitxer.         |
|                                        | logging.basicConfig(filename='app.log', level=logging.DEBUG)                                       | - Ideal per a desenvolupament i entorns de producció on es volen logs visibles i persistents.       | - Pot generar molts logs, augmentant l'ús d'espai d'emmagatzematge si no es gestiona adequadament.  |
|                                        | logging.debug('Missatge a la consola i fitxer')                                                   | - Flexibilitat per configurar diferents nivells de logs per a cada destinació (pantalla i fitxer). | - Necessita més configuració per gestionar diversos *handlers* adequadament.                        |


4- Cerca llibreries de logs en altres llenguatjes (al menys 2, i identifica cóm resolen les següents característiques típiques d’un sistema de logging. Omple la següent taula, i inclou-la al read-me del repositori:


### Taula de comparació de llibreries de logging en diferents llenguatges

| **Característica**                 | **Java (Log4j)**                                                                           | **JavaScript (Winston)**                                                                 |
|------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| **Nivells de logging**             | Log4j suporta múltiples nivells de logging, com ara DEBUG, INFO, WARN, ERROR, FATAL.      | Winston també suporta diversos nivells com DEBUG, INFO, WARN, ERROR.                     |
| **Especificació del nivell de logs** | El nivell es pot configurar tant a nivell de codi com a través del fitxer de configuració (XML o properties). | El nivell es configura per cada `logger` i es pot establir dinàmicament al moment d'executar l'aplicació. |
| **Destinació dels logs**           | Els logs es poden enviar a fitxers, bases de dades, serveis de xarxa, o a la consola.      | Els logs es poden enviar a múltiples destinacions (fitxers, base de dades, consola, HTTP, etc.). |
| **Rotació dels logs**              | Log4j ofereix rotació de logs basada en el temps o en la mida, amb configuració en fitxers. | Winston permet la rotació dels logs mitjançant configuracions personalitzades com a mòdul `winston-daily-rotate-file`. |
| **Format personalitzat**           | El format dels logs es pot personalitzar a través de patrons de configuració.             | Winston ofereix formats personalitzats mitjançant el mòdul `format` (com `json` o `simple` format). |
| **Suport per a múltiples loggers** | Suporta múltiples loggers amb configuracions independents per a cada un.                  | Permet crear múltiples loggers amb diferents configuracions, com ara transports i formats per a cada un. |
| **Persistència de logs**           | Log4j pot escriure els logs en fitxers locals o remots, bases de dades o sistemes de xarxa. | Winston permet escriure els logs a fitxers, bases de dades, o fins i tot a serveis de núvol com AWS. |
| **Interoperabilitat**              | Log4j s'integra bé amb altres tecnologies Java, incloent frameworks com Spring o Hibernate. | Winston s'integra fàcilment amb altres llibreries i aplicacions en Node.js.              |
| **Suport per a logs estructurats**  | Els logs poden ser estructurats (JSON) utilitzant l'add-on `log4j2` per a l'output en JSON. | Winston suporta logs estructurats natius en JSON per defecte.                             |



