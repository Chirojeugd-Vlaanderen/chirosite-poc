# Chirosite POC

Dit is een proof-of-concept opzet om te kijken hoe we de chirosite 
zouden kunnen opzetten met alle mogelijke nieuwe tools. 

## Doel

Het doel is om voor iedereen een snelle lokale makkelijke setup te 
voorzien. Cross-platform dus zowel op Linux / Mac OS / Windows. 

Anderzijds willen we ook alle mogelijke tools gebruiken, zonder dat we
hiervoor de drempel naar een lokale setup nog meer verhogen. 

## Oplossing

Deze setup wrapt een docker omgeving rond de eigenlijke chirosite-code. 
Op deze manier zijn omgeving en site gebundeld. Enerzijds hebben we 
een aantal docker-bestanden die voor de setup zorgen, anderzijds hebben
we ook een aantal bestanden die zorgen voor de drupal / chirosite installatie.

## Installatie

### Vereisten

Installeer docker. Docker is beschikbaar voor linux / mac / windows. 
Voor mac en niet de allernieuwste windows (< Win 10) is het beter te 
gaan voor de docker toolbox. Native docker voor mac is nogal traag
met zijn filesynch, iets wat drupal nogal intensief gebruikt. 

Maak een github account, zet je key correct op, en clone deze repository.

### Installatie

* Clone repository

#### Initializeer omgeving

* Install containers with `docker-compose up -d`
* Login to php container `docker-compose exec --user 82 php sh`

#### Composer

Deze D8 code-base is opgezet via composer. Dat wil zeggen dat we al onze
dependant code niet in de repo hebben gecommit, maar dat we die afzonderlijk
downloaden via composer. In de docker php container is composer mee geinstalleerd.

* Run composer install``

#### Installeer drupal met de huidige config.

Eens we alle code hebben gedownload, en alle dependencies is onze site
beschikbaar op http://localhost:8000/ (of via de docker-toolbox). 
Nu kunnen we de deze installeren. Doorloop de drupal installatie, en 
kies voor configuration profiel installatie. De database bevindt zich op
`host: mariadb`, `user/pass/db: drupal/drupal/drupal` Als config 
directory kies je voor  `/var/www/html/www/config` Op die manier 
installeer je alle config correct mee, en installeer je dus geen 
standaard drupal, maar de chirosite. 

Deze installatie is gelukkig maar 1 malig, want duurt een tijdje. 
