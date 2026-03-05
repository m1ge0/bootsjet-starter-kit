# Bootsjet Starter Kit

Bootstrap-first Laravel 12 starter kit built on Jetstream (Livewire stack).

## Usage

Requires publication on Packagist (and a stable tag such as `v1.0.0`) for the short package notation:

```bash
laravel new my-project --using=m1ge0/bootsjet-starter-kit
```

Repository URL works immediately (recommended until Packagist publication is active):

```bash
laravel new my-project --using="https://github.com/m1ge0/bootsjet-starter-kit"
```

## Current Scope

- Laravel 12 application skeleton
- Jetstream Livewire + Teams scaffolding
- Bootsjet Bootstrap views/assets applied as first-class project files
- Vite configured for Sass (`resources/sass/app.scss`)
- Livewire constraint prepared for `^3 || ^4` without forced downgrade

## Repository Setup

- Remote uses SSH alias account: `git@github.com-m1ge0:m1ge0/bootsjet-starter-kit.git`
- Migration blueprint is documented in `docs/P3_STARTERKIT_MIGRATION.md`

## Local Validation

```bash
composer validate
npm install
npm run build
php artisan test
```

## P3 Progress

- [x] Scaffolded Laravel 12 starter repository
- [x] Applied Bootsjet stub-to-template mapping
- [x] Updated docs for `laravel new --using=...`
- [x] Added CI workflow for install/build/test smoke checks
- [x] End-to-end validation with Laravel installer (`--using` from GitHub repository URL)

## Clean-Machine Verification Checklist

- [x] `laravel new bootsjet-starter-kit-e2e --using="https://github.com/m1ge0/bootsjet-starter-kit"`
- [x] `composer validate --strict`
- [x] `npm run build`
- [x] `php artisan test`
- [x] No application-level `resources/css/app.css` manifest dependency after scaffold
