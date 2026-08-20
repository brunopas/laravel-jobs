# LaraJobs

Job board for posting and browsing Laravel job listings with company logos. Study project from the [Laravel From Scratch 2022](https://www.youtube.com/watch?v=MYyJ4PuL4pY) course by Traversy Media.

## Features

- Browse job listings with tag filtering and keyword search
- Create, edit, and delete your own listings
- Upload a company logo for each listing
- Register, log in, and manage your listings from a dashboard
- Database seeder with sample listings and fictional companies

## Tech stack

- **Runtime:** PHP 8, Laravel 9
- **Views:** Blade components, Tailwind CSS (CDN), Alpine.js (CDN)
- **Database:** MySQL via Eloquent
- **Uploads:** Logo files stored in `storage/app/public`
- **Dev tools:** Laravel Pint, Clockwork

See [composer.json](./composer.json) and [package.json](./package.json) for full dependency lists.

## Requirements

- [PHP](https://www.php.net/) >= 8.0.2 with required extensions
- [Composer](https://getcomposer.org/)
- [Git](https://git-scm.com/)
- [MySQL](https://www.mysql.com/) (or change the driver in `config/database.php`)

## Environment variables

Copy `.env.example` to `.env` and fill in the values below.

| Variable | Required | Default |
| --- | --- | --- |
| `DB_DATABASE` | Yes | `laravel_jobs` |
| `DB_USERNAME` | Yes | `root` |
| `DB_PASSWORD` | Yes | — |

All other variables use sensible Laravel defaults for local development.

## Getting started

```bash
git clone https://github.com/brunopas/laravel-jobs.git
cd laravel-jobs

composer install
cp .env.example .env
php artisan key:generate
```

Create a MySQL database called `laravel_jobs` (or whatever you set in `DB_DATABASE`), then:

```bash
php artisan migrate --seed
php artisan storage:link
php artisan serve
```

Open [http://localhost:8000](http://localhost:8000).

The seeder creates an admin user (`admin@larajobs.com` / `password`) and sample job listings with logos.

## Scripts

| Command | What it does |
| --- | --- |
| `php artisan serve` | Start the development server |
| `php artisan migrate --seed` | Run migrations and seed the database |
| `php artisan storage:link` | Symlink `storage/app/public` to `public/storage` |

## Project structure

```text
laravel-jobs/
├── app/
│   ├── Http/Controllers/   # ListingController, UserController
│   └── Models/              # User, Listing
├── config/                  # Laravel config files
├── database/
│   ├── factories/           # Listing and User factories
│   ├── migrations/          # Schema migrations
│   └── seeders/             # DatabaseSeeder
├── lang/en/                 # English validation and auth messages
├── public/                  # Static assets, logos, favicon
├── resources/views/         # Blade templates (listings, users, components)
├── routes/                  # web.php
└── tests/                   # PHPUnit tests
```

## License

MIT. See [LICENSE](./LICENSE).
