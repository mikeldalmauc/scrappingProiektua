# Scrapping Proiektua

Scrapping proiektua 

Proiektu honen helburua software-sistema bat garatzeko urratsekin familiarizatzea da. Beraz, foku nagusia osagaien instalazioan, konfigurazioan eta konexioan ezarriko da, scrapping aplikazio baten garapenean baino. bigarrena Erabilera komuneko kasu batetik abiatutako testuinguru bat eskaintzeagaitik da, eta gainera, etorkizunean proiektu gehiagotarako balio daiteke.

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

## Redis datu basea ezarri

- [Nola sortu dockerren](https://hub.docker.com/_/redis)

- [Nola erabili javan:](https://redis.io/docs/clients/java/)

## Scrapinerako java libreria

Bilaketa egin huerrengo klaserako
