# cadre
Current Iteration: An API for water polo plus an application that uses the API

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
3. build a project that I've been wanting to build for two years now 

## (un)measureable, (un)clear Goals
### MVP, MVP, MVP: Version 0 (local)
    - Do as little as possible on the frontend, that's not my focus
    - SQLite > Postgres
    - Go through the RoR tutorial then appropriate for my own use
    - A user should be able to install and run this app locally as easily as possible
    - I have this end-goal for a complete platform that makes accessible through an API: pools, players, coaches, games, scores, etc. but this needs to be narrowed in scope:
    - CRUD and REST games that are played by teams, this is the api. Then I can create a decoupled app that calls the api. This app will show standings. No leagues, no pools, no people.
### Make External: Version 1
    - The app should be externally available on a working domain name
    - Minimum AWS, Terraform, Docker files, Jenkins. Ansible if necessary

## To-Do
Handled by Github's issue tracking

## Install
```
Here goes the script that a user should be able to use to clone and install cadre in 1 go
```

## Dev Diary

### October 21st, 2020
I started this project in order to dockerize a rails app. I've never worked with rails before. It took me a while to figure out how to setup the container. At first I tried installing ruby+rails+node+yarn myself but then decided to use the official ruby 2.7.2 image.

I knew that I wanted to do a much better job of having static versioning. As such I'm using the latest, LTS, and/or most stable versions of software.
- Rails is 6.0
- Ruby is 2.7.2
- Node is 12

It took me about 4 hours of frustration to get this to work. I referenced the Dockerfile best practices page a lot.

I was able to get my localhost to show the default Ruby server page, but I'm curious if I can do this without binding to `0.0.0.0`

If you're going to run `set -o pipefail` in a container, you need to make sure that you're running it with `bash` or another compatible shell.

I prefer to use long-form flags rather than their abbreviated forms for stuff like a Dockerfile or script.

If the Ruby Dockerhub maintainers decide to mess with 2.7.2 it could mess up this app.

I would like to use PostgreSQL because I've never used it before and it would justify creating another container. Then I could easily use RDS or EC2 with postgres since the app is designed to handle postgres.

I tried manually installing sqlite3 but had an issue where sqlite was in the PATH and yes the shell still couldn't find the binary. I had to resort to using apt to install sqlite3. This does not allow sqlite3 to be statically versioned

This app will not end up being a blog but being some sort of sports team management app.
