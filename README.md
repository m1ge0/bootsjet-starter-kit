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

