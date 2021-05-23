Pridavam muj komentar:

- vsechny vyskyty 'Group by' apod. pouzit jiny font? obcas zvyraznena obcas ne?

		Martin: Udelam
		
		Tom: cool
		
		DONE

- napsat proc delat vlastni databazi?

		Martin: Tohle bude v uvodu, mam to v planu
		
		Tom: super

		DONE - v uvodu jsem to popsal

- exekucni plan -> zminit, minamlen jako future work, dela to hodne (zalezi, ktery vertex matchujes jako prvni)

		Martin: Myslis exekucni plan toho prohledavani grafu? Ja myslel ze jsem ten způsob prohledavani popsal v kapitole analyzy sekce "Match" a pak konkretneji v kapitole implementace "Match". Ze vlastne vyhledavani vzoru je spusteno z kazdeho vrcholu grafu.
		Ale muzu pridat nejaky future work, ze ten zpusob prohledavani muye byt nejak jinak. Prakticky jsem to uz vlastne uvedl ve future worku, ale trochu oklikou u 3. odrazky v zaveru.

		Tom: jojo, typicky se exekucnim planem u grafovych/SQL databazi mysli, odkud spoustis prohledavani - napr. prikaz `SELECT COUNT(*) MATCH (x)->(y)->(z) WHERE id(z) = 123` je typicky po parsovani poslan do nejakeho 
		query planneru, ktery se rozhodne nad nejidealnejsi posloupnosti vrcholu/hran, protoze ten vyraz muzes hledat jako (zleva doprava): `(x)->(y)->(z)` nebo `(z)<-(y)<-(x)` atp... Treba v tomhle pripade je idealni 
		zacinat od `(z)`, protoze v grafu bude typicky jen jeden vrchol s `id() = 123` takze ty tim vlastne rychle omezis prohledavany prostor (kdybys pouzil prvni zpusob, muzes az pri poslednim skoku treba zjistit, ze tam zadny vrchol s `id(x) = 123` ani neni. 
		Kazdopadne, tohle je mega veda, je to problem sam o sobe, ale je to dost znamy problem -> zminil bych to jako future work/improvement

		DONE - dopsal jsem to do future work

- slozitost (pamet, cas) u algoritmu

		Martin: Napada me pridat ty casy jen k tomu (a, b) stromu a binarnimu vyhledavani.Jinak uplne nevim jak bych udelal cas k tem samostatnym resenim.

		Tom: no obecne by se hodilo rict, jakou spotrebu pameti to ma -> jestli je to linearni s poctem hran/vrcholu atp... To same pro cas -> nemusi to byt nic exaktniho, proste jen zminit.

		:(

- mozna pridat definice na zacatek,co je graf, vrchol, hrana -> nejak v rychlosti

		Martin: Martin Mareš s Ježkem říkali, že tyhle obecne definice nemusime popisovat.

		Takze DONE 

- expression -> pouzivaji navrhovy vzor composite

		Martin: Udelam
		
		DONE

- ze jsi pouzil zakladni paralelizaci
	  -- future work/improvmenet

		Martin: Tady vubec nevim co konkretne myslis nebo jakou mas predstavu.

		Tom: No, drobet bych to v textu zkusil napsat defenzivneji, s ohledem na paralelizaci -> prvni co kazdeho napadne je: proc tam davate paralelni reseni/benchmark, kterej vlastne teda nakonec nic neukaze, protoze
		jeho bottleneck je na synchronizaci. A tvoje obrana v textu by mela by neco na zpusob: "chteli jsme ukazat zakladni paralelni implementaci a kouknout se na jeho vykonnost, vime, ze to neni idealni, bude to future work, zavery z toho nejde moc vyvozovat, ale aspon vime kde je bottleneck pro para reseni; dulezite vysledky jsou ale videt v singhle thread reseni"


		DONE - dopsal jsem odstavec na konec experimentu group by a dodal to navic jako future work.


- pamet vs. vykon - zminit, proc pamet (na 1 proc dulezitejsi)

		Martin: Stacilo by to nejak obecne v uvodu treba? Nejaky nastrel ze grafy jsou v dnesni dobe velke, proto budeme cilit na mensi pametovou slozitost na ukor rychlosti?

		Tom: No, proste jen nekde v uvodu vysvetlit, proc cilis na pamet a ne vykon -> protoze kdyz mas 1 pocitac (napr notebook), tak to, co te omezuje v pripade tvoji "in-memory" databaze je vzdycky pamet, protoze to maji byt obrovske grafy a jejich zpracovani logicky zabere nejaky cas, ale abys je vubec mohl zacit zpracovavat, tak je nejdriv musis nacist, proto pamet. 

		DONE - dopsal jsem do uvodu kratsi sekci "uprednostneni pameti pred vykonem" proc cilit na pamet.


- vypsat omezeni GB/OB oproti Pgql standardu

		Martin: Ted nevim co myslis. Tu podmnozinu PGQL jsem popsal v uvodu. Jedine omezeni je snad jen ze nepouzivame slozite vyrazy v tech castech. Ale vyrazy ktere jsme vybrali jsem taky popsal v uvodu.

		Tom: tak v GB/OB muzou byt libovolne vyrazy -> otocil bych to a vlozil bych tam vetu, co presne podporujes (pokud to tam uz neni)

		Uz to tam je, vypsal jsem v kapitole 1 na zacatku co presne pouzivame z pgql.
		Vyrazy, agregacni funkce a co se muze zadat v tech dotazech.

		DONE 

- jak reseni ztizi GB + OB dohromady?

		Martin: Jsem to dal jako future work na konci. Ze hlavni problem je trideni podle vzsledku agregacnich funkci, protoze jsou finalni az po dokonceni group by. Ale jestli to ma byt i v textu, tak bych to mohl kratce popsat na konci analyzy.

		Tom: super :) takhle to staci

		DONE
		Udelal jsem to kratce jako future work. 

- jak paralel OB udelat obecne?

		Martin: Nevim co myslis obecne?

		Tom: tyjo, ja uz ted taky ne :/

- nektere sekce obsahuji na zacatku summary, co tam obsahuji (napr. 3.4.1), nektere vubec (3.3.1) -> konzistence

		Martin: Maji to jen sekce z dokumentace implementace aby se v tom lepe orientovalo.
		U zbytku mi to neprislo jako nutnost.
		U dokumentace je ten summary u vsech sekci konzistentni.

		DONE
		Nyni summary maji jen sekce z dokumentace implementace aby clovek vedel k cemu ty samotne tridy patri a z ceho se vychazi :)
		

- je oddeleno dostatecne parsovani Pgql (kdyby to treba nekdo chtel zmenit na nejaky jiny jazyk) -> pripadne, slo by to pouzit jako C# knihovnu pro Pgql jazyk? Zminit kdyztak jako future work a prinos

			Martin: zkusim neco vymyslet.

			om: hodil bych to i jako prinos -> zase otazka muze byt, proc zrovna Pgql (mas to tam nekde napsane? Myslim, ze ne). Na to bych napsal, ze je to jeden z jazyku pro PG graf dotazovani a ze sis to vybral, 
			protoze neni momentalne k dispozici C# implementace, takze by tvuj parser mohl byt ve future work rozsirene a pouzit jako parser. 

			DONE - udelal jsem odstavec ve future work. Proc pgql a ne opecCypher je v uvodu.
			Jinak jsem tam dopsal, ze se to da v budoucnu predelat/rozsirit a pouzit jako parser nebo zmenit ten jazyk.


Implementace:
- je strasne slozite to sledovat, UML/schema by mozna bylo lepsi

		Martin: Premyslel jsem nad tim. Obecne jsem tam popisoval jen hlavni objekty a u tech by to uml obsahovalo snad jen jednu tridu s vyctem, coz mi prislo jako zbytecne. Misty jsem tam sice popsal kratce hierarchii a u te by to asi slo. Pokud bys ale svolil, asi bych to radeji nechal uz takhle a soustredil se na ty obecne veci co si napsal vyse. Nakonec jestli by byl cas, treba bych tam nejake pridal. 

		Tom: jojo, to je jen takove doporuceni ;) Klidne bych to nechal -> pokud by tohle nekdo vytykal u obhajoby -> staci rict, ze UML jde vygenerovat ze trid (nekde ve VS), pripadne, klidne ty UML diagramy muzes i vygenerovat a vlozit do elektronicke prilohy. 
		
		Ale, bylo by tam hezke mit alespon 1 high-level diagram celeho tveho reseni, jako doplnek k textu. 

		Martin: Ted me napadlo, jak si zminil to vygenerovani, ze vlastne uz jsem to jednou zkousel pres doxygen. Takze bych mohl udelat elekronickou prilohu dokumentaci z komentaru kodu + ty diagramy, volaci grafy apod veci doxygen udela automaticky. Jen jestli neni problem, ze ty komentare jsou v anglictine.