Opus Knowledgement Base for Uzman Tech projects
===============================================

This images is based in the [Mark Fields's Jenkins and Docker Tutorial](https://github.com/maxfields2000/dockerjenkins_tutorial).

Run with `docker-compose`
-------------------------

Use `docker-compose.yml` to run __Opus__ from ready docker images. It uses:

* [SalahAdDin/jenkins-data](https://hub.docker.com/r//jenkins-data/)
* [SalahAdDin/jenkins-slave](https://hub.docker.com/r//jenkins-slave/)
* [SalahAdDin/jenkins-master](https://hub.docker.com/r//jenkins-master/)
* [SalahAdDin/jenkins-nginx](https://hub.docker.com/r//jenkins-nginx/)

To launch Jenkins in Rancher, use jenkins/rancher_docker-compose.yml.

Build from dockerfiles
----------------------

This Jenkins setup uses four dockerfiles from [SalahAdDin/Opus](https://github.com/SalahAdDin/opus) repository: 
- Jenkins master 
- Jenkins slave 
- Jenkins data volume 
- Jenkins nginx proxy.

If you want to pre install Jenkins plugins list them in jenkins/jenkins-master/plugins.txt

TODO:
- [ ] Change database engine to PostgreSQL.
- [ ] Make a custom nginx container for include `php-fpm` support(exist the confing file) (based from jenkins nginx container).
- [ ] Serve `opus` from nGinx instead `laravel`.
