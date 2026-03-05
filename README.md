# Bootsjet Starter Kit

Bootstrap-first Laravel 12 starter kit built on Jetstream (Livewire stack).

## Usage

```bash
laravel new my-project --using=m1ge0/bootsjet-starter-kit
```

Alternative:

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
- [ ] End-to-end validation on a clean machine with global Laravel installer
