Pridavam muj komentar:

- vsechny vyskyty 'Group by' apod. pouzit jiny font? obcas zvyraznena obcas ne?

		Martin: Udelam

		DONE

- napsat proc delat vlastni databazi?

		Martin: Tohle bude v uvodu, mam to v planu

- exekucni plan -> zminit, minamlen jako future work, dela to hodne (zalezi, ktery vertex matchujes jako prvni)

		Martin: Myslis exekucni plan toho prohledavani grafu? Ja myslel ze jsem ten způsob prohledavani popsal v kapitole analyzy sekce "Match" a pak konkretneji v kapitole implementace "Match". Ze vlastne vyhledavani vzoru je spusteno z kazdeho vrcholu grafu.
		Ale muzu pridat nejaky future work, ze ten zpusob prohledavani muye byt nejak jinak. Prakticky jsem to uz vlastne uvedl ve future worku, ale trochu oklikou u 3. odrazky v zaveru.

- slozitost (pamet, cas) u algoritmu

		Martin: Napada me pridat ty casy jen k tomu (a, b) stromu a binarnimu vyhledavani.Jinak uplne nevim jak bych udelal cas k tem samostatnym resenim.

- mozna pridat definice na zacatek,co je graf, vrchol, hrana -> nejak v rychlosti

		Martin: Martin Mareš s Ježkem říkali, že tyhle obecne definice nemusime popisovat.

		Takze DONE 

- expression -> pouzivaji navrhovy vzor composite

		Martin: Udelam
		
		DONE

- ze jsi pouzil zakladni paralelizaci
	  -- future work/improvmenet

		Martin: Tady vubec nevim co konkretne myslis nebo jakou mas predstavu.

- pamet vs. vykon - zminit, proc pamet (na 1 proc dulezitejsi)

		Martin: Stacilo by to nejak obecne v uvodu treba? Nejaky nastrel ze grafy jsou v dnesni dobe velke, proto budeme cilit na mensi pametovou slozitost na ukor rychlosti?

- vypsat omezeni GB/OB oproti Pgql standardu

		Martin: Ted nevim co myslis. Tu podmnozinu PGQL jsem popsal v uvodu. Jedine omezeni je snad jen ze nepouzivame slozite vyrazy v tech castech. Ale vyrazy ktere jsme vybrali jsem taky popsal v uvodu.

- jak reseni ztizi GB + OB dohromady?

		Martin: Jsem to dal jako future work na konci. Ze hlavni problem je trideni podle vzsledku agregacnich funkci, protoze jsou finalni az po dokonceni group by. Ale jestli to ma byt i v textu, tak bych to mohl kratce popsat na konci analyzy.

- jak paralel OB udelat obecne?

		Martin: Nevim co myslis obecne?


- nektere sekce obsahuji na zacatku summary, co tam obsahuji (napr. 3.4.1), nektere vubec (3.3.1) -> konzistence

		Martin: Maji to jen sekce z dokumentace implementace aby se v tom lepe orientovalo.
		U zbytku mi to neprislo jako nutnost.
		U dokumentace je ten summary u vsech sekci konzistentni.

		DONE
		Nyni summary maji jen sekce z dokumentace implementace aby clovek vedel k cemu ty samotne tridy patri a z ceho se vychazi :)
		

- je oddeleno dostatecne parsovani Pgql (kdyby to treba nekdo chtel zmenit na nejaky jiny jazyk) -> pripadne, slo by to pouzit jako C# knihovnu pro Pgql jazyk? Zminit kdyztak jako future work a prinos

			Martin: zkusim neco vymyslet.

Implementace:
- je strasne slozite to sledovat, UML/schema by mozna bylo lepsi

		Martin: Premyslel jsem nad tim. Obecne jsem tam popisoval jen hlavni objekty a u tech by to uml obsahovalo snad jen jednu tridu s vyctem, coz mi prislo jako zbytecne. Misty jsem tam sice popsal kratce hierarchii a u te by to asi slo. Pokud bys ale svolil, asi bych to radeji nechal uz takhle a soustredil se na ty obecne veci co si napsal vyse. Nakonec jestli by byl cas, treba bych tam nejake pridal. 