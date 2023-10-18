# Scrapping Proiektua

Scrapping proiektua 

Proiektu honen helburua software-sistema bat garatzeko urratsekin familiarizatzea da. Beraz, foku nagusia osagaien instalazioan, konfigurazioan eta konexioan ezarriko da, scrapping aplikazio baten garapenean baino. bigarrena Erabilera komuneko kasu batetik abiatutako testuinguru bat eskaintzeagaitik da, eta gainera, etorkizunean proiektu gehiagotarako balio daiteke.

- [Scrapping Proiektua](#scrapping-proiektua)
- [Analisi fasea](#analisi-fasea)
- [Garapena](#garapena)
  - [Githuben repositorioa sortu](#githuben-repositorioa-sortu)
  - [Garapen ingurunea sortu](#garapen-ingurunea-sortu)
  - [Java Boilerplate proiektua sortu](#java-boilerplate-proiektua-sortu)
  - [Maven erabiltzen](#maven-erabiltzen)
  - [Redis datu basea ezarri](#redis-datu-basea-ezarri)
    - [Contenedorea sortu](#contenedorea-sortu)
    - [Volumena aztertzen](#volumena-aztertzen)
  - [Java eta redis konektatu](#java-eta-redis-konektatu)
    - [Redis datu basearen helbidea](#redis-datu-basearen-helbidea)
  - [Scrapinerako java libreria](#scrapinerako-java-libreria)


# Analisi fasea
- Klasean adostu da, momentuz denek proiektu bera sortuko dugula irakaslearen gidaz, zailtasuna dela kontuan izanda lan fluxu hau erabiliz sortzen den lehenengo proiektua dela.
- Adostu da java erabiltzea programazioan lantzen den legoaia delak gehien bat, Scrappinerako python egokiagoa izan arren.
- Adostu da java spring-boot erabiltzea proiektu txikiak sortzeko eskeintzen dituen errestasunengaitik.
- Datu base bezala, redis erabiliko bere errazatasunagaitik.
- Docker erabiliko da garapen kontainerizazio plataforma gisa ikasle gustiak istalatuta daukatelako eta portatiletan abiadura handiz maquinan eta aplikazioak sortzen ahalbidetzen duelako, beste batzuen arten.
- Visual estudia erabiliko da dockerrekin integratzen delako eta gaur egun IDE oso ezaguna eta erabilia delako.

# Garapena

## Githuben repositorioa sortu
Sortu repositorio huts bat scrappingProiektua izenarekin githuben

## Garapen ingurunea sortu
Docker eta Visual studio instalatuta izan behar dituzu.

1. Instalatu hurrengo extensioa
<img width="250" alt="image" src="https://github.com/mikeldalmauc/scrappingProiektua/assets/90103384/aa7bd57b-6ee2-4d79-8f33-6ce1ef7fcbd0">

2. Klikatu izkinako botoi urdinean Visual Studioren testuingura aldatzeko, hau da lokaletik makina batera aldatzeko, eta hautatu **New dev container** aukera.
<img width="258" alt="image" src="https://github.com/mikeldalmauc/scrappingProiektua/assets/90103384/76315fd1-ef6d-4f7f-986c-9fe244797f5d">
<img width="562" alt="image" src="https://github.com/mikeldalmauc/scrappingProiektua/assets/90103384/19805a2d-8f24-49e0-8b77-90bac301dc36">

3. Idatzi java eta hautatu irudikoa
<img width="542" alt="image" src="https://github.com/mikeldalmauc/scrappingProiektua/assets/90103384/71fc2f1e-cfab-4721-baf7-c5c36f656976">

Pauso hauek jarraituta garapenerako kontendore bat sortu egingo da java, github eta beste tresna batzuekin. 

4. Klonatu gure github repositorioa sortutako makinak

## Java Boilerplate proiektua sortu

1. Honetarako spring eskeintzen duen [proiektu sortzailea erabiliko dugu.](https://start.spring.io/)

Ezarri huerrengo parametroak erabili eta deskargatu proiektua.
<img width="1405" alt="image" src="https://github.com/mikeldalmauc/scrappingProiektua/assets/90103384/c7269a92-69c9-48b5-b2bc-dc3201d2a20d">

2. Proiektuaren edukia kontenedoreko gure repositorioaren erroan itsatziko dugu.

3. Proiektuarekin datorren java main fitzategia exekutatzen saiatuko gara,

4. Igo aldaketak gitHubera hurrengo komandoak erabiliz.
   
   ```git add --all```
   
   ```git commit -m "lehen commita"```
   
   ```git push```


ikertu [Spring Boot](https://spring.io/projects/spring-boot)

## Maven erabiltzen

Maven dependentzia kudeaketarako programa bat da, javan erabiltzen dena, gure proiektuak maven erabiliko du eta honek hainbat comando eta erabilera ditu. Gure erabilera kasuak oso murriztuak izango dira beraz horiek ikusiko digutu soilik.

1. Maven instalatu: Izan daiteke maven instalatuta ez izatea. Gure proiektuan, **mvnw** eta **mvnw.cmd**(windowserako) izeneko script batzuk daude. Hauek, maven komandoak erabiltzen lagunduko digu, baita gure proiektuak erabiltzen duen bertsioa aurkituko du eta behar dugun mavena deskargatuko du.

    - ```./mvnw spring-boot:run```

2. Maven extensioa ezarri Visual Studion

![Alt text](assets/image.png)

3. Erabili ```Ctr + Shift + P``` eta bilatu eta aukeratu ** maven execute command** , maven **clean**, **install** edo **test** erabiltzeko.

[Zer da maven](https://maven.apache.org/)
[Pom referentzia](https://maven.apache.org/pom.html)

## Redis datu basea ezarri

### Contenedorea sortu
1. Sortu dockerren redis datu base bat huerrengo komandoa erabilita

```docker run --name some-redis -d redis redis-server --save 60 1 --loglevel warning```

Informazio gehiago parametroei buruz, [Nola sortu dockerren](https://hub.docker.com/_/redis)

### Volumena aztertzen

Antzemango duzunez, volumen berri bat sortu da.

![Alt text](assets/image2.png)

Volumen honek **dump.rdb** fitxategi bat besterik ez du izango. Hau, datu basearen kopia bat da eta 60 segundoro eguneratuko da gutxienez aldaketa 1 izan bada, goiko komandoan horrela ezarri baidugu. Fitxategi hau garrantzitsua da datu basea berreskuratu edo gorde nahi izatekotan.

![Alt text](assets/image3.png)

Gure kasuan volumena kontenedoreko **/data** helbidean izango da montatuta, terminalaren bitartez ikusi dezakegu hau:

![Alt text](assets/image4.png)

Hurrengo pausoan, gure java proiektutik redis datu basera konektatzen saiatuko gara

## Java eta redis konektatu

Hurrengo [gida erabiliko dugu](https://redis.io/docs/clients/java/). 

1. Aipatzen den dependentzia ```pom.xml``` fitxategira gehitu
2. Erakusten den kodea ScrappingApplicationTest.java klasean sartu, funtzio berri bat sortuz eta @Tets etiketa erabiliz.
3. Saiatu maven test executatzen goiko atalan azaldu den moduan. Zer gertatzen da?
4. Datu basearen helbide parametroak zuzendu behar ditugu, hurrengo puntuan.

### Redis datu basearen helbidea

Dockerren kontenedoreak sare virtualen bitartez konektatzen dira, hainbat sare mota daude dockerren eta hurrengo hiruilekoeta sakonago ikusiko ditugu, [dockerren sare motak YouTuben](https://youtu.be/bKFMS5C4CG0?si=2JvJv5apL_O3o6f5).

Momentuz jakin dezagun sarerik zehaztu ez dugunez kontenedoreak sortzerakoan, hauen **bridge** edo defektuzko sarean gehitu egin dira:

1. Erabili ```docker network``` agindua ikusteko zer aukera ditugun sareak kudeatzeko.
2. Erabili ```docker network ls``` existitzen diren sareak zerrendatzeko.
3. Erabili azkenik ```docker network inspect bridge``` bridge sarean konektaturiko gailuak ikusteko.

![Alt text](assets/image5.png)

4. Honekin ezagutu dezakegu zein ipv4 helbide erabili beharko dugun javan. Aldatu helbidea eta errepikatu testa, orain zuzena izan beharko litzateke.

## Scrapinerako java libreria

Bilaketa egin huerrengo klaserako
