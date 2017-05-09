Opus Knowledgement Base for Uzman Tech projects
===============================================


Run with `docker-compose`
-------------------------

Use `docker-compose.yml` to run __Opus__ from ready docker images. It uses:

* [SalahAdDin/opus-master](https://hub.docker.com/r//opus-master/)
* [SalahAdDin/opus-nginx](https://hub.docker.com/r//opus-nginx/)

Build from dockerfiles
----------------------

This Jenkins setup uses four dockerfiles from [SalahAdDin/Opus](https://github.com/SalahAdDin/opus) repository: 
- Opus master
- Opus nginx proxy


TODO:
- [ ] Change database engine to PostgreSQL.
- [ ] Make a custom nginx container for include `php-fpm` support(exist the confing file) (based from jenkins nginx container). https://medium.com/@shakyShane/laravel-docker-part-1-setup-for-development-e3daaefaf3c
- [ ] Serve `opus` from nGinx instead `laravel`. 
