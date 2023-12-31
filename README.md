![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/9b1111dd-6f59-405c-9ae7-e4f558caa2f2)

VERSLAG R0855381 

|Title |Verslag r0855381 |||
| - | - | :- | :- |
|Course |Business Analytics Major |||
|OPO Code ||Author |Amine Moussaif|
|Version |1\.0 |Review ||
|Created on ||Last update |31/08/2023 |

Roken verslag – Amine Moussaif 

1. INTRODUCTIE:

Dit verslag gaat rond roken en de verschillende subonderwerpen hierover. Eerst begon ik met het zoeken van drie bruikbare datasets van verschillende formaat. Na een lange tijd zoeken vond ik alleen csv-datasets die bruikbaar waren. Hierdoor heb ik besloten 2 datasets te converteren naar een xlsx-dataset en naar een txt-dataset. Dit heb ik gedaan met de[ https://convertio.co/ ](https://convertio.co/)tool. Alle files die tot dit verslag behoren zijn te vinden op projektwerkt onder mijn persoonlijke repository

2. DATABRONNEN:
1. Body signals of smoking (csv file) [https://www.kaggle.com/datasets/kukuroo3/body-signal-of- smoking ](https://www.kaggle.com/datasets/kukuroo3/body-signal-of-smoking)
1. Smoking related lung cancer (csv => converted to => xlsx) [https://www.kaggle.com/datasets/raddar/smoking-related- lung-cancers?resource=download ](https://www.kaggle.com/datasets/raddar/smoking-related-lung-cancers?resource=download)
1. Smoking dataset from the UK (csv => converted to => txt) [https://www.openintro.org/data/index.php?data=smoking ](https://www.openintro.org/data/index.php?data=smoking)

3.VRAGEN:

1) Is er een verband tussen roken en een lage bmi hebben?
   ![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/fc4f5bec-fbc8-4163-9dd3-b903a445f681)


Aan de hand van deze scatter plot kunnen we zien dat het bij zowel de rokers en niet rokers gelijk verdeeld is. Dit wilt zeggen dat er geen directe verband is. Ik merkte hier ook op dat de meerderheid van de rokers mannen zijn. ( Aan de hand van model in 4.2) 

2) Kunnen we aan de hand van lichaam signalen voorspellen of iemand rookt ? 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/720372cf-5b01-40fc-9e86-643f135d6a72)


De classification accuracy die de accuraatheid geeft van de predicties is niet vrij hoog maar ook niet laag. Van alle modellen zien we dat neural network het beste presteert met een CA van 71.7. Dit wilt zeggen dat het model 71.7 % van de tijd heeft kunnen voorspellen of iemand rookt of niet. In deze context zou ik zeggen dat dit niet zeer accuraat is maar wel goed. (Aan de hand van model in 4.2) 

3) Roken mensen zonder diploma/opleiding meer dan mensen met diploma/opleiding zoals de stereotype vertelt? 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/38c5e385-ed3d-432e-8092-d8f86d40a9ec)


Op eerste zicht dacht ik dat het inderdaad zo was, omdat je duidelijk kan zien dat 32.69% van de rokers geen diploma/opleiding heeft. Daarna realiseerde ik me dat als je alle opleidingsniveuas samen optelt, je een percentage bekomt van 67.31% wat veel hoger is dan de mensen zonder opleiding. Dit bewijst dus dat in deze studie mensen met een opleiding/qualificatie meer roken dan de mensen zonder. (kijk 4.1) 

4) Kan kNN voorspellen wat een person rookt(packets, hand-rolled or both) aan de hand van inkomen, opleidingsniveua, enz..? 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/5973a6b0-d258-4e24-8c3b-a86e7eccad74)


kNN bekomt een percentage van 71.3% wat in deze context vrij goed is.  (kijk 4.1) 

Ik merkte hier ook op dat mensen met een lager inkomen meer rollen met de hand tegenover de mensen die een hoger inkomen hebben. Deze roken vooral pakjes. (kijk 4.1) 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/ff910ff4-e384-48ef-8a4d-7803c308bc0a)


5) Welke soort mensen heeft stage 2 kanker? 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/0b270ca7-9e13-4d98-b118-48ea662eac2e)
 ![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/f163920a-7890-40a3-86b4-aa557536539b)
 ![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/b27fc58d-6145-4e83-98ec-c57fcbc01658)


Hoge stage 2 longkanker wordt meer gevonden bij blanke mannen die nog steeds roken. Een belangerijke factor die hier natuurlijk speelt is dat deze data is verzameld in amerika en daar is de meerderheid natuurlijk blank dus is het ook logisch dat dit in de distributie blijkt.  

(Kijk naar model 4.3) 

4.1 ETL VOOR DE CSV FILE: 

We beginnen met het inladen van de csv file. Eerst begin ik met het converteren van de age field van string naar integer.  Daarna verwijderen ik de ethnicity kolom omdat deze geen meerwaarde had aan de analyse. Ook heb ik de niet-rokers verwijderd van de dataset omdat ik in mijn onderzoek alleen de rokers wou. Ook verwijder ik de minderjarige omdat ik het verband van inkomen wil vergelijken met wat er gerookt wordt en minderjarigen hebben geen echte inkomen.

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/12cef17d-bdb7-4547-a30b-c101295eba3d)


Daarna sorteren we de rijen op leeftijd en inkomen. Daaruit crëeren we een SQL file ouput die we daarna gebruiken de data in de database te zetten, en een xml file die we kunnen gebruiken in orange om de data te analyseren 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/cffd6c56-c10f-41b3-834a-0e9a5490bece)


4.2 ETL VOOR DE TXT FILE: 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/7553ecfa-04dc-4ddb-8344-2da8aac4f2b3)


Voor de txt bestand ben ik begonnen met de text file input. Hier moest ik de seperator veranderen en de fields handmatig ingeven. Daarna heb ik de values gekozen die ik nodig ging hebben. Hierna zag ik dat de weight en height fields alleen niet veel meerwaarde hadden dus heb ik een nieuwe field gecrëerd die de BMI berekent. Daarna heb ik de rijen gesorteerd op leeftijd en heb ik de data geschreven in een excel file die ik kan gebruiken voor analyse in orange en heb ik ook een sql file output toegevoegd zodat ik de nieuwe data kan toevoegen op de analyse databank. 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/4b769be4-f9f0-4c9f-bebd-91a152e768c0)


4.3 ETL VOOR DE XLSX FILE: 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/5950df53-6bb6-4299-bdc7-a2bc747a8b63)


We beginnen met de microsoft excel input. Daarna heb ik een functie geschreven die de stages van kanker verandert in 0, 1 of 2. Dit is gemakkelijker om straks te analyseren. Ook waren er veel null waardes die ik veranderd heb in een 0. De null values van race heb ik veranderd naar “Other”. Hierna heb ik de kolommen gekozen die ik nodig had en heb ik ook de type van stage\_of\_cancer veranderd naar int omdat deze na de change van null values een string was geworden. Als laatste heb ik een excel writer en een sql output toegevoegd om de data in orange te analyseren en om de data op de analyse database te gooien.  

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/79c5a96b-a36c-4332-8622-3bcfd045277a)


5.DATABANK(DS) 

Local:

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/2e83146f-a6a7-454c-ab54-e6d81fd457e4)


Aan  de  hand  van  de  sql-file  outputs  heb  ik  de  data  op  mijn  local database kunnen zetten en op de school-database . 

52223: 

![image](https://github.com/AmineMousssaif/smoking_paper/assets/71696893/a2cc92fc-8452-4430-8a8b-aca1fc166ca6)


6. CONCLUSIE 

In dit verslag keken we naar verschillende data uit verschillende landen. De dataset van body signals kwam bijvoorbeeld uit Zuid-Korea en die van dataset\_uk kwam van Engeland. Dit was interessant omdat elke land natuurlijk andere statistieken heeft. 

Om de ruwe data te optimaliseren en te verfijnen, hebben we gebruik gemaakt van Pentaho. Binnen dit proces hebben we ETL-methodologie (Extract, Transform, Load) toegepast, wat ons in staat stelde om de ruwe data te transformeren naar verfijnde en schone informatie. De gegenereerde output van Pentaho hebben we vervolgens ingezet voor data-analyse met behulp van het Orange platform.Ik heb ontdekt dat Pentaho een heel handige tool is voor het transformeren van data en het ook de data-analyse vergemakkelijkt.  

Aan de hand van de geanalyseerde data heb ik al mijn vragen kunnen beantwoorden en heb ik veel interessante dingen geleerd over roken op veel verschillende manieren. Eerst leek de opdracht moeilijk en had ik veel moeite met het vinden van nuttige datasets, maar na het vinden van de datasets en het leren werken met Pentaho, werd de opdracht heel leuk en interessant. Deze ervaring heeft me sterk gemotiveerd om in de toekomst verder te gaan met data-analyse. 

