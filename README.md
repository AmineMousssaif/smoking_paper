![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.001.png)

VERSLAG R0855381 

|Title |Verslag r0855381 |||
| - | - | :- | :- |
|Course |Business Analytics Major |||
|OPO Code ||Author |Amine Moussaif|
|Version |1\.0 |Review ||
|Created on ||Last update |31/08/2023 |

Roken verslag – Amine Moussaif 

1. INTRODUCTIE: ![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.002.png)

Dit verslag gaat rond roken en de verschillende subonderwerpen hierover. Eerst begon ik met het zoeken van drie bruikbare datasets van verschillende formaat. Na een lange tijd zoeken vond ik alleen csv-datasets die bruikbaar waren. Hierdoor heb ik besloten 2 datasets te converteren naar een xlsx-dataset en naar een txt-dataset. Dit heb ik gedaan met de[ https://convertio.co/ ](https://convertio.co/)tool. Alle files die tot dit verslag behoren zijn te vinden op projektwerkt onder mijn persoonlijke repository

2. DATABRONNEN: ![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.003.png)
1. Body signals of smoking (csv file) [https://www.kaggle.com/datasets/kukuroo3/body-signal-of- smoking ](https://www.kaggle.com/datasets/kukuroo3/body-signal-of-smoking)
1. Smoking related lung cancer (csv => converted to => xlsx) [https://www.kaggle.com/datasets/raddar/smoking-related- lung-cancers?resource=download ](https://www.kaggle.com/datasets/raddar/smoking-related-lung-cancers?resource=download)
1. Smoking dataset from the UK (csv => converted to => txt) [https://www.openintro.org/data/index.php?data=smoking ](https://www.openintro.org/data/index.php?data=smoking)

3\.VRAGEN ![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.004.png)

1) Is er een verband tussen roken en een lage bmi hebben? 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.005.jpeg)

Aan de hand van deze scatter plot kunnen we zien dat het bij zowel de rokers en niet rokers gelijk verdeeld is. Dit wilt zeggen dat er geen directe verband is. Ik merkte hier ook op dat de meerderheid van de rokers mannen zijn. ( Aan de hand van model in 4.2) 

2) Kunnen we aan de hand van lichaam signalen voorspellen of iemand rookt ? 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.006.png)

De classification accuracy die de accuraatheid geeft van de predicties is niet vrij hoog maar ook niet laag. Van alle modellen zien we dat neural network het beste presteert met een CA van 71.7. Dit wilt zeggen dat het model 71.7 % van de tijd heeft kunnen voorspellen of iemand rookt of niet. In deze context zou ik zeggen dat dit niet zeer accuraat is maar wel goed. (Aan de hand van model in 4.2) 

3) Roken mensen zonder diploma/opleiding meer dan mensen met diploma/opleiding zoals de stereotype vertelt? 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.007.jpeg)

Op eerste zicht dacht ik dat het inderdaad zo was, omdat je duidelijk kan zien dat 32.69% van de rokers geen diploma/opleiding heeft. Daarna realiseerde ik me dat als je alle opleidingsniveuas samen optelt, je een percentage bekomt van 67.31% wat veel hoger is dan de mensen zonder opleiding. Dit bewijst dus dat in deze studie mensen met een opleiding/qualificatie meer roken dan de mensen zonder. (kijk 4.1) 

4) Kan kNN voorspellen wat een person rookt(packets, hand-rolled or both) aan de hand van inkomen, opleidingsniveua, enz..? 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.008.png)

kNN bekomt een percentage van 71.3% wat in deze context vrij goed is.  (kijk 4.1) 

Ik merkte hier ook op dat mensen met een lager inkomen meer rollen met de hand tegenover de mensen die een hoger inkomen hebben. Deze roken vooral pakjes. (kijk 4.1) 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.009.jpeg)

5) Welke soort mensen heeft stage 2 kanker? 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.010.png) ![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.011.png) ![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.012.png)

Hoge stage 2 longkanker wordt meer gevonden bij blanke mannen die nog steeds roken. Een belangerijke factor die hier natuurlijk speelt is dat deze data is verzameld in amerika en daar is de meerderheid natuurlijk blank dus is het ook logisch dat dit in de distributie blijkt.  

(Kijk naar model 4.3) 

![ref1] 4.1 ETL VOOR DE CSV FILE: 

We beginnen met het inladen van de csv file. Eerst begin ik met het converteren van de age field van string naar integer.  Daarna verwijderen ik de ethnicity kolom omdat deze geen meerwaarde had aan de analyse. Ook heb ik de niet-rokers verwijderd van de dataset omdat ik in mijn onderzoek alleen de rokers wou. Ook verwijder ik de minderjarige omdat ik het verband van inkomen wil vergelijken met wat er gerookt wordt en minderjarigen hebben geen echte inkomen.

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.014.jpeg)

Daarna sorteren we de rijen op leeftijd en inkomen. Daaruit crëeren we een SQL file ouput die we daarna gebruiken de data in de database te zetten, en een xml file die we kunnen gebruiken in orange om de data te analyseren 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.015.jpeg)

![ref1] 4.2 ETL VOOR DE TXT FILE: 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.016.jpeg)

Voor de txt bestand ben ik begonnen met de text file input. Hier moest ik de seperator veranderen en de fields handmatig ingeven. Daarna heb ik de values gekozen die ik nodig ging hebben. Hierna zag ik dat de weight en height fields alleen niet veel meerwaarde hadden dus heb ik een nieuwe field gecrëerd die de BMI berekent. Daarna heb ik de rijen gesorteerd op leeftijd en heb ik de data geschreven in een excel file die ik kan gebruiken voor analyse in orange en heb ik ook een sql file output toegevoegd zodat ik de nieuwe data kan toevoegen op de analyse databank. 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.017.jpeg)

![ref1] 4.3 ETL VOOR DE XLSX FILE: 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.018.jpeg)

We beginnen met de microsoft excel input. Daarna heb ik een functie geschreven die de stages van kanker verandert in 0, 1 of 2. Dit is gemakkelijker om straks te analyseren. Ook waren er veel null waardes die ik veranderd heb in een 0. De null values van race heb ik veranderd naar “Other”. Hierna heb ik de kolommen gekozen die ik nodig had en heb ik ook de type van stage\_of\_cancer veranderd naar int omdat deze na de change van null values een string was geworden. Als laatste heb ik een excel writer en een sql output toegevoegd om de data in orange te analyseren en om de data op de analyse database te gooien.  

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.019.jpeg)

![ref1] 5.DATABANK(DS) 

Local:

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.020.jpeg)

Aan  de  hand  van  de  sql-file  outputs  heb  ik  de  data  op  mijn  local database kunnen zetten en op de school-database . 

52223: 

![](Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.021.jpeg)

![ref1] 6. CONCLUSIE 

In dit verslag keken we naar verschillende data uit verschillende landen. De dataset van body signals kwam bijvoorbeeld uit Zuid-Korea en die van dataset\_uk kwam van Engeland. Dit was interessant omdat elke land natuurlijk andere statistieken heeft. 

Om de ruwe data te optimaliseren en te verfijnen, hebben we gebruik gemaakt van Pentaho. Binnen dit proces hebben we ETL-methodologie (Extract, Transform, Load) toegepast, wat ons in staat stelde om de ruwe data te transformeren naar verfijnde en schone informatie. De gegenereerde output van Pentaho hebben we vervolgens ingezet voor data-analyse met behulp van het Orange platform.Ik heb ontdekt dat Pentaho een heel handige tool is voor het transformeren van data en het ook de data-analyse vergemakkelijkt.  

Aan de hand van de geanalyseerde data heb ik al mijn vragen kunnen beantwoorden en heb ik veel interessante dingen geleerd over roken op veel verschillende manieren. Eerst leek de opdracht moeilijk en had ik veel moeite met het vinden van nuttige datasets, maar na het vinden van de datasets en het leren werken met Pentaho, werd de opdracht heel leuk en interessant. Deze ervaring heeft me sterk gemotiveerd om in de toekomst verder te gaan met data-analyse. 

[ref1]: Aspose.Words.1635f41a-c764-4215-88f3-fd7476c2f449.013.png
