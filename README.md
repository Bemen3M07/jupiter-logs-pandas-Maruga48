[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ULiw8LbN)
# Empty

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


