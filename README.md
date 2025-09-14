# Laravel + Blade Starter Kit

This is a Dockerised Laravel 12 + Blade starter kit focused for beginner to start explore in developing a web application. Powered with Docker setup to ease the development setup.

## Setup Guide

1. Install Docker Desktop (Windows / Mac) or Docker Engine (Linux).
2. Ensure docker, docker-compose and composer commands work by running below command in terminal

```
docker --version
docker compose version
composer -v
```

3. Git clone this repository

```
git clone https://github.com/nblkmal/larablade-starter-kit.git
```

4. Change directory to project directory `./larablade-starter-kit`
5. Run `cp .env.example .env` -> to initialize the .env
6. Run `./vendor/bin/sail up -d`. You should see something like below :-

```
./vendor/bin/sail up -d

[+] Running 2/2
 ✔ Container mysql             Started                                0.1s 
 ✔ Container laravel.test      Started                                0.1s
 ```

7. Run `./vendor/bin/sail artisan key:generate` -> to set web application APP_KEY
8. Run `./vendor/bin/sail artisan migrate` -> to run database migration
9. Run `./vendor/bin/sail npm install && npm run build` -> to compile frontend assets.
8. Open http://localhost:80 in your browser. Your laravel web app should be accessible


---

## Introduction

Our Laravel 12 + Blade starter kit provides the typical functionality found in the Laravel Starter kits, but with a few key differences:

- A CoreUI/AdminLTE inspired design layout
- Blade + AlpineJS code

This kit aims to fill the gap where there is no simple **Blade only** starter kit available.

Our internal goal at Laravel Daily is to start using this starter kit for our Demo applications, to avoid overwhelming our audience with Vue/Livewire/React if we had used one of the official Laravel 12 starter kits.

**Note:** This is Work in Progress kit, so it will get updates and fixes/features as we go.

## What is Inside?

Inside you will find all the functions that you would expect:

- Authentication
    - Login
    - Registration
    - Password Reset Flow
    - Email Confirmation Flow
- Dashboard Page
- Profile Settings
    - Profile Information Page
    - Password Update Page
    - Appearance Preferences

---

## Design Elements

If you want to see examples of what design elements we have, you can [visit the Wiki](<https://github.com/LaravelDaily/starter-kit/wiki/Design-Examples-(Raw-Files)>) and see the raw HTML files.

---

## Licence

Starter kit is open-sourced software licensed under the MIT license.
