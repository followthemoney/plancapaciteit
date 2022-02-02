# Analyse plancapaciteit woningen

In [deze notebook](https://github.com/ftmnl/woningbouw/notebooks/plancapaciteit.ipynb) zetten we cijfers op een rij om de woningbouwplannen van Nederlandse gemeenten in kaart te kunnen brengen. Beschikbare datasets zijn:

1. [Plancapaciteit per gemeente.](https://docs.google.com/spreadsheets/d/1v5jXy01Xfx7tZHE5Wna7StYFtER3Xnus/edit?usp=sharing&ouid=113330074508532941534&rtpof=true&sd=true) Deze dataset is samengesteld door Data Bewijst en bevat enkele mitsen en maren:
* De meeste provincies werken met het onderscheid harde en zachte plannen en hanteren de fasering 2020-2024, 2025-2029, 2030 en verder.
* Limburg hanteert de fasering 2021-2023, 2024 en verder en maakt wel onderscheid in hard en zacht.
* Zuid-Holland gooit alle harde en zachte plannen op een hoop en hanteert 1 fase: 2021-2030
* Groningen maakt onderscheid tussen hard en zacht, maar hanteert de periode 2020-2029
* Drenthe gooit alles op 1 hoop en het is onduidelijk welke periode het hanteert. Daarnaast lijken de cijfers niet te kloppen. Dat wordt nog gechecked.
* Friesland maakt onderscheid tussen hard en zacht, maar geeft voor beide 1 tijdsperiode: 2021-2030.
* Overijssel maakt wel gebruik van de fasering voor harde plannen, maar alle zachte plannen krijgen 1 tijdsfasering, namelijk 2021-2030.
* De gemeente Haaren is in 2021 opgegaan in Vught, Boxtel, Oisterwijk en Tilburg. De vraag is: wat doen we daarmee? Alle vier gemeenten een kwart van Haaren erbij? Waarschijnlijk kunnen we het beste de indeling van 2020 gebruiken.

2. [CBS woningvoorraad per gemeente](https://opendata.cbs.nl/statline/portal.html?_la=nl&_catalog=CBS&tableId=81955NED&_theme=275). Deze data is gebaseerd op de BAG en bestrijkt de periode 2012-2020.

3. Plannen van [De Nieuwe Kaart](https://nieuwekaartnl.nl/). Deze kaart is alleen niet volledig (een aantal provincies ontbreekt), toont gemengde data (polygonen en punten die als polygoon worden weergegeven) en is niet helemaal *up to date* meer. 

## Voor toekomstig onderzoek hebben we nog deze datasets

4. Eigendomsgegevens van de RVO. Dit zijn niet-openbare data. Per perceel wordt het type eigendom gegeven (woningbouwcorporatie, bouw- of projectontwikkelaar, publiek gemeente, publiek rijk, etc.) Deze data zijn van 2019 en een exacte datum ontbreekt, dus we moeten ervan uitgaan dat ze op 1 januari 2019 zijn gemaakt. 

5. Data van de [nieuwbouwmonitor](https://geodienst.xyz/nieuwbouwmonitor/) van de Geodienst van de RUG. Dit is gebaseerd op BAG data en geverifieerd met data van het CBS. Toont de woningbouw per gemeente sinds 2014 en rekent ook de doorlooptijd van vergunning tot oplevering uit. In veel opzichten lijkt deze op de dataset van het CSB.

6. [De Basisregistratie Kadaster](https://www.pdok.nl/introductie/-/article/basisregistratie-kadaster-brk-) voor percelen en kadastrale grenzen. Uit het register zijn mutaties te halen die mogelijk interessant zijn voor de analyse. 