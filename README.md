# cadre
1. API platform for water polo, and sports in general
2. An application that interacts with the API 

## Prerequisites
- Mac Mojave `10.14.6`
- Docker for Mac `2.2.0.3`
  - Docker Engine `19.03.5`
  - docker-compose `1.25.4`
- Git `2.20.1`

## Software
These are the versions of the major software I used. These are not prerequisites for you to run the app.
- Rails `6.0.3.4`
- Ruby `2.7.2`
- Node `12.19.0`
- sqlite3 `3.27.2` (not currently static)
- yarn `1.22.5` (not currently static)

## Install
```
# copy and paste assuming you have the prerequisites
git clone https://github.com/JacobBHartman/cadre.git
cd cadre
docker-compose build
# docker-compose build --no-cache is slower but better if Dockers image cache interfere
docker-compose up
# go to localhost:8001 in your browser
```
In a separate terminal:
```
docker exec -it $(docker container ls | grep "cadre_ruby" | awk '{print $1}') /bin/bash
```
And then from within the container:
```
./dev/github.sh
# follow the prompt
```

## Purpose
The purposes of this project are to...
1. demonstrate my ability to acquire proficiency in technologies that I haven't worked with before
    - Ruby on Rails
    - A database other than MySQL, so I'll probably go with PostgreSQL and get to touch SQLite
    - Implement my own caching
    - If it makes sense, Vue
2. demonstrate a complete aptitude for the DevOps toolkit including:
    - Jenkins, might switch to Gitlab or something else to learn something new
    - Docker to get it out the door, but will use LXC if I have time and have determined it makes sense
    - Terraform, though I wouldn't mind toying with Pulumi
    - Ansible, I used Saltstack but didn't like it. I previously used Ansible and liked it alot. It seems to be the most popular.
    - Kubernetes, do I need to look into Rancher?
    - Helm, do I need this, how does it help me? This project should help answer those questions.
    - Bash, use best practices for scripting
    - AWS, I risk pigeonholing myself in AWS further but if I want to get frisky I can switch to GCP
    - System design and justification
3. build a project that I've been wanting to build for two years now 

### Topics to add to README
* Configuration
* Database creation
* Database initialization
* How to run the test suite
* Services (job queues, cache servers, search engines, etc.)
* Deployment instructions

### Scope
I define project scope using Github Projects
- MVP, MVP, MVP: Version 0 (local)
- Make External: Version 1
    - The app should be externally available on a working domain name
    - Minimum AWS, Terraform, Docker files, Jenkins. Ansible if necessary
- Mature: Version X
    - Complete API: pools, players, coaches, games, scores, etc.
    - Not water polo specific
    - Example applicaton that looks good and uses the API

### Dev Diary
Located in `/dev/diary`

### To-Do
Handled by Github's Issue Tracking

## Contributers
JacobBHartman
