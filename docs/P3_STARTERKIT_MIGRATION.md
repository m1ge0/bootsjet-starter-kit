# P3 Starter-Kit Migration Blueprint

## Goal

Transform `m1ge0/bootsjet` from a "swap package" (`bootsjet:swap`) into a Laravel Starter-Kit template that can be installed via:

```bash
laravel new my-project --using=m1ge0/bootsjet-starter-kit
```

This requires shipping a complete project template (application skeleton), not only stubs plus an installer command.

## Target Strategy

- Keep current package line (`bootsjet:swap`) for migration/legacy support.
- Create a Starter-Kit line (recommended as a dedicated template repository/branch).
- Move Bootstrap/Jetstream/Livewire views and assets from `stubs/*` into first-class project files (`resources/*`, `config/*`, etc.).
- Remove runtime swap dependency for new projects.

## Target Template Structure

Minimal target structure for the template repository:

```text
app/
bootstrap/
config/
database/
public/
resources/
  js/
  sass/
  views/
routes/
storage/
tests/
.env.example
artisan
composer.json
package.json
vite.config.js
```

## Mapping: `stubs/*` -> Template Paths

### Root-level files

- `stubs/vite.config.js` -> `vite.config.js`

### Config

- `stubs/config/jetstream.php` -> `config/jetstream.php`

### Public assets

- `stubs/resources/custom.js` -> `public/js/custom.js`

### Frontend source

- `stubs/resources/js/app.js` -> `resources/js/app.js`
- `stubs/resources/js/bootstrap.js` -> `resources/js/bootstrap.js`
- `stubs/resources/sass/app.scss` -> `resources/sass/app.scss`
- `stubs/resources/sass/_custom.scss` -> `resources/sass/_custom.scss`
- `stubs/resources/sass/_variables.scss` -> `resources/sass/_variables.scss`

### Views (all)

- `stubs/resources/views/welcome.blade.php` -> `resources/views/welcome.blade.php`
- `stubs/resources/views/dashboard.blade.php` -> `resources/views/dashboard.blade.php`
- `stubs/resources/views/navigation-menu.blade.php` -> `resources/views/navigation-menu.blade.php`
- `stubs/resources/views/policy.blade.php` -> `resources/views/policy.blade.php`
- `stubs/resources/views/terms.blade.php` -> `resources/views/terms.blade.php`

#### Auth

- `stubs/resources/views/auth/login.blade.php` -> `resources/views/auth/login.blade.php`
- `stubs/resources/views/auth/register.blade.php` -> `resources/views/auth/register.blade.php`
- `stubs/resources/views/auth/forgot-password.blade.php` -> `resources/views/auth/forgot-password.blade.php`
- `stubs/resources/views/auth/reset-password.blade.php` -> `resources/views/auth/reset-password.blade.php`
- `stubs/resources/views/auth/confirm-password.blade.php` -> `resources/views/auth/confirm-password.blade.php`
- `stubs/resources/views/auth/two-factor-challenge.blade.php` -> `resources/views/auth/two-factor-challenge.blade.php`
- `stubs/resources/views/auth/verify-email.blade.php` -> `resources/views/auth/verify-email.blade.php`

#### Layouts

- `stubs/resources/views/layouts/app.blade.php` -> `resources/views/layouts/app.blade.php`
- `stubs/resources/views/layouts/guest.blade.php` -> `resources/views/layouts/guest.blade.php`

#### API

- `stubs/resources/views/api/index.blade.php` -> `resources/views/api/index.blade.php`
- `stubs/resources/views/api/api-token-manager.blade.php` -> `resources/views/api/api-token-manager.blade.php`

#### Profile

- `stubs/resources/views/profile/show.blade.php` -> `resources/views/profile/show.blade.php`
- `stubs/resources/views/profile/update-profile-information-form.blade.php` -> `resources/views/profile/update-profile-information-form.blade.php`
- `stubs/resources/views/profile/update-password-form.blade.php` -> `resources/views/profile/update-password-form.blade.php`
- `stubs/resources/views/profile/two-factor-authentication-form.blade.php` -> `resources/views/profile/two-factor-authentication-form.blade.php`
- `stubs/resources/views/profile/logout-other-browser-sessions-form.blade.php` -> `resources/views/profile/logout-other-browser-sessions-form.blade.php`
- `stubs/resources/views/profile/delete-user-form.blade.php` -> `resources/views/profile/delete-user-form.blade.php`

#### Teams

- `stubs/resources/views/teams/show.blade.php` -> `resources/views/teams/show.blade.php`
- `stubs/resources/views/teams/create.blade.php` -> `resources/views/teams/create.blade.php`
- `stubs/resources/views/teams/create-team-form.blade.php` -> `resources/views/teams/create-team-form.blade.php`
- `stubs/resources/views/teams/update-team-name-form.blade.php` -> `resources/views/teams/update-team-name-form.blade.php`
- `stubs/resources/views/teams/team-member-manager.blade.php` -> `resources/views/teams/team-member-manager.blade.php`
- `stubs/resources/views/teams/delete-team-form.blade.php` -> `resources/views/teams/delete-team-form.blade.php`

#### Components

- `stubs/resources/views/components/action-message.blade.php` -> `resources/views/components/action-message.blade.php`
- `stubs/resources/views/components/action-section.blade.php` -> `resources/views/components/action-section.blade.php`
- `stubs/resources/views/components/application-logo.blade.php` -> `resources/views/components/application-logo.blade.php`
- `stubs/resources/views/components/application-mark.blade.php` -> `resources/views/components/application-mark.blade.php`
- `stubs/resources/views/components/authentication-card.blade.php` -> `resources/views/components/authentication-card.blade.php`
- `stubs/resources/views/components/authentication-card-logo.blade.php` -> `resources/views/components/authentication-card-logo.blade.php`
- `stubs/resources/views/components/banner.blade.php` -> `resources/views/components/banner.blade.php`
- `stubs/resources/views/components/button.blade.php` -> `resources/views/components/button.blade.php`
- `stubs/resources/views/components/checkbox.blade.php` -> `resources/views/components/checkbox.blade.php`
- `stubs/resources/views/components/confirms-password.blade.php` -> `resources/views/components/confirms-password.blade.php`
- `stubs/resources/views/components/confirmation-modal.blade.php` -> `resources/views/components/confirmation-modal.blade.php`
- `stubs/resources/views/components/danger-button.blade.php` -> `resources/views/components/danger-button.blade.php`
- `stubs/resources/views/components/dialog-modal.blade.php` -> `resources/views/components/dialog-modal.blade.php`
- `stubs/resources/views/components/dropdown.blade.php` -> `resources/views/components/dropdown.blade.php`
- `stubs/resources/views/components/dropdown-link.blade.php` -> `resources/views/components/dropdown-link.blade.php`
- `stubs/resources/views/components/form-section.blade.php` -> `resources/views/components/form-section.blade.php`
- `stubs/resources/views/components/input.blade.php` -> `resources/views/components/input.blade.php`
- `stubs/resources/views/components/input-error.blade.php` -> `resources/views/components/input-error.blade.php`
- `stubs/resources/views/components/label.blade.php` -> `resources/views/components/label.blade.php`
- `stubs/resources/views/components/modal.blade.php` -> `resources/views/components/modal.blade.php`
- `stubs/resources/views/components/nav-link.blade.php` -> `resources/views/components/nav-link.blade.php`
- `stubs/resources/views/components/responsive-nav-link.blade.php` -> `resources/views/components/responsive-nav-link.blade.php`
- `stubs/resources/views/components/secondary-button.blade.php` -> `resources/views/components/secondary-button.blade.php`
- `stubs/resources/views/components/section-border.blade.php` -> `resources/views/components/section-border.blade.php`
- `stubs/resources/views/components/section-title.blade.php` -> `resources/views/components/section-title.blade.php`
- `stubs/resources/views/components/switchable-team.blade.php` -> `resources/views/components/switchable-team.blade.php`
- `stubs/resources/views/components/validation-errors.blade.php` -> `resources/views/components/validation-errors.blade.php`
- `stubs/resources/views/components/welcome.blade.php` -> `resources/views/components/welcome.blade.php`

#### Mail

- `stubs/resources/views/emails/team-invitation.blade.php` -> `resources/views/emails/team-invitation.blade.php`

## Package -> Starter-Kit Refactor Scope

The following package runtime files are no longer needed in a pure starter template:

- `src/M1Ge0/Bootsjet/Console/InstallCommand.php`
- `src/M1Ge0/Bootsjet/BootsjetServiceProvider.php`
- `src/M1Ge0/Bootsjet/Bootsjet.php`
- `src/M1Ge0/Bootsjet/BootsjetFacade.php`

For template mode, application state is already "swapped" at project creation time.

## Composer/Dependency Target for Starter-Kit

Starter template `composer.json` should be project-oriented:

- `laravel/framework: ^12.0`
- `laravel/jetstream: ^5.0` (or compatible line used by Laravel 12 template)
- Livewire compatibility (allow `^4.0`; avoid forcing downgrade)
- remove package auto-discovery metadata (`extra.laravel.providers/aliases`) for Bootsjet package classes

## P3 Execution Plan

1. Scaffold starter template repository/branch from Laravel 12 baseline.
2. Apply mapping above (`stubs/*` into real template paths).
3. Remove swap-package runtime classes from starter template.
4. Update docs with `laravel new --using=m1ge0/bootsjet-starter-kit`.
5. Add starter template CI (install + build + tests/smoke).
6. Validate install path end-to-end on a clean machine.

## Definition of Done

- `laravel new my-project --using=m1ge0/bootsjet-starter-kit` produces a ready Bootstrap/Jetstream/Livewire project.
- No `bootsjet:swap` step required.
- Welcome page, auth flow, profile, API tokens, and team screens render correctly.
- Livewire 4 on Laravel 12 remains intact (no downgrade).

## Current Status (March 2026)

- Steps 1-5 are complete in `m1ge0/bootsjet-starter-kit`.
- Step 6 was validated via:
  - `laravel new bootsjet-starter-kit-e2e --using="https://github.com/m1ge0/bootsjet-starter-kit"`
  - `composer validate --strict`
  - `npm run build`
  - `php artisan test`
