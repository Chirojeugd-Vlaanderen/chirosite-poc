This is a test-case for running a local D8 site through docker. 
This contains a docker image, and the necessary files to install a
local environment. 

Pre-requisites:
Install docker

Installation:
* Clone repository
* Install containers with docker-compose up -d
* Login to php container docker-compose exec --user 82 php drush
* Run composer install to get drupal / contrib and other libraries
* Access site at http://localhost:8000/
