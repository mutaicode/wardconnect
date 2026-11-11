# chemosot-ward

# WardConnect — Chemoot Ward Digital Service Portal

A web-based community information and administrative service management
system for Chemoot Ward, Kericho County, Kenya.

- **Stack:** PHP 8.2+ · MySQL 8 · Tailwind CSS · PDO
- **Status:** In development (v0.x)

## Local setup

**Prerequisites:** PHP 8.2+, Composer, MySQL 8.

```bash
git clone <repo-url> wardconnect
cd wardconnect

cp .env.example .env
# edit .env with your local DB credentials

composer install

# create the database and user in MySQL first, then:
mysql -u root -p wardconnect < database/migrations/001_*.sql
mysql -u root -p wardconnect < database/seeders/villages.sql

composer serve   # → http://localhost:8000
```

## Project structure

```
public/      → web root (the ONLY folder exposed to the browser)
app/         → controllers, models, middleware, views
config/      → configuration loaders
database/    → migrations and seeders
storage/     → uploads, backups, logs (not web-accessible)
docs/        → project brief and decisions
```

## Security notes

- Never commit `.env`.
- Never commit real resident data (see `SECURITY.md`).
- All DB access uses PDO prepared statements.
- All POST requests require a CSRF token.

## License

Proprietary — internal Chemoot Ward project.