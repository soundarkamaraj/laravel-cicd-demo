# laravel-cicd-demo

A Laravel application with a CI/CD pipeline deploying to a remote server.

**Live:** http://REDACTED

## Stack

- **Framework:** Laravel (PHP 8.4)
- **Database:** SQLite (default, swap as needed)
- **CI/CD:** GitHub Actions
- **Deployment:** Remote server via SSH

## Local Setup

```bash
git clone <repo-url> cicd
cd cicd
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

App will be available at http://127.0.0.1:8000.

## Running Tests

```bash
php artisan test
```

## CI/CD Pipeline

The pipeline runs on every push to `main`:

1. Install dependencies
2. Run tests
3. Deploy to the remote server via SSH

Workflow file: `.github/workflows/deploy.yml` (to be added).

## Deployment

Deployment is triggered automatically on merges to `main`. The pipeline SSHes into the target server, pulls the latest code, installs dependencies, runs migrations, and reloads the app.

## License

MIT
